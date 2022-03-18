#include <iostream>
#include <fstream>
#include <string.h>
#include <cstring>
#include <conio.h>
#include <stdio.h>
#include <typeinfo>
#include <windows.h> 
#include <time.h>
#include <iomanip>
#include <algorithm>
using namespace std;

void welcome(){
	cout<<"\t\t";
	for (int j = 0; j < 90; j++) {
    Sleep(2);
    cout<<"\xDB";
 	 }
	cout<<"\n\t\t\xDB\t\t\t\t\t\t\t\t\t\t\t \xDB\n\t\t\xDB\t\t\t	RAILWAY RESERVATION SYSTEM \t\t\t\t \xDB"<<endl;
	cout<<"\t\t\xDB\t\t\t\t\t\t\t\t\t\t\t \xDB"<<endl;
	cout<<"\t\t";
	for (int j = 0; j < 90; j++) {
    Sleep(2);
    cout<<"\xDB";
 	 }
 	 cout<<"\n\n\t\t\t\t\t\t  A PROJECT MADE BY "<<endl;
 	 cout<<"\t\t\t\t\t\t    -------------"<<endl;
 	 cout<<"\t\t\t\t\t\t\xDB\xB2 AHMAD ALI TAHIR"<<endl;
 	 cout<<endl;
 	 cout<<"\t\t\t\t\t\t\xDB\xB2 MUHAMMAD ZAIN"<<endl;
 	 cout<<endl;
 	 cout<<"\t\t\t\t\t\t\xDB\xB2 AASHIQ HUSSAIN"<<endl;
 	 cout<<endl;
 	 cout<<"\t\t\t\t\t\t\xDB\xB2 TOUSEEF ILIYAS"<<endl;
 	 cout<<endl;
 	 getch();
}

bool Is_empty(std::ifstream &fin){
    return fin.peek() == std::ifstream::traits_type::eof();
}
bool check_number(long long int no){
    if (no < 0)
        return false;
    return true;
}
long long int Input_checkNO(string type){
	long long int No;
    cout << "\t\t\t Please Enter " << type << " : ";
    cin >> No;
    while (!cin)
    {
        cin.clear();
        cin.ignore(256, '\n');
        cout << "\t\t\t Please Enter Valid " << type << " : ";
        cin >> No;
    }
    while (!check_number(No))
    {
        cout << "\t\t\t Please Enter Valid " << type << " : ";
        cin >> No;
    }
    return No;
}
bool checkString(string s){ // checks if string consists only of letters

    if (!s.empty())
    {
        for (int i = 0; i < s.length(); i++)
        {
            if (!((s.at(i) >= 'a' && s.at(i) <= 'z') || (s.at(i) >= 'A' && s.at(i) <= 'Z') || s.at(i) == ' '))
            {
                return false;
            }
        }
        return true;
    }
    else
    { //return false
        return false;
    }
}






class Train{
	private:
		
	char source[20];
	char Destination[20];
	char Train_Name[20];
	char Arr_time[20];
	char Depurture_time[20];
	char Distance[20];
	long int Train_no;
	public:
		Train(){
			strcpy(source,"None");
			strcpy(Destination,"None");
			strcpy(Train_Name,"None");
			strcpy(Arr_time,"None");
			strcpy(Depurture_time,"None");
			strcpy(Distance,"None");
			Train_no=0;
		}
	void set_Train(){
		
		cout<<"Enter Train_no : ";
		cin>>Train_no;
		cin.ignore();
		cout<<"Enter source : ";
		gets(source);
		cout<<"Enter Destination : ";
		gets(Destination);
		cout<<"Enter Train_name : ";
		cin.ignore();
		cin>>Train_Name;
		cout<<"Enter Arr_time : ";
		cin.ignore();
		gets(Arr_time);
		cout<<"Enter Depurture_time : ";
		gets(Depurture_time);
		cout<<"Enter Distance : ";
		gets(Distance);
		
	}
	void display_Train(){
		cout <<"*********************************************************************************************************" << endl;
        cout<<"Train_No  ||  Train_Name  ||  Source  ||  Destination  ||  Distance  ||  Depurture_Time  ||  Arrival_Time"<<endl;
        cout <<"*********************************************************************************************************\n";
        cout<<endl;
            cout<<Train_no<<"\t       ";
			cout<<Train_Name<<"\t      ";
			cout<<source<<"\t    ";
			cout<<Destination<<"\t    ";
			cout<<Distance<<"\t     ";
			cout<<Depurture_time<<"\t       ";
			cout<<Arr_time;
			cout<<"\n\n";
	}
	void readFile(ifstream &fin)
    {
        fin.read((char *)this, sizeof(*this));
    }
  
  
    void writeFile(ofstream &fout)
    {
        fout.write((char *)this, sizeof(*this));
    }
    
