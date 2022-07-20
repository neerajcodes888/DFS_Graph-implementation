# DFS_Graph-implementation
#include<iostream>
using namespace std;
 int graph[8][8],visited[88],n,a[8];
 static int k=0,count=0;
 void DFS(int vertex);
 int main()
{
    cout<<"Enter no. of vertices:";
    cin>>n;
    for(int i=0;i<n;i++)
    {
        for(int j=0;j<n;j++)
        {
            cin>>graph[i][j];
        }
    }
    for(int i=0;i<n;i++)
    {
        visited[i]=0;
    }
    DFS(0);
}
void DFS(int vertex)
{
    count++;
    cout<<vertex<<" ";
    visited[vertex]=1;
    
    int c=0;
    for(int i=0;i<n;i++)
    {
        if(!visited[i]&&graph[vertex][i]==1)
        {
          a[++k]=i;
          c=1;
        }
        if(count==n)
        {
            exit(0);
        }
    }
    if(c==1)
    {
        DFS(a[k]);
    }
    else{
        k--;
        DFS(a[k]);
    }
}
