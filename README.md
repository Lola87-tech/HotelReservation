# HotelReservation
//This program is designed for Hotels and Reservations from business management prespective.
#include<iostream> #include<fstream> #include<string> using namespace std; class SingleRooms
{
private:
string phoneNum;
string fName;
string lName;
int roomNum = 5;
int roomType=4;
float roomPrice= 150;
public:
SingleRooms(){}
void setFname(string fname){
this->fName = fname; }
string getFname(){ return this->fName;
}
float getRoomPrice(){
return this->roomPrice; }
void setLname(string lname){ this->lName = lname;
}
string getLname(){
return this->lName; }
};
class PentHouseRooms {
private:
string phoneNum; string fName; string lName;
int roomNum =2;
int roomType = 1;

 float roomPrice = 1000;
public:
PentHouseRooms(){}
void setFname(string fname){
this->fName = fname; }
string getFname(){ return this->fName;
}
float getRoomPrice(){
return this->roomPrice; }
void setLname(string lname){ this->lName = lname;
}
string getLname(){
return this->lName; }
};
class ExecutiveRooms {
private:
string phoneNum;
string fName; string lName;
int roomNum=3; int roomType = 2;
float roomPrice =500;
public:
ExecutiveRooms(){}
void setFname(string fname){
this->fName = fname; }
string getFname(){ return this->fName;
}
float getRoomPrice(){
return this->roomPrice; }

 void setLname(string lname){ this->lName = lname;
}
string getLname(){
return this->lName; }
};
class DoubleRooms {
private:
string phoneNum; string fName; string lName;
int roomNum = 5;
int roomType = 3;
float roomPrice = 300;
public:
DoubleRooms(){}
void setFname(string fname){
this->fName = fname; }
string getFname(){ return this->fName;
}
float getRoomPrice(){
return this->roomPrice; }
void setLname(string lname){ this->lName = lname;
}
string getLname(){
return this->lName; }
};
int main() {
string email; string phoneNum; int roomNum; string fName;

 string lName; float roomPrice; int roomType;
cout<<"Welcome to Reservations INN \n";
cout<<"Please wait for a customer service representative to assist you with reservations today, \n";
cout<<"Creating customer receipt \n"; cout <<"Customer First Name: \n"; cin>>fName;
cout<<"Customer Last Name: \n"; cin>>lName;
cout<< "Customer contact number :";
cin>>phoneNum;
cout << "Enter room type : \n"; cin>>roomType;
cout << "Enter room number: \n";
cin >> roomNum;
cout << "Please enter cutomer email address as contact info: "; cin >> email;
cout << "Enter price per night: \n";
cin >>roomPrice;
cout << "\n Displaying Receipt information \n" << endl;
cout<< "Customer full name: \n"<<fName+" "+ lName<<endl; cout << "Room type is : \n"<<roomType<<" Room "<< endl; cout <<"Room number is : \n" <<roomNum << endl;
cout << "Reservation price per night is : $"<<roomPrice<<endl;
cout << "Printing Receipt...\n";
fstream dataFile;
dataFile.open ("Reservation.txt",ios::out|ios::in);
dataFile << fixed; // Format for fixed-point notation
dataFile << fName<<" "<< lName<<endl; // Write the number
dataFile<< "Contact Phone is: "<<phoneNum<<endl;
dataFile << "Room Type "<<roomType <<" Room Number "<<roomNum <<endl; dataFile << "Reservation Nightly charge of $"<<roomPrice << endl; // Write the number
dataFile.close(); // Close the file PentHouseRooms PR;

 ExecutiveRooms ER; DoubleRooms DR; SingleRooms SR;
int roomtype;
string fname;
string lname;
int srm = 10; //to hole the running total number of single room
int drm = 5; //to hole the running total number of double room
int erm = 3; //to hole the running total number of executive room int prm = 2; //to hole the running total number of penthours room int numofrooms;
cout<<"1 - for Room Options\n";
cout <<"2 - for Room Options\n";
cout<<"3 - for Room Options\n";
cout <<"4 - for Room Options\n";
cin >> roomtype;
if (roomtype == 4){
string fname;
cout<<"Please enter your first name.\n"; cin>>fname;
SR.setFname(fname);
cout<<"Please enter your last name. \n"; cin>>lname;
SR.setLname(lname);
cout<<"Please enter number of rooms. \n"; cin >> numofrooms;
cout<<"What room number? : \n"; cin>>roomNum;
cout<<"What room type would you prefer? \n"; cin>>roomType;
srm-=srm;
if (srm > 10){
cout << "sorry no more Single rooms"; }else{
cout<< SR.getFname();
cout<<" \n Reserved : "<<numofrooms;
cout<<" \n Amount Due "<< numofrooms*SR.getRoomPrice();
}
if (roomtype == 1){
string fname;
cout<<"Please enter your first name.\n"; cin>>fname;

 PR.setFname(fname);
cout<<"Please enter your last name.\n";
cin>>lname;
cout<<"Please enter number of rooms.\n";
cin >> numofrooms;
cout<<"What room number? : \n"; cin>>roomNum;
cout<<"What room type would you prefer? \n";
cin>>roomType; prm-=prm;
if (prm < 2){
cout << "sorry no more Penthouse rooms"; }else{
cout<< PR.getFname();
cout<<"Reserved "<<numofrooms;
cout<<"Amount Due"<< numofrooms*PR.getRoomPrice();
} }
if (roomtype == 3){
string fname;
cout<<"Please enter your first name.\n"; cin>>fname;
DR.setFname(fname);
cout<<"Please enter your last name.\n"; cin>>lname;
cout<<"Please enter number of rooms.\n";
cin >> numofrooms;
cout<<"What room number? : \n"; cin>>roomNum;
cout<<"What room type would you prefer? \n"; cin>>roomType;
drm-=drm; if (drm < 5){
cout << "sorry no more Double rooms.\n"; }else{
cout<< DR.getFname();
cout<<"Reserved "<<numofrooms;
cout<<"Amount Due "<< numofrooms*DR.getRoomPrice();
} }
if (roomtype == 2){

 string fname;
cout<<"Please enter your first name.\n"; cin>>fname;
ER.setFname(fname);
cout<<"Please enter your last name.\n"; cin>>lname;
cout<<"Please enter number of rooms.\n";
cin >> numofrooms;
cout<<"What room number? : \n"; cin>>roomNum;
cout<<"What room type would you prefer? \n"; cin>>roomType;
erm-=erm; if (erm < 3){
cout << "sorry no more Executive rooms. \n"; }else{
cout<< ER.getFname();
cout<<"Reserved "<<numofrooms;
cout<<"Amount Due"<< numofrooms*ER.getRoomPrice();
} }
}
return 0; }