	int get_TrainNo() { return this->Train_no; }
	string get_TrainSource(){return this->source;}
	string get_TrainDes(){return this->Destination;}
	string get_TrainName(){return this->Train_Name;}
	string get_TrainArr_time(){return this->Arr_time;}
	string get_Depurture_time(){return this->Depurture_time;}
	string get_Distance(){return this->Distance;}
	
	
	void set_TrainNo(char Train_no){(this->Train_no = Train_no);}
	void set_TrainSource(char source[20]){strcpy(this->source,source);}
	void set_TrainDes(char Destination[20]){strcpy(this->Destination,Destination);}
	void set_TrainName(char Train_Name[20]){strcpy(this->Train_Name, Train_Name);}
	void set_TrainArr_time(char Arr_time[20]){strcpy(this->Arr_time , Arr_time);}
	void set_TrainDepurture_time(char Depurture_time[20]){strcpy(this->Depurture_time,Depurture_time);}
	void set_TrainDistance(char Distance[20]){strcpy(this->Distance , Distance);}
	
};
class Train_node{
public:
	Train Tr;
	Train_node *link;
    Train_node *head, *cur, *next;
    Train_node()
    {
        head = cur = next = link = NULL;
    }
    void InsertAtEnd()
    {
        cur = head;
        while (cur->link != NULL)
        {

            cur = cur->link;
        }
        next = new Train_node;
        cur->link = next;
        next->Tr.set_Train();
        cur = next;
        next->link = NULL;
    }

    void insert_train()
    {

        if (head == NULL)
        {
            head = new Train_node;
            head->Tr.set_Train();
            head->link = NULL;
            writeTrainDatadata();
            system("cls");
            cout<<"\n\nTrain added Successfully\n\n"<<endl;
            _getch();
            return;
        }
        else
        {
            InsertAtEnd();
        }
        writeTrainDatadata();
        system("cls");
            cout<<"\n\nTrain Added Successfully\n\n"<<endl;
            _getch();
        return;
    }

    void SearchTrain()
    {
        int count = 0;
        char choice;
        int IDNo;
        char temp[30];
        bool flag = false;

        if (head == NULL)
        {
            cout << "\t\t\t There is no any record" << endl;
            _getch();
            return;
        }
        do
        {
            cur = head;
            cout << "\t Please choose menue to search " << endl;
            cout << "\t 1. Name " << endl;
            cout << "\t 2. Train_no " << endl;
            cout << "\t 0. Go back " << endl;
            cout << "\t Enter here :  " << endl;
            choice = getch();
            cout << endl;
            switch (choice)
            {
            case '1':
            {
                count = 0;
                cout << "\t Please Enter Name to search: ";
                cin.ignore();
                gets(temp);
                while (!checkString(temp))
                {
                    cout << "\t Please Enter Valid Name to search: ";
                    gets(temp);
                }
                while (cur != NULL)
                {
                    if (cur->Tr.get_TrainName()==temp)
                    {
                        count++;
                        system("cls");
                        cur->Tr.display_Train();
                    }
                    cur = cur->link;
                }
                if (count == 0)
                {
                    cout << "\t No record found." << endl;
                    _getch();
                }
                break;
            }
            case '2':
            {
                count = 0;
                IDNo = Input_checkNO("Train_No to Search");
                while (cur != NULL)
                {
                    if (cur->Tr.get_TrainNo()== IDNo)
                    {
                        count++;
                        system("cls");
                        cur->Tr.display_Train();
                        break;
                    }
                    cur = cur->link;
                }
                if (count == 0)
                {
                	system("cls");
                    cout << "\t No record found." << endl;
                    _getch();
                    system("cls");
                    
                }
                break;
            }
            case '0':
                break;

            default:
                cout << "\t Invalid input try again " << endl;
                _getch();
                break;
            }

        } while (choice != '0');
    }
    
