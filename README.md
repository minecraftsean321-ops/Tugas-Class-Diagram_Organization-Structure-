# Tugas-Class-Diagram_Organization-Structure-

| No.  | Name                   | NRP                |
|------|------------------------|--------------------|
| 1.   | Sean Arthur Tamajaya   | 5027251050         |

Penjelasan  
**Deskripsi Kasus**  
Jadi studi kasus yang saya gunakan adalah masalah dari suatu organisasi yang tidak bisa merubah-rubah data yang dimilikinya dengan efisien dan efektif dikarenakan organisasi tersebut masih menggunakan sistem manual. Jadi disini saya berusaha untuk mmebuat program dimana pemilik dari organisasi tersebut dapat merubah dan menampilkan data dari setiap divisi yang ada diorganisasi dengan lebih efesien dan efektif menggunakan konsep dari OOP.

**Class Diagram**  

![Class Diagram](<Assets/Class Diagram_Organization Structure.png>)

**Kode Java**

```java

import java.util.List;
import java.util.ArrayList;

class Organization implements OrganizationInfo{
    private
    String name;
    int foundedYear;

public Organization (String name, int foundedYear) {
    this.name = name;
    this.foundedYear = foundedYear;
}

String getName (){
    return name;
}

void setName (String namaBaru) {
    this.name = namaBaru;
}

public int getFoundedYear() {
    return foundedYear;
}

public void setFoundedYear(int foundedYear) {
    this.foundedYear = foundedYear;
}

@Override
public void showInfo(){
    System.out.println("Name of the Organization: " + name);
    System.out.println("Year formed: " + foundedYear);
}

}

public interface OrganizationInfo {

    void showInfo ();
    
}

class Head implements OrganizationInfo{
    private
    String headId;
    String namaKetua;
    String email;
    protected Organization org;

    public Head (Organization org, String headId, String namaKetua, String email){
        this.org = org;
        this.headId = headId;
        this.namaKetua = namaKetua;
        this.email = email;
    }

    public String getHeadId() {
        return headId;
    }

    public String getNamaKetua() {
        return namaKetua;
    }

    public String getEmail() {
        return email;
    }
    public void setHeadId(String headId) {
        this.headId = headId;
    }

    public void setNamaKetua(String namaKetua) {
        this.namaKetua = namaKetua;
    }

    public void setEmail(String email) {
        this.email = email;
    }

    void makeDecision () {
        System.out.println( "Ketua sedang membuat keputusan");        
    }

    void superviseTeam (){

    }

    @Override
    public void showInfo() {
        System.out.println("HeadID: " + headId);
        System.out.println("Nama Ketua: " + namaKetua);
        System.out.println("Email: " + email);
    }
}

class Treasurer implements OrganizationInfo{
    private 
    String treasurerID;
    String nama;
    String email;
    double balanced;
    protected Organization org;

    public Treasurer (Organization org, String treasurerID, String nama, String email, double balanced){
        this.org = org;
        this.treasurerID = treasurerID;
        this.nama = nama;
        this.balanced = balanced;
        this.email = email;

    }

    public String getTreasurerID() {
        return treasurerID;
    }

    public String getNama() {
        return nama;
    }

    public String getEmail() {
        return email;
    }

    public double getBalanced() {
        return balanced;
    }

    public void setNama(String nama) {
        this.nama = nama;
    }

    public void setEmail(String email) {
        this.email = email;
    }

    public void setBalanced(double balanced) {
        this.balanced = balanced;
    }

    public void setTreasurerID(String treasurerID) {
        this.treasurerID = treasurerID;
    }

    //Mencatat penegeluaran beserta deskripsi dan jumlahnya
    void recordExpense (String description, double amount){
        System.out.println("Deskripsi Pengeluaran: " + description);
        System.out.println("Pengeluaran Organisasi: " + amount);
    };

    //Mencatat pendapatan beserta sumber dan jumlahnya
    void recordIncome (String source, double amount) {};

    void generteReport () {

    };

    @Override
    public void showInfo () {
        System.out.println("TresureID: " + treasurerID);
        System.out.println("Nama Bendahara: " + nama);
        System.out.println("Email: " + email);
        System.out.println("Jumlah kas: " + balanced);
    }

}

class Instructor implements OrganizationInfo {
private
String instructorID;
String name;
String email;
String specialization;
protected String[] schedule;

public Instructor (String instructorID, String name, String email, String specialization, String[] schedule){
    this.instructorID = instructorID;
    this.name = name;
    this.email = email;
    this.specialization = specialization;
    this.schedule = schedule;
}



public String getInstructorID() {
    return instructorID;
}

public void setInstructorID(String instructorID) {
    this.instructorID = instructorID;
}

public String getName() {
    return name;
}

public void setName(String name) {
    this.name = name;
}

public String getEmail() {
    return email;
}

public void setEmail(String email) {
    this.email = email;
}

public String getSpecialization() {
    return specialization;
}

public void setSpecialization(String specialization) {
    this.specialization = specialization;
}

void conductClass (String className) {};

void createLesson (String lessonName) {};

void evaluateStudent (String studentName, double score){};

    @Override
    public void showInfo () {
        System.out.println("InstructorID: " + instructorID);
        System.out.println("Nama instructor: " + name);
        System.out.println("Email instructor: " + email);
        System.out.println("Keahlian: " + specialization);
        for(int i = 0; i < schedule.length; i++){
        System.out.println("Jadwal ke " + (i + 1) + ": " + schedule[i]);
        }
    }
}



class External implements OrganizationInfo{
private
String externalID;
String name;
String email;
String organization;

public External(String externalID, String name, String email, String organization){
    this.externalID = externalID;
    this.name = name;
    this.email = email;
    this.organization = organization;
}

public String getExternalID() {
    return externalID;
}

public void setExternalID(String externalID) {
    this.externalID = externalID;
}

public String getName() {
    return name;
}

public void setName(String name) {
    this.name = name;
}

public String getEmail() {
    return email;
}

public void setEmail(String email) {
    this.email = email;
}

public String getOrganization() {
    return organization;
}

public void setOrganization(String organization) {
    this.organization = organization;
}

void buildPartnership (String partnername){

};

void promoteEvent (String eventname){

};

@Override
public void showInfo () {
    System.out.println("ExternalID: " + externalID);
    System.out.println("Nama eksternal: " + name);
    System.out.println("Email eksternal: " + email);
    System.out.println("Partner Organisasi: " + organization); 

}

}

class Secretary implements OrganizationInfo{
    private
    String secretaryID;
    String name;
    String email;
    String phone;
    protected Organization org;

    public Secretary (Organization org, String secretaryID, String name, String email, String phone){
        this.org = org;
        this.secretaryID = secretaryID;
        this.name = name;
        this.email = email;
        this.phone = phone;
    }

    public String getSecretaryID() {
        return secretaryID;
    }

    public void setSecretaryID(String secretaryID) {
        this.secretaryID = secretaryID;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getEmail() {
        return email;
    }

    public void setEmail(String email) {
        this.email = email;
    }

    public String getPhone() {
        return phone;
    }

    public void setPhone(String phone) {
        this.phone = phone;
    }

    void recordMinutes(String Minutes){

    };

    void scheduleEvent(String eventName, String date){};

    void sendNotification(String message){};

    @Override
    public void showInfo () {
        System.out.println("SecretaryID: " + secretaryID);
        System.out.println("Secretary Name: " + name);
        System.out.println("Email: " + email);
        System.out.println("Secretary phone: " + phone);
    }
}

class Internal implements OrganizationInfo {
    private
    String internalID;
    String name;
    String email;
    String responsibility;
    protected Organization org;

    Internal (Organization org, String internalID, String name, String email, String responsibility){
        this.org = org;
        this.internalID = internalID;
        this.name = name;
        this.email = email;
        this.responsibility = responsibility;
    }

    public String getInternalID() {
        return internalID;
    }

    public void setInternalID(String internalID) {
        this.internalID = internalID;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getEmail() {
        return email;
    }

    public void setEmail(String email) {
        this.email = email;
    }

    public String getResponsibility() {
        return responsibility;
    }

    public void setResponsibility(String responsibility) {
        this.responsibility = responsibility;
    }

    void coordinateInternal (String activity) {};

    void manageMembership () {};

    @Override
    public void showInfo () {
        System.out.println("InternalID: " + internalID);
        System.out.println("Internal Name: " + name);
        System.out.println("Email: " + email);
        System.out.println("Tanggung jawab: " + responsibility);
    }
}

class Main {
    public static void main (String[] args){
    Organization myOrg = new Organization("Pecinta Musik", 2007);

    List<OrganizationInfo> listPIC = new ArrayList<>();
    listPIC.add(new Organization("Pecinta Musik", 2007));
    listPIC.add(new Head(myOrg, "5087", "Sam", "email@gmail.com"));
    listPIC.add(new Treasurer(myOrg, "5312", "Anna", "Anna@gmail.com", 200000));
    listPIC.add(new Instructor("5547", "Steve vai", "Steve@gmail.com", "Guitarist", new String[] {"Senin, 15:00", "Rabu, 07:00"}));
    listPIC.add(new External("4321", "John", "john@gmail.com", "Pecinta Film"));
    listPIC.add(new Secretary(myOrg, "6324", "Julia", "Julia@gmail.com", "6281242445342"));
    listPIC.add(new Internal(myOrg, "7765", "Michele", "Michele@gmail.com", "Makes everyone happy"));

    System.out.println("====== Organization Data ======");
    for (OrganizationInfo o :listPIC){
        o.showInfo();
        System.out.println("-----------------------------");
    }

    }
   
}

```
**Output Program**

!
