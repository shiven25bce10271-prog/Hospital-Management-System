import mysql.connector
conn = mysql.connector.connect(host="localhost",user="root",password="shiv009988",database="Hospital_Management")
cursor = conn.cursor()
print("**********Welcome to the Hospital Management System**********")

while True:
    print("\nMenu:")
    print("1. Add a new patient")
    print("2. View all patients")
    print("3. Search patient by ID")
    print("4. Update patient details")
    print("5. Delete patient record")
    print("6. Exit")
    choice = input("Enter your choice: ")

    if choice == '1':
        ID = input("Enter patient ID: ")
        name = input("Enter patient name: ")
        age = int(input("Enter patient age: "))
        gender = input("Enter patient gender (Male/Female): ")
        disease = input("Enter patient disease: ")
        
        query = "INSERT INTO Patients(ID,name, age, gender, disease) VALUES(%s, %s, %s, %s, %s)"
        values = (ID,name, age, gender, disease)
        cursor.execute(query, values)
        conn.commit()
        print("Patient added successfully!")

    elif choice == '2':
        cursor.execute("SELECT * FROM Patients")
        rows = cursor.fetchall()
        print("\nAll Patients:")
        print("Name\t\t","Age\t\t","Gender\t\t","Disease\t\t","ID\t\t")
        print("---------------------------------------------------------------------------------")
        for row in rows:
            for i in row:
                print(i,end="\t\t")
            print()

    elif choice == '3':
        search_id = input("Enter patient ID to search: ")
        cursor.execute("SELECT * FROM patients WHERE id = %s", (search_id,))
        row = cursor.fetchone()
        if row:
            print("Name\t\t","Age\t\t","Gender\t\t","Disease\t\t","ID\t\t")
            print("---------------------------------------------------------------------------------")
            print(row[0],"\t\t",row[1],"\t\t",row[2],"\t\t",row[3],"\t\t",row[4])
        else:
            print("Patient not found.")

    elif choice == '4':
        update_id = input("Enter patient ID to update: ")
        cursor.execute("SELECT * FROM patients WHERE id = %s", (update_id,))
        row = cursor.fetchone()
        if row:
            print("Name\t\t","Age\t\t","Gender\t\t","Disease\t\t","ID\t\t")
            print("---------------------------------------------------------------------------------")
            print(row[0],"\t\t",row[1],"\t\t",row[2],"\t\t",row[3],"\t\t",row[4])
            name = input("Enter new name (press enter to skip): ") or row[1]
            age = input("Enter new age (press enter to skip): ") or row[2]
            gender = input("Enter new gender (press enter to skip): ") or row[3]
            disease = input("Enter new disease (press enter to skip): ") or row[4]

            query = "UPDATE patients SET name = %s, age = %s, gender = %s, disease = %s WHERE id = %s"
            values = (name, age, gender, disease, update_id)
            cursor.execute(query, values)
            conn.commit()
            print("Patient details updated!")
        else:
            print("Patient not found.")

    elif choice == '5':
        delete_id = input("Enter patient ID to delete: ")
        cursor.execute("SELECT * FROM patients WHERE id = %s", (delete_id,))
        row = cursor.fetchone()
        if row:
            cursor.execute("DELETE FROM patients WHERE id = %s", (delete_id,))
            conn.commit()
            print("Patient record deleted!")
        else:
            print("Patient not found.")

    elif choice == '6':
        print("Exiting...")
        break

    else:
        print("Invalid choice. Please try again.")

cursor.close()
conn.close()