    bool Validate_train(long long int Train_n)
    {
        if (head == NULL)
        {
            return true;
        }
        Train_node *cur1 = head;
        while (cur1 != NULL)
        {
            if (cur1->Tr.get_TrainNo() == Train_n)
            {
                return false;
            }
            cur1 = cur1->link;
        }
        return true;
    }
    
    
    void updateTrain(int idno)
    {
    char source[20];
	char Destination[20];
	char Train_Name[20];
	char Arr_time[20];
	char Depurture_time[20];
	char Distance[20];
	long int Train_no;
	bool flag;
	int count= 0;
	int choice;
	
        cur = head;
        while (cur != NULL)
        {
            if (cur->Tr.get_TrainNo() == idno)
            {
                flag = true;
                count++;
                
                cur->Tr.display_Train();
                do
                {
                    cout << "\t\t\tChoose menue to update" << endl;
                    cout << "\t\t\t 1. Source" << endl;
                    cout << "\t\t\t 2. Destination" << endl;
                    cout << "\t\t\t 3. Train_name" << endl;
                    cout << "\t\t\t 4. Arr Time" << endl;
                    cout << "\t\t\t 5. Depurture Time" << endl;
                    cout << "\t\t\t 6. Distance" << endl;
                    cout << "\t\t\t 7. Train_no" << endl;
                    cout << "\t\t\t 8. Complete Train Data" << endl;
                    cout << "\t\t\t 0.exit menue" << endl;
                    cin.ignore();
                    cout << "\t\t\t Enter here";
                    choice = getche();
                    switch (choice)
                    {
                    case '1':
                    {
                        cout << "\t\t\t Please Enter New source ";
                        gets(source);
//                        while (!checkString(source))
//                        {
//                            cout << "\t\t\t Please Enter Valid New source ";
//                            gets(source);
//                        }
                        cur->Tr.set_TrainSource(source);
                        break;
                    }
                    case '2':
                    {
                    	cout << "\t\t\t Please Enter New Destination ";
                        gets(Destination);
//                        while (!checkString(Destination))
//                        {
//                            cout << "\t\t\t Please Enter Valid New source ";
//                            gets(Destination);
//                        }
                        cur->Tr.set_TrainDes(Destination);
                        break;
                    }
                    case '3':
                    {
                        cout << "\t\t\t Please Enter New Train name ";
//                        gets(Train_Name);
//                        while (!checkString(Train_Name))
//                        {
//                            cout << "\t\t\t Please Enter Valid New Train name ";
//                            gets(Train_Name);
//                        }
                        cur->Tr.set_TrainName(Train_Name);
                        break;
                    }
                    case '4':
                    {
                        cout << "\t\t\t Please Enter New Arr_time ";
                        gets(Arr_time);
//                        while (!checkString(Arr_time))
//                        {
//                            cout << "\t\t\t Please Enter Valid New Arr_time ";
//                            gets(Arr_time);
//                        }
                        cur->Tr.set_TrainArr_time(Arr_time);
                        break;
                    }
                    case '5':
                    {
                        cout << "\t\t\t Please Enter New Depurture_time ";
                        gets(Depurture_time);
//                        while (!checkString(Depurture_time))
//                        {
//                            cout << "\t\t\t Please Enter Valid New Depurture_time ";
//                            gets(Depurture_time);
//                        }
                        cur->Tr.set_TrainDepurture_time(Depurture_time);
                        break;
                    }
                    case '6':
                    {
                        cout << "\t\t\t Please Enter New Distance ";
                        gets(Distance);
//                        while (!checkString(Distance))
//                        {
//                            cout << "\t\t\t Please Enter Valid New Distance ";
//                            gets(Distance);
//                        }
                        cur->Tr.set_TrainDistance(Distance);
                        break;
                    }
                    case '7':
                    {
                        idno = Input_checkNO("Train_no #");
                        while (!Validate_train(idno))
                        {
                            cout << "\t\t\t Another Train is Book with same ID No." << endl;
                            idno = Input_checkNO("another ID #");
                        }

                        cur->Tr.set_TrainNo(idno);
                        break;
                    }
                    
                    case '8':
                    {
                        cout << "\t\t\t Please Enter new Record" << endl;
                        cur->Tr.set_Train();
                        break;
                    }
                    case '0':
                    {
                        break;
                    }
                    default:
                    {
                        cout << "\t\t\t Invalid input please try again" << endl;
                        break;
                    }
                        cout << "\t\t\t Train updated" << endl;
                        _getch();
                        
                        cout<<"New Train Data"<<endl;
                        
                        cur->Tr.display_Train();
                        cout << endl;
                        cout << "\t\t\t ";
                        system("PAUSE");
                        system("CLS");
                    }

                } while (choice != '0');
                return;
            }

            cur = cur->link;
        }
        if (flag == false)
        {
        	
            cout << "\t\t\t Record not found try again..";
            _getch();
            //updateTrain(idno);
        }
    }

    void DeleteFirstNode()
    {
        Train_node *temp;
        temp = head->link;
        free(head);
        head = NULL;
        head = temp;
        cout << "\t\t\tDeleted successfully" << endl;
    }

    void DeleteEndNode()
    {

        if (head->link == NULL)
        {
            free(head);
            head = NULL;
        }
        else
        {
            cur = head;
            while (cur->link->link != NULL)
            {
                cur = cur->link;
            }
            free(cur->link);
            cur->link = NULL;
            cout << "\t\t\tDeleted Successfully" << endl;
            _getch();
        }
    }
    
