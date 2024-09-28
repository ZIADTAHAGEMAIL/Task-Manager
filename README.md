# Task-Manager

#include <iostream>
#include<string>
#include<vector>
using namespace std;

int main()
{
    vector<string>vname, vhistory, vdeadline;
    vector<bool>Iscompleted;
    bool continue1 = 1;
    while (continue1) {
        cout << " ****** Welcome ****** \n";
        cout << " 1 Add Task \n";
        cout << " 2 Show Task \n";
        cout << " 3 Complete Task \n";
        cout << " 4 Delete Task \n";
        cout << " 5 Search about Task \n";
        cout << " 6 End Proggrame  \n";
        short choice = 1;
        cout << " Enter Your Choice \n";
        cin >> choice;
        if (choice == 1)
        {
            string name, history, deadline;
            cout << "Enter Name , History , Deadline \n";
            cin >> name >> history >> deadline;
            vname.push_back(name);
            vhistory.push_back(history);
            vdeadline.push_back(deadline);
            Iscompleted.push_back(false);
        }
        else if (choice == 2)
        {
            for (int i = 0; i < vname.size(); i++)
            {
                cout << " *** Task " << i + 1 << " Is *** \n";
                cout << " Task Name >> " << vname[i] << endl;
                cout << " Task History >> " << vhistory[i] << endl;
                cout << " Task deadline >> " << vdeadline[i] << endl;
                cout << endl;
            }
        }
        else if (choice == 3)
        {
          
            cout << " 1 You want to know Is any Task Is completed ? \n";
            cout << " 2 You complete  Task? \n";
            int q; cin >> q;
            string namee; 
            cout << " Enter Name of Task To Search \n";
            cin >> namee;
            if (q == 1)
            {
                for (int i=0;i<vname.size();i++)
                {
                    if (vname[i] == namee)
                    {
                        if(Iscompleted[i])
                        {
                            cout << "This Task Is Realy Completed \n";
                        }
                        else
                        {
                            cout << " This Task Is not Completed \n";
                        }
                    }
                }
            }
            else if (q == 2)
            {
                for (int i = 0; i < vname.size(); i++)
                {
                    if (vname[i] == namee)
                    {
                        Iscompleted[i] = true;
                      
                    }
                }
            }
        }
        else if (choice == 4)
        {
            string n;
            cout << " What is Name of Task That you want to  ! \n";
            cin >> n;
            bool IsFound1 = 0;
            int Index = 0;
            for (int i = 0; i < vname.size()-1; i++)
            {
                if (vname[i] == n)
                {
                    Index = i;
                    IsFound1 = true;
                    break;
                }
            }
            if (IsFound1)
            {
                for (int i = Index; i < vname.size() - 1; i++)
                {
                    swap(vname[i], vname[i + 1]);
                    swap(vhistory[i], vhistory[i + 1]);
                    swap(vdeadline[i], vdeadline[i + 1]);
                }
                vname.pop_back();
                vhistory.pop_back();
                vdeadline.pop_back();
            }
            else
            {
                vname.pop_back();
                vhistory.pop_back();
                vdeadline.pop_back();
            }
        }
        else if (choice == 5)
        {
            string n;
            cout << " What is Name of Task ! \n";
            cin >> n;
            bool IsFound1 = 0;
            for (int i = 0; i < vname.size(); i++)
            {
                if (vname[i] == n)
                {
                    IsFound1 = 1;
                 cout << " *** Num Of This Task On List IS " << i + 1 <<endl;
                 cout << " Task Name >> " << vname[i] << endl;
                 cout << " Task History >> " << vhistory[i] << endl;
                 cout << " Task deadline >> " << vdeadline[i] << endl;
                 cout << endl;
                }
            }
            if (!IsFound1)cout << "This Task Is Not Found \n";
        }
        else
        {
            cout << " ^^^ GOOD BUY ^^^ \n";
            continue1 = 0;
        }

    }
}

