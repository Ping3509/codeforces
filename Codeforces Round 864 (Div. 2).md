Codeforces Round 864 (Div. 2)
https://codeforces.com/contest/1797/standings
#  A
```cpp
#include<bits/stdc++.h>
#define int long long
const int N=1e5+5,M=305;
using namespace std;
int n,m,x,y,xx,yy,sum1,sum2;
void solve()
{
	cin>>n>>m;sum1=4;sum2=4;
	cin>>x1>>y1>>x2>>y2;
	if(x1==1||x1==n)sum1--;
	if(y1==1||y1==m)sum1--;
	if(x2==1||x2==n)sum2--;
	if(y2==1||y2==m)sum2--;
//像这种都在边上的情况没有考虑到，没有用到min
	cout<<min(sum1,sum2)<<'\n';
}

int main(){
	int T;
	cin>>T;
	while(T--)
		solve();
	return 0;
}
```
# B
```cpp
#include <bits/stdc++.h>
#define int long long 
using namespace std;
const int INF=1e3+5;
int n,k,a[INF][INF],b[INF][INF];
void solve() {
	cin>>n>>k;
	for (int i=1;i<=n;i++)
		for (int j=1;j<=n;j++)
			cin>>a[i][j];
	for (int i=1;i<=n;i++)
		for (int j=1;j<=n;j++)
			b[n-j+1][n-i+1]=a[i][j];
	int res=0;
	for (int i=1;i<=n;i++)
		for (int j=1;j<=n;j++) {
			if (a[n-i+1][n-j+1]!=a[i][j]) {
				res++;
				a[n-i+1][n-j+1]=a[i][j];
			}
		}
	if (res>k || (res%2!=k%2 && n%2==0)) cout<<"NO\n";
	else cout<<"YES\n";
}
signed main()
{
	ios::sync_with_stdio(false);
	int t=0;cin>>t;
	while (t--) solve();
	return 0;
}
```