    void DeletebyID(int ID)
    {
        cur = head;
        bool flag = false;
        Train_node *prev = head;
        if (head == NULL)
        {
            cout << "\t\t\t There is no data " << endl;
            _getch();
            return;
        }
    //    head->Tk.display_Ticket();
        if (head->Tr.get_TrainNo()== ID)
        {
            DeleteFirstNode();
            cout << "\t\t\t Deleted succesfully" << endl;
            _getch();
            return;
        }
        while (cur->link != NULL)
        {
            cur = cur->link;
        }
        if (cur->Tr.get_TrainNo()== ID)
        {
            DeleteEndNode();
            cout << "\nDeleted succesfully" << endl;
            _getch();
            return;
        }
        cur = head;
        while (cur != NULL)
        {
            if (cur->Tr.get_TrainNo()== ID)
            {
                flag = true;
                prev->link = cur->link;
                free(cur);
                cur = NULL;
                cout << "\nDeleted succesfully" << endl;
                _getch();
                break;
                return;
            }
            prev = cur;
            cur = cur->link;
        }
        if (!flag)
        {
            cout << "No record matched" << endl;
            _getch();
            return;
        }
    }

    void List_train()
    {
        if (head == NULL)
        {
            cout << "\n\t\t\t No recode found" << endl;
            _getch();
            return;
        }
        cur = head;
        while (cur != NULL)
        {
            cur->Tr.display_Train();
            cur = cur->link;
        }
    }

    void writeTrainDatadata()
    {
        cur = head;
        ofstream fout("Train.bin", ios::binary);
        if (fout.is_open())
        {
            fout.clear();
            while (cur != NULL)
            {
                fout.write((char *)&(cur->Tr), sizeof(cur->Tr));
                cur = cur->link;
            }
            fout.close();
        }
        else
        {
            cout << "\t\t\t File Error!" << endl;
            cout << "\t\t\t File No found" << endl;
            return;
        }
    }

    void ReadTraindata()
    {
        Train_node *temp = NULL;
        head = NULL;
        ifstream fin("Train.bin", ios::binary);
        if (fin.is_open())
        {
            if (!Is_empty(fin))
            {
                head = new Train_node;
                fin.read((char *)&(head->Tr), sizeof((head->Tr)));
                head->link = NULL;
                cur = head;
            }
            while (!fin.eof())
            {
                if (head != NULL)
                {
                    if (!fin.eof())
                    {

                        next = new Train_node;
                        if (fin.read((char *)&(next->Tr), sizeof((next->Tr))))
                        {
                            cur->link = next;
                            next->link = NULL;
                            cur = next;
                            break;
                        }
                    }
                }
            }
            fin.close();
        }
        else
        {
            cout << "\t\t\t File Error!" << endl;
            cout << "\t\t\t File No found" << endl;
        }
    }
};









































class Ticket{
	private:
		int Tiket_no;
		char name[50];
		long long int cnic;
		long long int p_no;
		char gender[50];
		int age;
	public:
		Ticket(){
			strcpy(name,"None");
			cnic=0;
			p_no=0;
			strcpy(gender,"None");
			age=0;
			Tiket_no=0;
		}
	void set_Ticket(){
		cin.ignore();
//		cout<<"Enter Name : ";
//		gets(name);
        cout << "\t\t\t Please Enter Name ";
                        gets(name);
                        while (!checkString(name))
                        {
                            cout << "\t\t\t Please Enter Valid Name ";
                            gets(name);                  
                        }

		cnic=Input_checkNO("CNIC. ");
		while(cnic==0){
			cin.ignore();
			cnic=Input_checkNO("CNIC.  ");
		}
		
		p_no=Input_checkNO("Phone no. ");
		while(p_no==0){
			cin.ignore();
			p_no=Input_checkNO("Phone no.  ");
		}

		cout<<"Enter Gender : ";
		cin.ignore();
		gets(gender);
		cout<<"Age : ";
		cin>>age;
		Tiket_no=Input_checkNO("Ticket No. ");
		while(Tiket_no==0){
			cin.ignore();
			Tiket_no=Input_checkNO("Ticket No. ");
		}
	}
	void display_Ticket(){
		 cout << "\n\t\t\t****************************" << endl;
        cout << "\t\t\t       Ticket# " << Tiket_no << endl;
        cout << "\t\t\t****************************\n"
             << endl;
        cout << "\t\t\t Name :          " <<  name<< endl;
        cout << "\t\t\t CNIC #          " << cnic << endl;
        cout << "\t\t\t Gender :        " << gender << endl;
        cout << "\t\t\t Phone No :      " <<p_no<<endl;
        cout << "\t\t\t AGE :           "<<age<<endl;
        cout << "\n\t\t\t****************************" << endl;
	}
	void readFile(ifstream &fin)
    {
        fin.read((char *)this, sizeof(*this));
    }
  
  
    void writeFile(ofstream &fout)
    {
        fout.write((char *)this, sizeof(*this));
    }
	int get_TicketID() { return this->Tiket_no; }
	string get_Ticketname(){return this->name;}
	int get_TikcetCNIC(){return this->cnic;}
	int get_Ticket_P_no(){return this->p_no;}
	string get_TicketGender(){return this->gender;}
	int get_Ticket_Age(){return this->age;}
	
	
	void set_TicketID(char Tiket_no){(this->Tiket_no = Tiket_no);}
	void set_Ticketname(char name[50]){strcpy(this->name,name);}
	void set_TicketCNIC(char cnic){(this->cnic = cnic);}
	void set_Ticketp_no(char p_no){(this->p_no = p_no);}
	void set_Ticketgender(char gender[8]){strcpy(this->gender,gender);}
	void set_TicketAge(char age){(this->age = age);}
	
};
class Ticket_node{
public:
	Ticket Tk;
	Ticket_node *link;
    Ticket_node *head, *cur, *next;
    Ticket_node()
    {
        head = cur = next = link = NULL;
    }

