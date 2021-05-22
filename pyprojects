import csv
import os
import colorama
import pandas as pd
import hashlib
from colorama import Fore, Back, Style

csv_filename = 'projek.csv'


def clear_screen():
    os.system('cls' if os.name == 'nt' else 'clear')

def back_menu():
    print ("\n")
    input ("Tekan Enter untuk kembali...")
    menu()

def buat_biodata():
    clear_screen()
    with open (csv_filename, mode = 'a') as csv_file:
        fieldnames =  ['NIM','Nama','Universitas','Kursus','TTL','Asal Kota','Alamat','No.Telp']
        writer = csv.DictWriter(csv_file, fieldnames=fieldnames)

        nim = input("Masukkan NIM Mahasiswa = ")
        nama = input("Masukkan Nama Mahasiswa = ")
        univ = input("Masukkan Asal Universitas  = ")
        kursus = input("Masukkan Kursus Yang Mahasiswa ingin ikuti = ")
        ttl = input ("Masukkan Tempat dan Tanggal Lahir Mahasiswa = ")
        askot = input ("Masukkan Asal Kota Mahasiswa = ")
        alamat = input ("Masukkan Alamat Mahasiswa = ")
        telepon = input("Masukkan No.Telp Mahasiswa yang bisa dihubungi = ")

        writer.writerow({'NIM':nim,'Nama':nama,'Universitas':univ,'Kursus':kursus,'TTL':ttl,'Asal Kota':askot,'Alamat':alamat,'No.Telp':telepon})
        print ("")
        print ("="*60)
        print ("berhasil disimpan !")


def edit_biodata():
    clear_screen()
    biodata=[]
    with open(csv_filename, mode= "r") as csv_file:
        csv_reader = csv.DictReader(csv_file)
        for row in  csv_reader:
            biodata.append(row)
    print ("="*102)
    print ("NIM \t Nama \t Universitas \t Kursus \t TTL \t Asal Kota \t Alamat \t No.Telp")
    print ("="*102)
    
    for data in biodata:
        print (f"{data['NIM']} \t {data['Nama']} \t {data['Universitas']}\t {data['Kursus']}\t {data['TTL']}\t {data['Asal Kota']} \t {data['Alamat']} \t {data['No.Telp']}")

    print ("============================================================================================================")
    nim = input("Masukkan NIM Mahasiswa = ")
    nama = input("Masukkan Nama Mahasiswa = ")
    univ = input("Masukkan Asal Universitas  = ")
    kursus = input("Masukkan Kursus Yang Mahasiswa ingin ikuti = ")
    ttl = input ("Masukkan Tempat dan Tanggal Lahir Mahasiswa = ")
    askot = input ("Masukkan Asal Kota Mahasiswa = ")
    alamat = input ("Masukkan Alamat Mahasiswa = ")
    telepon = input("Masukkan No.Telp Mahasiswa yang bisa dihubungi = ")

    indeks = 0
    for data in biodata:
        if data['NIM'] == nim:
            biodata[indeks]['Nama'] = nama
            biodata[indeks]['Universitas'] = univ
            biodata[indeks]['Kursus'] = kursus
            biodata[indeks]['TTL'] = ttl
            biodata[indeks]['Asal Kota'] = askot
            biodata[indeks]['Alamat'] = alamat
            biodata[indeks]['No.Telpon'] = telepon
        indeks = indeks + 1
    with open(csv_filename, mode ="w") as csv_file:
        fieldnames =  ['NIM','Nama','Universitas','Kursus','TTL','Asal Kota','Alamat','No.Telp']
        writer = csv.DictWriter(csv_file, fieldnames=fieldnames)
        writer.writeheader()
        for new_data in biodata:
            writer.writerow({'NIM':new_data['NIM'],'Nama':new_data['Nama'],'Universitas':new_data['Universitas'],'Kursus':new_data['Universitas'],'TTL':new_data['TTL'],'Asal Kota':new_data['Asal Kota'],'Alamat':new_data['Alamat'],'No.Telp':new_data['No.Telp']})
    back_menu()

