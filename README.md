# Yazilim_Gelistirici_Yetistirme-Python_Selenium-odev2

#Bu öğrenci kayıt sisteminde;
#Aldığı isim soy isim ile listeye öğrenci ekleyen
#Aldığı isim soy isim ile eşleşen değeri listeden kaldıran
#Listeye birden fazla öğrenci eklemeyi mümkün kılan
#Listedeki tüm öğrencileri tek tek ekrana yazdıran
#Öğrencinin listedeki index numarası öğrenci numarası olarak kabul edildiğini düşünerek öğrencinin numarasını öğrenmeyi mümkün kılan
#Listeden birden fazla öğrenci silmeyi mümkün kılan (döngü kullanınız)
#fonksiyonları geliştiriniz ve her bir fonksiyonu en az bir kere çağırarak konsolda test ediniz


    print("*****Student Registration*****")

    student_list = []

    def studentRegistration():
         name = input("Please enter your student name: ")
         surname = input("Please enter your student surname: ")
         return name, surname
    
    def mainMenu():
    
    action = input("Choose your action: "
                   "1-Add Student,"
                   "2-Remove Student,"
                   "3-List Students,"
                   "4-Learn Student Number,"
                   "5-Exit ")

    if action == "1":
        addStudent()
    elif action == "2":
        removeStudent()
    elif action == "3":
        listStudent()
    elif action == "4":
        studentNumber()
    elif action == "5":
        exit_program()
    else:
        print("Invalid input. Please try again.")
        mainMenu()
    
    def addStudent():
        name, surname = studentRegistration()
        student_list.append((name, surname))
        print("Student added: {}, {}".format(name, surname))
        mainMenu()
    
    def removeStudent():
        name, surname = studentRegistration()
        if (name, surname) in student_list:
            student_list.remove((name, surname))
            print("Student removed: {}, {}".format(name, surname))
        else:
            print("Student not found.")
            mainMenu()

    def listStudent():
        print("List of students:")
        for name, surname in student_list:
           print("- {}, {}".format(name, surname))
        mainMenu()
    
    def studentNumber():
        name, surname = studentRegistration()
        if (name, surname) in student_list:
            index = student_list.index((name, surname))
            print("Student number: {}".format(index))
        else:
            print("Student not found.")
        mainMenu()

    def exit_program():
        print("program exiting")
        exit()
    