    void insert_ticket()
    {

        if (head == NULL)
        {
            head = new Ticket_node;
            head->Tk.set_Ticket();
            head->link = NULL;
            cur = head;
            writeTicketDatadata();
            system("cls");
            cout<<"\n\nTicket Booked Successfully\n\n"<<endl;
            _getch();
            
        }
        else
        {
            InsertAtEnd();
            writeTicketDatadata();
        }
        
        system("cls");
        cout<<"\n\nTicket Booked Successfully\n\n"<<endl;
        _getch();     
    }
    void InsertAtEnd()
    {
        cur = head;
        while (cur->link != NULL)
        {

            cur = cur->link;
        }
        next = new Ticket_node;
        next->Tk.set_Ticket();
        cur->link = next;
        cur = next;
        next->link = NULL;
    }

    void SearchTikcet()
    {
        int count = 0;
        char choice;
        int IDNo;
        char temp[30];
        bool flag = false;

        if (head == NULL)
        {
            cout << "\t\t\t There is no any record" << endl;
            _getch();
            return;        
        }
        do
        {
            cur = head;
            cout << "\t Please choose menue to search " << endl;
            cout << "\t 1. Name " << endl;
            cout << "\t 2. CNIC " << endl;
            cout << "\t 0. Go back " << endl;
            cout << "\t Enter here :  " << endl;
            choice = getch();
            cout << endl;
            switch (choice)
            {
            case '1':
            {
                count = 0;
                cout << "\t Please Enter Name to search: ";
                cin.ignore();
                gets(temp);
                while (!checkString(temp))
                {
                    cout << "\t Please Enter Valid Name to search: ";
                    gets(temp);
                }
                while (cur != NULL)
                {
                    if (cur->Tk.get_Ticketname()==temp)
                    {
                        count++;
                        system("cls");
                        cur->Tk.display_Ticket();
                    }
                    cur = cur->link;
                }
                if (count == 0)
                {
                    cout << "\t No record found." << endl;
                    _getch();
                }
                break;
            }
            case '2':
            {
                count = 0;
                IDNo = Input_checkNO("ID No to Search");
                while (cur != NULL)
                {
                    if (cur->Tk.get_TikcetCNIC()== IDNo)
                    {
                        count++;
                        system("cls");
                        cur->Tk.display_Ticket();
                        break;
                    }
                    cur = cur->link;
                }
                if (count == 0)
                {
                    cout << "\t No record found." << endl;
                    _getch();
                }
                break;
            }
            case '0':
                break;

            default:
                cout << "\t Invalid input try again " << endl;
                _getch();
                break;
            }

        } while (choice != '0');
    }
    
