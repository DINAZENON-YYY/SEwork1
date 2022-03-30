## 这是二级标题

#### 这是四级标题

https://www.acwing.com/about/

**加粗了**

1. 第一个列表
   1. 第一一个列表
2. 第二个列表
3. 第三个列表

![](https://i0.hdslb.com/bfs/album/424c4f01f203b739ea4b4bbdb8334d1381c51699.jpg@1036w.webp)

https://i0.hdslb.com/bfs/album/424c4f01f203b739ea4b4bbdb8334d1381c51699.jpg@1036w.webp

![](1.JPG)

```
#include<iostream>
#include<cstring>
#include<algorithm>

using namespace std;

const int N=3e4+10;

int n,t;
int p[N],dis[N],siz[N];

int findfa(int x)
{
    if(p[x]!=x)
    {
        int u=findfa(p[x]);
        dis[x]+=dis[p[x]];
        p[x]=u;
    }
    return p[x];
}

int main()
{
    scanf("%d",&t);
    for(int i=1;i<=30000;i++)
    {
        p[i]=i;
        dis[i]=0;
        siz[i]=1;
    }
    while(t--)
    {
        char c[2];
        int a,b;
        scanf("%s%d%d",c,&a,&b);
        if(c[0]=='M')
        {
            int fa=findfa(a),fb=findfa(b);
            if(fa!=fb)
            {
                dis[fa]=siz[fb];
                siz[fb]+=siz[fa];
                p[fa]=fb;
            }
        }
        else
        {
            int fa=findfa(a),fb=findfa(b);
            if(fa!=fb)
                puts("-1");
            else
            {
                if(a==b)
                    puts("0");
                else
                    printf("%d\n",abs(dis[a]-dis[b])-1);
            }
        }
    }
    return 0;
}
```

>blockquote


1. 数字列表1
2. 数字列表2
   
* 列表1
* 列表2
  
~~划线~~

**加粗**

Horizontal Rule

-----------

<table class="table table-bordered table-striped table-condensed">
    <tr>
        <td>北京</td>
	<td>雾霾</td>
    </tr>
    <tr>
        <td>深圳</td>
	<td>暴雨</td>
    </tr>
</table>