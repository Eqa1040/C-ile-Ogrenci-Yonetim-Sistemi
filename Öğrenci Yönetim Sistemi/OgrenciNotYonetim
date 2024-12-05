#include<stdio.h>
#include<stdlib.h>
#include<string.h>

#define MAX_STUDENTS 100
#define MAX_NAME_LENGTH 50

typedef struct {
    int id;
    char name[MAX_NAME_LENGTH];
    float grade;
}student;
 
student students[MAX_STUDENTS];
int studentCount = 0 ;

void addStudent(){
    if(studentCount >= MAX_STUDENTS){
        printf("maksimum kapasiteye ulaştiniz.\n");
        return;
    }
    student newStudent;
    newStudent.id = studentCount + 1;
    printf("Ogrencinin adi:");
    scanf("%s",newStudent.name);
    printf("\nOgrencinin notu:");
    scanf("%f",&newStudent.grade);
    students[studentCount]=newStudent;
    studentCount++;
    printf("\nOgrenci basariyla eklendi.\n");
}
void listStudents(){
    if(studentCount == 0){
        printf("henüz ogrenci eklenmedi.\n");
        return;
    }
    printf("\nTum ogrenciler:\n");
    printf("ID\tAd\tNotu\n");
    printf("----------------------------\n");
    for(int i = 0; i<studentCount;i++){
        printf("%d\t%s\t%.2f\n",students[i].id,students[i].name,students[i].grade);
    }
}
void updateStudent(){
    int id ;
    printf("\nGuncellenecek ogrencinin ID'si:");
    scanf("%d",&id);
    if(id<1 || id>studentCount){
        printf("Gecersiz ID.\n");
        return;
    }
    printf("\nYeniOgrenciadi:");
    scanf("%s",students[id-1].name);
    printf("\nYeniOgrencinotu:");
    scanf("%f",&students[id-1].grade);
    printf("\nOgrencibilgileribasariylaguncellendi.\n");
}
void deleteStudent(){
    int id;
    printf("\nSilinecek ogrencinin ID'si:");
    scanf("%d",&id);
    if(id<1 || id>studentCount){
        printf("Gecersiz ID.\n");
        return;
    }
    for(int i = id-1;i<studentCount-1;i++){
        students[i]=students[i+1];
    }
    studentCount--;
    printf("\nOgrenci basariyla silindi.\n");
}
int main(){
    int choice ; 
    do{
        printf("\nOgrenci Not Yonetim Sistemi\n");
        printf("1 - Ogrenci Ekle\n");
        printf("2 - Ogrencileri listele\n");
        printf("3 - Ogrenci Guncelle\n");
        printf("4 - Ogrenci sil\n");
        printf("0 - Cikis\n");
        printf("Secimininiz:");
        scanf("%d",&choice);
        switch(choice){
            case 1:
            addStudent();
            break;
            case 2:
            listStudents();
            break; 
            case 3:
            updateStudent();
            break;
            case 4:
            deleteStudent();
            break;
            case 5:
            printf("\nProgramdan cikiliyor...\n");
            break;
            default:
            printf("\nGecersiz secim.\n");
        }
    }
    while(choice != 0);
    return 0;
}