    bool Validate_ticket(long long int CNIC)
    {
        if (head == NULL)
        {
            return true;
        }
        Ticket_node *cur1 = head;
        while (cur1 != NULL)
        {
            if (cur1->Tk.get_TikcetCNIC() == CNIC)
            {
                return false;
            }
            cur1 = cur1->link;
        }
        return true;
    }
    
    
    void updateTicket(int idno)
    {
        char choice;
        bool flag = false;
		char name[50];
		long long int cnic;
		long long int p_no;
		char gender[50];
		int age;
        cur = head;
        while (cur != NULL)
        {
            if (cur->Tk.get_TikcetCNIC() == idno)
            {
                flag = true;
                
                
                cur->Tk.display_Ticket();
                do
                {
                    cout << "\t\t\tChoose menue to update" << endl;
                    cout << "\t\t\t 1. Name" << endl;
                    cout << "\t\t\t 2. CNIC" << endl;
                    cout << "\t\t\t 3. Gender" << endl;
                    cout << "\t\t\t 4. Phone_Number" << endl;
                    cout << "\t\t\t 5. Age" << endl;
                    cout << "\t\t\t 6. Complete Ticket Data" << endl;
                    cout << "\t\t\t 0.exit menue" << endl;
                    cin.ignore();
                    cout << "\t\t\t Enter here";
                    choice = getche();
                    switch (choice)
                    {
                    case '1':
                    {
                        cout << "\t\t\t Please Enter New Name ";
                        gets(name);
                        while (!checkString(name))
                        {
                            cout << "\t\t\t Please Enter Valid New Name ";
                            gets(name);
                            
                        }
                        cur->Tk.set_Ticketname(name);
                        
                        system("cls");
                         cout << "\n\n\n\t\t\t *******Ticket updated*******" << endl;
                         _getch();
                        break;
                    }
                    case '2':
                    {
                        idno = Input_checkNO("CNIC #");
                        while (!Validate_ticket(idno))
                        {
                            cout << "\t\t\t Another Ticket is Book with same CNIC No." << endl;
                            idno = Input_checkNO("another CNIC #");
                        }

                        cur->Tk.set_TicketCNIC(idno);
                       system("cls");
                       cout << "\n\n\n\t\t\t *******Ticket updated*******" << endl;
                         _getch();
                        break;
                    }
                    case '3':
                    {

                        cout << "\t\t\t Please Enter New Gender ";
                        gets(gender);
                        while (!checkString(gender))
                        {
                            cout << "\t\t\t Please Enter Valid New Phone_Number ";
                            cin.ignore();
                            gets(gender);
                        }
                        cur->Tk.set_Ticketgender(gender);
                        system("cls");
                        cout << "\n\n\n\t\t\t *******Ticket updated*******" << endl;
                        _getch();
                        break;
                    }
                    case '4':
                    {
                        cout << "\t\t\t Please Enter New Phone_Number ";
                        cin>>p_no;
                        while (!check_number(p_no))
                        {
                            cout << "\t\t\t Please Enter Valid New Phone_Number ";
                            cin>>p_no;
                        }
                        cur->Tk.set_Ticketp_no(p_no);
                        system("cls");
                         cout << "\n\n\n\t\t\t *******Ticket updated*******" << endl;
                        _getch();
                        break;
                    }
                    case '5':
                    {
                        cout << "\t\t\t Please Enter New Age ";
                        cin>>age;
                        while (!check_number(age))
                        {
                            cout << "\t\t\t Please Enter Valid New Phone_Number ";
                            cin>>age;
                        }
                        cur->Tk.set_TicketAge(age);
                        system("cls");
                         cout << "\n\n\n\t\t\t *******Ticket updated*******" << endl;
                        _getch();
                        break;
                    }
                    case '6':
                    {
                        cout << "\t\t\t Please Enter new Record" << endl;
                        cur->Tk.set_Ticket();
                        system("cls");
                         cout << "\n\n\n\t\t\t *******Ticket updated*******" << endl;
                        _getch();
                        break;
                    }
                    case '0':
                    {
                        break;
                    }
                    default:
                    {
                        cout << "\t\t\t Invalid input please try again" << endl;
                        _getch();
                        break;
                    }
                        cout << "\t\t\t Ticket updated" << endl;
                        
                        cout<<"New Ticket Data"<<endl;
                        
                        cur->Tk.display_Ticket();
                        cout << endl;
                        cout << "\t\t\t ";
                        system("PAUSE");
                        system("CLS");
                    }

                } while (choice != '0');
                return;
            }

            cur = cur->link;
        }
        if (flag == false)
        {
            cout << "\t\t\t Record not found try again..";
            _getch();
            return;
          //  updateTicket(idno);
        }
    }

    void DeleteFirstNode()
    {
        Ticket_node *temp;
        temp = head->link;
        free(head);
        head = NULL;
        head = temp;
        cout << "\t\t\tDeleted successfully" << endl;
        return;
    }

    void DeleteEndNode()
    {

        if (head->link == NULL)
        {
            free(head);
            head = NULL;
        }
        else
        {
            cur = head;
            while (cur->link->link != NULL)
            {
                cur = cur->link;
            }
            free(cur->link);
            cur->link = NULL;
            cout << "\t\t\tDeleted Successfully" << endl;
            return;
        }
    }
    
    void DeletebyID(int ID)
    {
        cur = head;
        bool flag = false;
        Ticket_node *prev = head;
        if (head == NULL)
        {
            cout << "\t\t\t There is no data " << endl;
            _getch();
            return;
        }
    //    head->Tk.display_Ticket();
        if (head->Tk.get_TikcetCNIC()== ID)
        {
            DeleteFirstNode();
            cout << "\t\t\t Deleted succesfully" << endl;
            _getch();
            return;
            
        }
        while (cur->link != NULL)
        {
        	flag = true;
            cur = cur->link;
        }
        if (cur->Tk.get_TikcetCNIC()== ID)
        {
            DeleteEndNode();
            cout << "\nDeleted succesfully" << endl;
            _getch();
            return; 
            
        }
        cur = head;
        while (cur != NULL)
        {
            if (cur->Tk.get_TikcetCNIC()== ID)
            {
                flag = true;
                prev->link = cur->link;
                free(cur);
                cur = NULL;
              //  cout << "\nDeleted succesfully" << endl;
                _getch();
                break;
                
            }
            prev = cur;
            cur = cur->link;
        }
        if (!flag)
        {
            cout << "No record matched" << endl;
            _getch();
            return;
        }
    }