def delete_biodata():
    clear_screen()
    biodata = []
    with open(csv_filename, mode ="r") as csv_file:
        csv_reader = csv.DictReader(csv_file)
        for row in csv_reader:
            biodata.append(row)
    print ("="*82)
    print ("NIM \t Nama \t Universitas \t Kursus \t TTL \t Asal Kota \t Alamat \t No.Telp")
    print ("="*82)
    for data in biodata:
        print (f"{data['NIM']} \t {data['Nama']} \t {data['Universitas']}\t {data['Kursus']}\t {data['TTL']}\t {data['Asal Kota']} \t {data['Alamat']} \t {data['No.Telp']}")
    
    print ("="*82)
    nim = input("Hapus NIM > ")

    indeks = 0
    for data in biodata:
        if data['NIM'] == nim:
            indeks = -1
            biodata.remove(biodata[indeks])
        indeks = indeks +1
    
    with open(csv_filename, mode ="w") as csv_file:
        fieldnames =  ['NIM','Nama','Universitas','Kursus','TTL','Asal Kota','Alamat','No.Telp']
        writer = csv.DictWriter(csv_file, fieldnames=fieldnames)
        writer.writeheader()
        for new_data in biodata:
            writer.writerow({'NIM':new_data['NIM'],'Nama':new_data['Nama'],'Universitas':new_data['Universitas'],'Kursus':new_data['Universitas'],'TTL':new_data['TTL'],'Asal Kota':new_data['Asal Kota'],'Alamat':new_data['Alamat'],'No.Telp':new_data['No.Telp']})
        
    if indeks == len(biodata):
        print ("Data Tidak Ada")
    else:
        print ("Data Mahasiswa Telah Terhapus...")
    
    back_menu()

def search_biodata():
    clear_screen()
    biodata = []
    with open(csv_filename, mode ="r") as csv_file:
        csv_reader = csv.DictReader(csv_file)
        for row in csv_reader:
            biodata.append(row)

    nim = input("Cari berdasrakan NIM Mahasiswa > ")

    data_found = []

    indeks = 0
    for data in biodata:
        if (data['NIM'] == nim):
            data_found = biodata[indeks]   
        indeks = indeks + 1

    if len(data_found) > 0:
        print("DATA DITEMUKAN: ")
        print(f"Nama: {data_found['Nama']}")
        print(f"Universitas: {data_found['Universitas']}")
        print(f"Kursus: {data_found['Kursus']}")
        print(f"TTL:{data_found['TTL']}")
        print(f"Asal Kota: {data_found['Asal Kota']}")
        print(f"Alamat: {data_found['Alamat']}")
        print(f"No.Telp: {data_found['No.Telp']}")
    else:
        print("Tidak ada data ditemukan")
    back_menu()

def show_biodata():
    clear_screen()
    biodata = []
    with open(csv_filename, mode="r") as csv_file:
        csv_reader = csv.DictReader(csv_file)
        for row in csv_reader:
            biodata.append(row)
    print ("="*120)
    print ("NIM \t Nama \t Universitas \t Kursus \t TTL \t Asal Kota \t Alamat \t No.Telp")
    print ("="*120)

    for data in biodata:
        print (f"{data['NIM']} \t {data['Nama']}\t {data['Universitas']} \t {data['Kursus']}\t {data['TTL']} \t {data['Asal Kota']} \t {data['Alamat']} \t {data['No.Telp']}")

# def bi():
#     basing = []
#     with open(csv_filename, mode= "a") as csv_file:
#         writer = csv.writer(csv_file)
#         writer.writerow(basing)  

def pdlist():
    df = pd.read_csv('/A/Python/projek/projek.csv', error_bad_lines=False)
    print(df.to_string())
def lg():
    clear_screen()
    #encode string
    def encodeSHA512(string):
        hs =  hashlib.sha512()
        hs.update(string.encode("UTF-8"))
        hs = hs.hexdigest()
        return hs

    #compare a strig with a hash
    def testSHA512(string, hs):
        if encodeSHA512(str(string)) == hs:
            return True
        else:
            return False

    #register an user
    def regis(login, password):
        login = str(login)
        password = encodeSHA512(str(password))
        file = open("login.txt", 'a')
        file.write("\n"+login+"\n"+password)
        file.close()

    print('''
            [!] REGISTER ----> 1
            [!] LOGIN    ----> 2
            [!] EXIT     ----> 0
        ''')

    op = int(input(">>> "))

    if op == 1:
        #Register an user
        userName = input("Username: ")
        passWord = input("Password: ")
        passConf = input("Password: ")
        if passWord == passConf:
            try:
                regis(userName, passWord)
                print("\nSuccess!\n")
                input ("")
            except:
                print("\n;-; Fail... Try again\n")
                input ("")

    elif op == 2:
        userName = input("\nUsername: ")+"\n"
        passWord = input("Password: ")
        #open the "data base"
        with open("login.txt", 'r') as users:
            loginAndPass = users.readlines()
            #find for the login in "data base"
            if userName in loginAndPass:
                posi = loginAndPass.index(userName)
                #make the login
                if posi % 2 != 0:
                    if testSHA512(passWord, loginAndPass[int(posi)+1].replace('\n', '')):
                        print("\nSuccess!\n")
                        input ("")
                        menu()
                    else:
                        print("\nInvalid login or password\n")
                        input ("")
                else:
                    print("\nInvalid login or password\n")
                    input ("")
            else:
                print("\nInvalid login or password\n")
                input ("")
    elif op == 0:
        clear_screen()
        exit()
    else :
        print ("Input yang anda masukkan salah")
        input ("")

