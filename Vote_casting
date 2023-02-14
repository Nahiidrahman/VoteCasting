#include<stdio.h>
project()
{
    printf("\n\t****Welcome to The Project Of Polling Center for Vote Casting****\t\n");
}
Line_Distribution(int v,int c,int *L)
{

    int i,k;
    for(i=1; i<=c; i++)
    {
        L[i]=0;
    }
    if(v%c==0)
    {
        for(i=1; i<=c; i++)
        {
            L[i]=v/c;
        }
    }
    else
    {
        k=v%c;
        for(i=1; i<=c; i++)
        {
            L[i]=v/c;
        }
        for(i=1; i<=k; i++)
        {
            L[i]=L[i]+(k/k);
        }
    }
}
Line_Show(int c,int *L)
{
    int i;
    printf("\n");
    for(i=1; i<=c; i++)
    {
        printf("\t\t              %dth Line Have %d Voters\n",i,L[i]);
    }
    printf("\n\n");
}
int Time(int t)
{
    t=t*60;
    printf("\n\t       The voting will continue for %d minutes\n",t);
    return t;
}
Mark(int c)
{
    int i;
    for(i=1; i<=c; i++)
    {
        printf("\t\t\t     For Candidate-%d press %d: \n",i,i);

    }
    printf("\t\t\t       For no vote press %d: \n",c+1);
}
initial(int c,int *C)
{
    int i;
    for(i=1; i<=c+2; i++)
    {
        C[i]=0;
    }

}
Vote(int c,int v,int t,int *C)
{

    int mark,i,j,f=0,k,m=0,r;

    for(i=1; i<=v; i++)

    {

        printf("\n\t\t       %dth voter Enter your vote number: ",i);
        scanf("%d",&mark);
        for(j=1; j<=c; j++)
        {
            if(mark==j)
            {
                C[j]=C[j]+1;
                break;
            }
            else if(mark==c+1)
            {
                C[c+1]=C[c+1]+1; //No votes;
                break;
            }
            else if(mark<1 || mark>c+1)
            {
                C[c+2]= C[c+2]+1; //Spoil votes;
                break;
            }
        }
        f=f+1;
        if(f==c)
        {
            m=m+3;
            f=0;
        }
        if(m==t)
        {
            r=v-(i-1);
            printf("\n\tRemaining voters are %d\n",r);
            break;
        }
    }


}
Display(int j,int *C)
{
    int i;
    system("cls");
    for(i=1; i<=j; i++)
    {
        printf("\n\t\tCandidate-%d got %d Votes\n",i,C[i]);

    }
    printf("\n\t\tNo votes are %d\n",C[i]);
    printf("\n\t\tSpoil votes are %d\n",C[i+1]);
}
winner(int c, int *C)
{
    int i,x=-1,f=0,g=0;
    for(i=1; i<=c; i++)
    {
        if(C[i]>x)
        {
            x=C[i];
        }
    }
    for(i=1; i<=c; i++)
    {
        if(C[i]==x)
        {
            f++;
            g=i;
        }
    }
    if(f>1)
    {

        printf("\n\t\t\tIt's Draw\n");
    }
    else
    {

        printf("\n\t\t****The Winner Is Candidate-%d with %d Votes****\n",g,C[g]);
    }
}
int main()
{
    int error=0;
start1:

    if(error==0)
        project();
    else
    {
        printf("\n");
    }


    int i,j,k,c,l,v,time,end;


    printf("\n\t\t          Enter the number of Candidates: ");
    scanf("%d",&c);
    if(c==0)
    {
        printf("\n\t\t      Without Candidates Voting can't start\n");
        error++;

        goto start1;

    }
    else if(c<0)
    {
        printf("\n\t\t        Candidates Can't be Imaginary\n");
        error++;

        goto start1;
    }
    start2:
    printf("\n\t\t            Enter the number of Voters: ");
    scanf("%d",&v);
    if(v==0)
    {
        printf("\n\t\t      Without Voters Voting can't start\n");
        error++;

        goto start2;
    }
    else if(v<0)
    {
        printf("\n\t\t        Voters Can't be Imaginary\n");
        error++;

        goto start2;
    }
start3:
    printf("\n\t\t             Enter the time in hour: ");
    scanf("%d",&time);
    if(time==0)
    {
        printf("\n\t\t      Without Given time Voting can't start\n");
        error++;

        goto start3;
    }
    else if(time<0)
    {
        printf("\n\t\t        Time Can't be Imaginary\n");
        error++;
        goto start3;
    }

    int Line[c+1],Candidate[c+3]; //c+3 cause for spoil vote +1 and for no vote +1;//


    Line_Distribution(v,c,&Line);

    Line_Show(c,&Line);

    time=Time(time);

    Mark(c);

    initial(c,&Candidate);

    Vote(c,v,time,&Candidate);

    Display(c,&Candidate);

    winner(c,&Candidate);

    printf("\n\t\tIf you want to start another voting press 1 else any digit\n");
    scanf("%d",&end);

    if(end==1)
    {
        system("cls");
        printf("\t\t\t*****Starting New Voting Center*****\n");
        
        main();
    }
    else
    {
        printf("\t*****Thank You All,Have a Nice Day*****\n");
    }
    return 0;

}