    void List_tickets()
    {
        if (head == NULL)
        {
            cout << "\n\t\t\t No recode found" << endl;
            return;
        }
        cur = head;
        while (cur != NULL)
        {
            cur->Tk.display_Ticket();
            cur = cur->link;
        }
    }

    void writeTicketDatadata()
    {
        cur = head;
        ofstream fout("Ticket.bin",ios::binary);
        if (fout.is_open())
        {
            fout.clear();
            while (cur != NULL)
            {
                fout.write((char *)&(cur->Tk), sizeof(cur->Tk));
                cur = cur->link;
            }
            fout.close();
        }
        else
        {
            cout << "\t\t\t File Error!" << endl;
            cout << "\t\t\t File No found" << endl;
        }
    }

    void ReadTicketdata()
    {
        Ticket_node *temp = NULL;
        head = NULL;
        ifstream fin("Ticket.bin", ios::binary);
        if (fin.is_open())
        {
            if (!Is_empty(fin))
            {
                head = new Ticket_node;
                fin.read((char *)&(head->Tk), sizeof((head->Tk)));
                head->link = NULL;
                cur = head;
            }
            while (!fin.eof())
            {
                if (head != NULL)
                {
                    if (!fin.eof())
                    {

                        next = new Ticket_node;
                        if (fin.read((char *)&(next->Tk), sizeof((next->Tk))))
                        {
                            cur->link = next;
                            next->link = NULL;
                            cur = next;
                            break;
                        }
                    }
                }
            }
            fin.close();
        }
        else
        {
            cout << "\t\t\t File Error!" << endl;
            cout << "\t\t\t File No found" << endl;
        }
    }
};

void Railway_database(Ticket Tk,Ticket_node t , Train Tr , Train_node Tn){
	int f=0;
	int n;
	int CNIC;
	while(f!=1){
				system("cls");
	cout<<"\t\t\t\t!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"<<endl;
	cout<<"\t\t\t\t||      Railway_DataBase      ||"<<endl;
	cout<<"\t\t\t\t!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"<<endl;
	cout<<endl;
	cout<<"\t\t\t1- ADD TRAIN"<<endl;
	cout<<"\t\t\t2- REMOVE TRAIN"<<endl;
	cout<<"\t\t\t3- UPDATE TRAIN"<<endl;
	cout<<"\t\t\t4- SHOW AVAILABLE TRAIN"<<endl;
	cout<<"\t\t\t5- Exit"<<endl;
		int ch=Input_checkNO("Choice ");
	switch(ch){
		case 1:
			system("cls");
			Tn.insert_train();
			Tn.writeTrainDatadata();
			system("cls");
			break;
			
		case 2:
            n=Input_checkNO("Train_no for Canceling the Train : ");
			Tn.DeletebyID(n);
			Tn.writeTrainDatadata();
			break;
		case 3:
		//	lib.ReadLibrarydata();
			system("cls");
			Tn.ReadTraindata();
			n=Input_checkNO("Train_no for Updating the Train : ");
			Tn.updateTrain(n);
			Tn.writeTrainDatadata();
			system("cls");
			_getch();
			break;
		case 4:
			system("cls");
			Tn.ReadTraindata();
			Tn.List_train();
			_getch();
			break;
		case 5:
			f=1;
		    Tn.writeTrainDatadata();
			break;
		default:
			cout<<"Invalid Choice !"<<endl;
			break;
	}
	}
}

