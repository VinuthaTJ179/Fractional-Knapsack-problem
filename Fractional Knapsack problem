//Knapsack problem
#include <iostream>
using namespace std;
void decrease_sort(int n,int weight[],int value[]);
void strategy1(int n,int weight[],int value[],int capacity);
void increase_sort(int n,int weight[],int value[]);
void strategy2(int n,int weight[],int value[],int capacity);
void strategy3(int n,int weight[],int value[],int capacity);
void decrease_sort_strat3(int n,double ratio[],int weight[],int value[]);
int main()
{
    int n=0;
    cout<<"Enter the number of elements:"<<endl;
    cin>>n;
    int weight[n]={0},value[n]={0},capacity=0,i=0;
    cout<<"Enter the weights and its corresponding capacities:"<<endl;
    for(i=0;i<n;i++)
    {
        cout<<"Enter for weight["<<i+1<<"] & value["<<i+1<<"]:"<<endl;
        cin>>weight[i]>>value[i];
    }
    cout<<"Enter the capacity of the bag:"<<endl;
    cin>>capacity;
    cout<<"Strategy 1:"<<endl;
    strategy1(n,weight,value,capacity);
    cout<<"Strategy 2:"<<endl;
    strategy2(n,weight,value,capacity);
    cout<<"Strategy 3:"<<endl;
    strategy3(n,weight,value,capacity);
    return 0;
}
void strategy1(int n,int weight[],int value[],int capacity)
{
    //Arrange the profits in their decreasing order
    decrease_sort(n,weight,value);
    int i=0,j=0,rem_cap=capacity,sum_weight=0;
    double profit=0;
    while(rem_cap!=0)
    {
        if(rem_cap>=weight[i])
        {
            profit+=value[i];
            sum_weight+=weight[i];
            rem_cap-=weight[i];
            i++;
        }
        if(rem_cap<weight[i])
        {
            profit+=(value[i]*((double)(rem_cap)/weight[i]));
            sum_weight+=rem_cap;
            rem_cap=0;
        }
    }
    if(rem_cap==0)
    {
        cout<<"Profit:"<<profit<<" Weight:"<<sum_weight<<endl;
    }
    return;
}

void strategy2(int n,int weight[],int value[],int capacity)
{
    //Arrange the profits in their decreasing order
    increase_sort(n,weight,value);
    int i=0,j=0,rem_cap=capacity,sum_weight=0;
    double profit=0;
    while(rem_cap!=0)
    {
        if(rem_cap>=weight[i])
        {
            profit+=value[i];
            sum_weight+=weight[i];
            rem_cap-=weight[i];
            i++;
        }
        if(rem_cap<weight[i])
        {
            profit+=(value[i]*((double)(rem_cap)/weight[i]));
            sum_weight+=rem_cap;
            rem_cap=0;
        }
    }
    if(rem_cap==0)
    {
        cout<<"Profit:"<<profit<<" Weight:"<<sum_weight<<endl;
    }
    return;
}

void strategy3(int n,int weight[],int value[],int capacity)
{
    double ratio[n];
    for(int i=0;i<n;i++)
    {
        ratio[i]=(double)value[i]/weight[i];
    }
    decrease_sort_strat3(n,ratio,weight,value);
    int i=0,j=0,rem_cap=capacity,sum_weight=0;
    double profit=0;
    while(rem_cap!=0)
    {
        if(rem_cap>=weight[i])
        {
            profit+=value[i];
            sum_weight+=weight[i];
            rem_cap-=weight[i];
            i++;
        }
        if(rem_cap<weight[i])
        {
            profit+=(value[i]*((double)(rem_cap)/weight[i]));
            sum_weight+=rem_cap;
            rem_cap=0;
        }
    }
    if(rem_cap==0)
    {
        cout<<"Profit:"<<profit<<" Weight:"<<sum_weight<<endl;
    }
    return;
    return;
}
void decrease_sort_strat3(int n,double ratio[],int weight[],int value[])
{
    int i=0,j=0,temp1=0,temp2=0;
    double temp;
    for(i=0;i<n;i++)
    {
        for(j=i+1;j<n;j++)
        {
            if(ratio[j]>ratio[i])
            {
                temp=ratio[i];
                ratio[i]=ratio[j];
                ratio[j]=temp;
                temp1=weight[i];
                weight[i]=weight[j];
                weight[j]=temp1;
                temp2=value[i];
                value[i]=value[j];
                value[j]=temp2;
            }
        }
    }
    return;
}

void decrease_sort(int n,int weight[],int value[])
{
    int i=0,j=0,temp=0,temp1=0;
    for(i=0;i<n;i++)
    {
        for(j=i+1;j<n;j++)
        {
            if(value[j]>value[i])
            {
                temp=value[i];
                value[i]=value[j];
                value[j]=temp;
                temp1=weight[i];
                weight[i]=weight[j];
                weight[j]=temp1;
            }
        }
    }
    return;
}
void increase_sort(int n,int weight[],int value[])
{
    int i=0,j=0,temp=0,temp1=0;
    for(i=0;i<n;i++)
    {
        for(j=i+1;j<n;j++)
        {
            if(weight[i]>weight[j])
            {
                temp1=weight[i];
                weight[i]=weight[j];
                weight[j]=temp1;
                temp=value[i];
                value[i]=value[j];
                value[j]=temp;
            }
        }
    }
    return;
}
