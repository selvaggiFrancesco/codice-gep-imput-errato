{
#include <iostream>
#include <cstdlib>
#include <ctime>
#include <cmath>
#include <string>

#define LUNG 1000

using namespace std;

struct data
{
	short g;
	short m;
	short a;	
};

struct schedaCliente
{
	data ultrev;
	string nomeCognome;
	string targa;
	string telefono;
	int cil;
	int cav;
	
};

short inserimento = 0;

void inserisci(schedaCliente archivio[]);
void stampa(schedaCliente archivio[]);

int main()
{
	schedaCliente record[LUNG];
	int scelta;
	do
	{
		cout<<"1. inserisci scheda"<<endl<<"2. stampa archivio"<<endl<<"0. uscita"<<endl<<endl;
		cin>>scelta;
		switch(scelta)
		{
			case 1:
				
				inserisci(record);
				cout<<endl<<"scelta 1"<<endl;
				break;
		
		
		
			case 2:
				
				stampa(record);
				cout<<endl<<"scelta 2"<<endl;
				break;
		
		
			case 0:
				
				cout<<"grazie e arrivederci"<<endl<<endl;
				break;
				
				
				
			default:
				cout<<"comando non riconosciuto"<<endl;
				break;
		}
		
		
	}while(scelta != 0);
	
	
	system("pause");
	return 0;
}

void inserisci(schedaCliente archivio[])
{
	
	if(inserimento==LUNG)
	{
		return;
	}
	
	cout<<"inserisci cognome e nome "<<endl;
	cin>>archivio[inserimento].nomeCognome;
	
	cout<<"inserisci tel "<<endl;
	cin>>archivio[inserimento].telefono;
	
	cout<<"inserisci targa "<<endl;
	cin>>archivio[inserimento].targa;
	
	cout<<"inserisci data revisione giorno "<<endl;
	cin>>archivio[inserimento].ultrev.g;
	
	cout<<"inserisci data revisione mese "<<endl;
	cin>>archivio[inserimento].ultrev.m;
	
	cout<<"inserisci data revisione anno "<<endl;
	cin>>archivio[inserimento].ultrev.a;
	
	cout<<"inserisci cilindrata "<<endl;
	cin>>archivio[inserimento].cil;
	
	cout<<"inserisci cavalli "<<endl;
	cin>>archivio[inserimento].cav;
	
	inserimento++;
}

void stampa(schedaCliente archivio[])
{
	cout<<"cliente\ttelefono\ttarga\trevisione\tcilindrata\tcavalli"<<endl;
	for(int i=0;i<inserimento;i++)
	{
		cout<<archivio[i].nomeCognome<<"\t";
		cout<<archivio[i].telefono<<"\t";
		cout<<archivio[i].targa<<"\t";
		cout<<archivio[i].ultrev.g<<"/"<<archivio[i].ultrev.m<<"/"<<archivio[i].ultrev.a<<"\t";
		cout<<archivio[i].cil<<"\t";
		cout<<archivio[i].cav<<"\n";
		
	}
}
}