void admin_menu(Ticket Tk,Ticket_node t ,  Train Tr , Train_node Tn){
	int f=0;
	int n;
	int CNIC;
	char ch;
	string pass ="";
	cout << "\nEnter password: ";
        ch = _getch();
        while(ch != 13){//character 13 is enter
        pass.push_back(ch);
        cout << '*';
        ch = _getch();
        }
        if(pass == "123"){
	
	while(f!=1){
		system("cls");
	    
				
	cout<<"\t\t\t\t!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"<<endl;
	cout<<"\t\t\t\t||         ADMIN_MENU         ||"<<endl;
	cout<<"\t\t\t\t!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"<<endl;
	cout<<endl;
	cout<<"\t\t\t1- BOOK TICKET"<<endl;
	cout<<"\t\t\t2- DISPLAY BOOKED TICKET"<<endl;
	cout<<"\t\t\t3- RAILWAY DATABASE"<<endl;
	cout<<"\t\t\t4- TRAIN ENQUIRY"<<endl;
	cout<<"\t\t\t5- CANCEL TICKET"<<endl;
	cout<<"\t\t\t6- SEARCH TICKET"<<endl;
	cout<<"\t\t\t7- EDIT TICEKT"<<endl;
	cout<<"\t\t\t8- Exit"<<endl;
	int ch=Input_checkNO("Choice ");
	switch(ch){
		case 1:
			
			t.insert_ticket();
			t.writeTicketDatadata();
			break;
		case 2:
	        t.ReadTicketdata();
		    system("cls");
			t.List_tickets();
			t.writeTicketDatadata();
			_getch();
		//	lib.writeLibraryDatadata();
			break;
		case 3:
		//	lib.ReadLibrarydata();
			Railway_database(Tk, t , Tr , Tn);
			_getch();
			break;
		case 4:
			system("cls");
			Tn.ReadTraindata();
			Tn.SearchTrain();
			system("cls");
			break;
		case 5:
	     	n=Input_checkNO("CNIC for Canceling the Ticket : ");
			t.DeletebyID(n);
			t.writeTicketDatadata();
			break;	
		case 6:
			system("cls");
			t.SearchTikcet();
			system("cls");
			break;
		case 7:
			system("cls");
			n=Input_checkNO("CNIC for Updating the Ticket Info: ");
			t.updateTicket(n);
			t.writeTicketDatadata();
			system("cls");
			break;
		case 8:
			t.writeTicketDatadata();
			f=1;
			break;
		default:
			cout<<"Invalid Choice !"<<endl;
			_getch();
			break;
	}
	}
}
else{
    	cout<<endl;
    	cout<<endl;
    	cout<<"\n\n                         ";
		for (int i=0;i<15;i++){
		Sleep(20);
	    cout<<"\xB2";
	    }
    	cout<<" Wrong Password ";
		for (int i=0;i<15;i++){
		Sleep(20);
	    cout<<"\xB2";	
	    }
	    _getch();
}
}

void user_menu(Ticket Tk,Ticket_node t , Train Tr , Train_node Tn){
	int f=0;
	int n;
	int CNIC;
	while(f!=1){
				system("cls");
	cout<<"\t\t\t\t!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"<<endl;
	cout<<"\t\t\t\t||         USER_MENU          ||"<<endl;
	cout<<"\t\t\t\t!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"<<endl;
	cout<<endl;
	cout<<"\t\t\t1- BOOK TICKET"<<endl;
	cout<<"\t\t\t2- TRAIN ENQUIRY"<<endl;
	cout<<"\t\t\t3- CANCEL TICKET"<<endl;
	cout<<"\t\t\t4- SEARCH TICKET"<<endl;
	cout<<"\t\t\t5- EDIT TICEKT"<<endl;
	cout<<"\t\t\t6- Exit"<<endl;
	int ch=Input_checkNO("Choice ");
	switch(ch){
		case 1:
			
			t.insert_ticket();
		//	t.writeTicketDatadata();
			break;
		case 2:
		//lib.ReadLibrarydata();
		    system("cls");
		    Tn.ReadTraindata();
			Tn.SearchTrain();
			system("cls");
			break;
		case 3:
			n=Input_checkNO("CNIC for Canceling the Ticket : ");
			t.DeletebyID(n);
			t.writeTicketDatadata();
			break;	
		case 4:
			system("cls");
			t.ReadTicketdata();
			t.SearchTikcet();
			system("cls");
			break;
		case 5:
			system("cls");
			n=Input_checkNO("CNIC for Updating the Ticket Info: ");
			t.updateTicket(n);
			system("cls");
			break;
		case 6:
			t.writeTicketDatadata();
			f=1;
			break;
		default:
			cout<<"Invalid Choice !"<<endl;
			_getch();
			break;
	}
	}
}


void login_menu(Ticket Tk,Ticket_node t ,Train Tr , Train_node Tn){
	int f=0;
	while(f!=1){
		system("cls");
		cout<<"\t\t\t\t!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"<<endl;
		cout<<"\t\t\t\t||          WELLCOME          ||"<<endl;
		cout<<"\t\t\t\t!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!"<<endl;
		cout<<endl;
		cout<<endl;
		cout<<"\t\t\t**************\t\t\t**************"<<endl;
		cout<<"\t\t\t  1- ADMIN    \t\t\t   2- USER    "<<endl;
		cout<<"\t\t\t**************\t\t\t**************"<<endl;
		cout<<"\t\t\t\t\t**************\t\t\t"<<endl;
		cout<<"\t\t\t\t\t  3- EXIT     "<<endl;
		cout<<"\t\t\t\t\t**************\t\t\t"<<endl;
		int ch=Input_checkNO("Choice ");
	switch(ch){
		case 1:
			admin_menu(Tk , t , Tr , Tn);
			break;
		case 2:
			user_menu(Tk,t , Tr , Tn);
			break;
		case 3:
			f=1;
			break;
		
		default:
			cout<<"\t\t\tInvalid Choice ! Enter Again.";
			_getch();
			break;
	}
	}
}

int main(){
	
//	welcome();
	Train Tr;
	Train_node Tn;
	Ticket Tk;
	Ticket_node t;

	t.ReadTicketdata();
	Tn.ReadTraindata();
	login_menu(Tk ,t , Tr , Tn);
	
	
    }
    