def ksh():
    print (" ---------------------------------- ")
    print ("|     1. Bahasa Inggris            |")
    print ("|     2. Pemgrogramman Java        |")
    print ("|     3. Pemrogramman Web          |")
    print ("|     4. Jaringan Komputer         |")
    print ("|     5. Penerapan VR\AR           |")
    print ("|     6. AI dan Machine Learning   |")
    print ("|     7. Pemrogramman Mobile       |")
    print ("|     8. IOT                       |")
    print ("|     9. Robotika                  |")
    print ("|     10. Animasi 3D               |")
    print (" ---------------------------------- ")

    ap = input("Masukkan Pilihan Kursus Anda >> ")

    if ap == '1':
        print ("Kursus Bahasa Inggris ")
        print ("Penanggung Jawab Dr. Michael Stein")
        print ("Lokasi : Jln. Samarinda Bangunan Central Studio Kursus Informatika ")
        aps = input ("Apakah anda yakin ? >> ")

        if aps == "Yakin" or "yakin":
            buat_biodata()
            
        else :
            ksh()
    elif ap == '2':
        print ("Kursus Pemrogramman Java ")
        print ("Penanggung Jawab Dr.Budi Sulistyo")
        print ("Lokasi : Jln. Samarinda Bangunan Central Studio Kursus Informatika")
        apl = input ("Apakah anda yakin ? >> ")

        if apl == "Yakin" or "yakin":
            buat_biodata()
        else :
            ksh()
    elif ap == '3':
        print ("Kursus Pemrogramman Web ")
        print ("Penanggung Jawab Dr.Budi Sulistyo ")
        print ("Lokasi : Jln. Samarinda Bangunan Central Studio Kursus Informatika")
        apm = input ("Apakah anda yakin ? >> ")

        if apm == "Yakin" or "yakin":
            buat_biodata()
        else :
            ksh()
    elif ap == '4':
        print ("Kursus Jaringan Komputer ")
        print ("Penanggung Jawab Dr.Agung Hapsawan ")
        print ("Lokasi : Jln. Samarinda Bangunan Central Studio Kursus Informatika")
        apc = input ("Apakah anda yakin ? >> ")

        if apc == "Yakin" or "yakin":
            buat_biodata()
        else :
            ksh()
    elif ap == '5':
        print ("Kursus Penerapan VR\AR ")
        print ("Penanggung Jawab Dr.Hendri ")
        print ("Lokasi : Jln. Samarinda Bangunan Central Studio Kursus Informatika")
        apd = input ("Apakah anda yakin ? >> ")

        if apd == "Yakin" or "yakin":
            buat_biodata()
        else :
            ksh()        
    elif ap == '6':
        print ("Kursus AI dan Machine Learning ")
        print ("Penanggung Jawab Dr.Michael Stein ")
        print ("Lokasi : Jln. Samarinda Bangunan Central Studio Kursus Informatika")
        apo = input ("Apakah anda yakin ? >> ")

        if apo == "Yakin" or "yakin":
            buat_biodata()
        else :
            ksh()       
    elif ap == '7':
        print ("Kursus Pemrogramman Mobile ")
        print ("Penanggung Jawab Dr.Martha ")
        print ("Lokasi : Jln. Samarinda Bangunan Central Studio Kursus Informatika")
        apt = input ("Apakah anda yakin ? >> ")

        if apt == "Yakin" or "yakin":
            buat_biodata()
        else :
            ksh()
    elif ap == '8':
        print ("Kursus IOT (Internet Of Thinks) ")
        print ("Penanggung Jawab Dr.Hairunnisa Syabil ")
        print ("Lokasi : Jln. Samarinda Bangunan Central Studio Kursus Informatika")
        api = input ("Apakah anda yakin ? >> ")

        if api == "Yakin" or "yakin":
            buat_biodata()
        else :
            ksh() 
    elif ap == '9':
        print ("Kursus Robotika ")
        print ("Penanggung Jawab Dr.Hendri ")
        print ("Lokasi : Jln. Samarinda Bangunan Central Studio Kursus Informatika")
        apy = input ("Apakah anda yakin ? >> ")

        if apy == "Yakin" or "yakin":
            buat_biodata()
        else :
            ksh()          
    elif ap == '10':
        print ("Kursus Animasi 3D ")
        print ("Penanggung Jawab Dr.Martha ")
        print ("Lokasi : Jln. Samarinda Bangunan Central Studio Kursus Informatika")
        apr = input ("Apakah anda yakin ? >> ")

        if apr == "Yakin" or "yakin":
            buat_biodata()
        else :
            ksh()

def ksh1():
    print (" ---------------------------------- ")
    print ("|     1. Bahasa Inggris            |")
    print ("|     2. Pemgrogramman Java        |")
    print ("|     3. Pemrogramman Web          |")
    print ("|     4. Jaringan Komputer         |")
    print ("|     5. Penerapan VR\AR           |")
    print ("|     6. AI dan Machine Learning   |")
    print ("|     7. Pemrogramman Mobile       |")
    print ("|     8. IOT                       |")
    print ("|     9. Robotika                  |")
    print ("|     10. Animasi 3D               |")
    print (" ---------------------------------- ")

    ap_self = input("Masukkan Pilihan Kursus Anda >> ")


    if ap_self == '1':
        print ("Kursus Bahasa Inggris ")
        print ("Penanggung Jawab Dr. Michael Stein")
        print ("Lokasi : Jln. Samarinda Bangunan Central Studio Kursus Informatika ")
        aps_self = input ("Apakah anda yakin ? >> ")

        if aps_self == "Yakin" or "yakin":
            delete_biodata()
        else :
            ksh1()
    elif ap_self == '2':
        print ("Kursus Pemrogramman Java ")
        print ("Penanggung Jawab Dr.Budi Sulistyo")
        print ("Lokasi : Jln. Samarinda Bangunan Central Studio Kursus Informatika")
        apl_self = input ("Apakah anda yakin ? >> ")

        if apl_self == "Yakin" or "yakin":
            delete_biodata()
        else :
            ksh1()
    elif ap_self == '3':
        print ("Kursus Pemrogramman Web ")
        print ("Penanggung Jawab Dr.Budi Sulistyo ")
        print ("Lokasi : Jln. Samarinda Bangunan Central Studio Kursus Informatika")
        apm_self = input ("Apakah anda yakin ? >> ")

        if apm_self == "Yakin" or "yakin":
            delete_biodata()
        else :
            ksh1()
    elif ap_self == '4':
        print ("Kursus Jaringan Komputer ")
        print ("Penanggung Jawab Dr.Agung Hapsawan ")
        print ("Lokasi : Jln. Samarinda Bangunan Central Studio Kursus Informatika")
        apc_self = input ("Apakah anda yakin ? >> ")

        if apc_self == "Yakin" or "yakin":
            delete_biodata()
        else :
            ksh1()
    elif ap_self == '5':
        print ("Kursus Penerapan VR\AR ")
        print ("Penanggung Jawab Dr.Hendri ")
        print ("Lokasi : Jln. Samarinda Bangunan Central Studio Kursus Informatika")
        apd_self = input ("Apakah anda yakin ? >> ")

        if apd_self == "Yakin" or "yakin":
            delete_biodata()
        else :
            ksh1()        
    elif ap_self == '6':
        print ("Kursus AI dan Machine Learning ")
        print ("Penanggung Jawab Dr.Michael Stein ")
        print ("Lokasi : Jln. Samarinda Bangunan Central Studio Kursus Informatika")
        apo_self = input ("Apakah anda yakin ? >> ")

        if apo_self == "Yakin" or "yakin":
            delete_biodata()
        else :
            ksh1()       
    elif ap_self == '7':
        print ("Kursus Pemrogramman Mobile ")
        print ("Penanggung Jawab Dr.Martha ")
        print ("Lokasi : Jln. Samarinda Bangunan Central Studio Kursus Informatika")
        apt_self = input ("Apakah anda yakin ? >> ")

        if apt_self == "Yakin" or "yakin":
            delete_biodata()
        else :
            ksh1()
    elif ap_self == '8':
        print ("Kursus IOT (Internet Of Thinks) ")
        print ("Penanggung Jawab Dr.Hairunnisa Syabil ")
        print ("Lokasi : Jln. Samarinda Bangunan Central Studio Kursus Informatika")
        api_self = input ("Apakah anda yakin ? >> ")

        if api_self == "Yakin" or "yakin":
            delete_biodata()
        else :
            ksh1() 
    elif ap_self == '9':
        print ("Kursus Robotika ")
        print ("Penanggung Jawab Dr.Hendri ")
        print ("Lokasi : Jln. Samarinda Bangunan Central Studio Kursus Informatika")
        apy_self = input ("Apakah anda yakin ? >> ")

        if apy_self == "Yakin" or "yakin":
            delete_biodata()
        else :
            ksh1()          
    elif ap_self == '10':
        print ("Kursus Animasi 3D ")
        print ("Penanggung Jawab Dr.Martha ")
        print ("Lokasi : Jln. Samarinda Bangunan Central Studio Kursus Informatika")
        apr_self = input ("Apakah anda yakin ? >> ")

        if apr_self == "Yakin" or "yakin":
            delete_biodata()
        else :
            ksh1()


def menu():
    clear_screen()
    md = input ('''
                [|] Admin     -----> (Verify)
                [|] Mahasiswa -----> 2
                [|] Exit      -----> 0    
>> ''')

    if md == "admin" :
        menu1()
    elif md == "2":
        menu2()
    elif md == "0":
        exit()
    else :
        print ("Anda salah memasukkan input !")

def menu1():
    clear_screen()
    print (Fore.GREEN+"/================================================\ "+Style.RESET_ALL)
    print (Fore.CYAN+" | Selamat Datang di Sistem Pendaftaran Mahasiswa |"+Style.RESET_ALL)
    print (Fore.CYAN+" |     Untuk Pendfataran Kursus Pembelajaran      |"+Style.RESET_ALL)
    print (Fore.CYAN+" |                [--Menu Admin--]                |"+Style.RESET_ALL)
    print (Fore.GREEN+"\================================================/"+Style.RESET_ALL)
    print("")
    print(Fore.YELLOW+"Menu"+Style.RESET_ALL)
    print(Fore.CYAN)
    print ("[1].Pendaftaran Mahasiswa")
    print ("[2].Pengajuan Penarikan Mahasiswa")
    print ("[3].Pengubahan Biodata Mahasiswa")
    print ("[4].Pencarian Biodata Mahasiswa")
    print ("[5].Tampilkan Biodata Mahasiswa")
    print ("[0].Untuk exit")
    print(Style.RESET_ALL)
    print (Fore.GREEN+"<---------------------------------------->"+Style.RESET_ALL)
    selected_menu = input(Fore.CYAN+"Silahkan masukkan pilihan anda = "+Style.RESET_ALL)
    
   
    if selected_menu == '1' :
        ksh()
    elif selected_menu == '2' :
        ksh1()
    elif selected_menu == '3' :
        edit_biodata()
    elif selected_menu == '4' :
        search_biodata()
    elif selected_menu == '5':
        show_biodata()
    elif selected_menu == '0':
        exit()
    else :
        print ('nilai yang anda masukkan salah')
        menu1()
    back_menu()

   

    
    

def menu2():
    clear_screen()
    print (Fore.GREEN+"/================================================\ "+Style.RESET_ALL)
    print (Fore.CYAN+" | Selamat Datang di Sistem Pendaftaran Mahasiswa |"+Style.RESET_ALL)
    print (Fore.CYAN+" |     Untuk Pendfataran Kursus Pembelajaran      |"+Style.RESET_ALL)
    print (Fore.CYAN+" |             [--Menu Mahasiswa--]               |"+Style.RESET_ALL)
    print (Fore.GREEN+"\================================================/"+Style.RESET_ALL)
    print("")
    print(Fore.YELLOW+"Menu"+Style.RESET_ALL)
    print(Fore.CYAN)
    print ("[1].Pendaftaran Mahasiswa")
    print ("[2].Pengajuan Penarikan Mahasiswa")
    print ("[3].Pencarian Biodata Mahasiswa")
    print ("[4].List Mahasiswa Yang Sudah Terdaftar")
    print ("[0].Untuk exit")
    print(Style.RESET_ALL)
    print (Fore.GREEN+"<---------------------------------------->"+Style.RESET_ALL)
    pilihan_menu = input(Fore.CYAN+"Silahkan masukkan pilihan anda = "+Style.RESET_ALL)

    if pilihan_menu == '1' :
        buat_biodata()
    elif pilihan_menu == '2' :
        ksh1()
    elif pilihan_menu == '3' :
        search_biodata()
    elif pilihan_menu == '4':
        pdlist()
    elif pilihan_menu == '0' :
        exit()
    else : 
        print ('nilai yang anda masukkan salah') 
        menu2()
    back_menu()

while True:
    lg()
