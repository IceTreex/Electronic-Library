#include<iostream>
#include<winbgim.h>
#include<string.h>
using namespace std;
class Book_entry
{
public:
    string bookname;
    int bookid;
    string writer;
    Book_entry()
    {}
    Book_entry(const Book_entry &b_e)
    {
        bookname = b_e.bookname;
        writer = b_e.writer;
        bookid = b_e.bookid;
    }
    ~Book_entry() {}
    void bookin()
    {
        cin>>bookname;
        cin>>bookid;
        cin>>writer;
    }
    void setbook(string bn,int bi,string wr)
    {
        bookname = bn;
        bookid = bi;
        writer = wr;
    }
    void bookinprint()
    {
        cout<<"书名："<<bookname<<"   "<<"书号："<<bookid<<"   "<<"作者："<<writer<<endl;
    }
};
class Student
{
public:
    int stuid;
    string stuname;
    Book_entry B;
    Student() {}
    Student(const Student & s):B(s.B)
    {
        stuid = s.stuid;
        stuname = s.stuname;
    }
    void setdata()
    {
        cin>>stuid;
        cin>>stuname;
        //B.bookin();
    }
    void setstu(int si,string sn)
    {
        stuid = si;
        stuname = sn;
    }
    void setdataprint()
    {
        cout<<"姓名："<<stuname<<"   "<<"学号："<<stuid<<"   ";
    }
};
int main()
{
    initwindow(750,750,"ELECTRONIC LIBRARY");
    setbkcolor(COLOR(255,228,196));
    cleardevice();
    setfillstyle(1,COLOR(240,248,255));
    fillellipse(375,375,200,200);
    settextstyle(8,0,16);
    outtextxy(285,250,"Welcome");
    outtextxy(350,325,"To");
    outtextxy(250,400,"Electronic");
    outtextxy(285,475,"Library");
    delay(3000);
g_b:
    cleardevice();
    setfillstyle(1,COLOR(230,230,250));
    bar3d(200,100,350,175,25,3);
    bar3d(400,100,550,175,25,3);
    bar3d(200,225,550,300,25,3);
    bar3d(200,350,550,425,25,3);
    bar3d(200,475,550,550,25,3);
    bar3d(200,600,550,675,25,3);
    settextstyle(8,0,16);
    outtextxy(225,117,"借书");
    outtextxy(425,117,"还书");
    outtextxy(225,242,"图书信息管理");
    outtextxy(225,367,"图书信息查询");
    outtextxy(225,492,"图书会员注册");
    outtextxy(225,617,"图书信息统计");
    Student stu[100];
    stu[0].setstu(301,"小明");
    stu[1].setstu(302,"小光");
    stu[2].setstu(303,"小白");
    Book_entry book[100];
    book[0].setbook("三国演义",01,"罗贯中");
    book[1].setbook("水浒传",02,"施耐庵");
    book[2].setbook("西游记",03,"吴承恩");
    book[3].setbook("红楼梦",04,"曹雪芹");
    book[4].setbook("狼王梦",05,"沈石溪");
    int a,b,c,d,e,f;
    int s0b0 = 0,s1b0 = 0,s2b0 = 0;
    int s0b1 = 0,s1b1 = 0,s2b1 = 0;
    int s0b2 = 0,s1b2 = 0,s2b2 = 0;
    int s0b3 = 0,s1b3 = 0,s2b3 = 0;
    int s0b4 = 0,s1b4 = 0,s2b4 = 0;
    while(1)
    {
        if(ismouseclick(WM_LBUTTONDOWN))
        {
            getmouseclick(WM_LBUTTONDOWN,a,b);
            clearmouseclick(WM_LBUTTONDOWN);
            if(a >= 200 && a <= 350 && b >= 100 && b <= 175)//借书
            {
                int si;
                cout<<"请输入你的学号"<<endl;
                cin>>si;
                if(si == 301)
                {
                    cout<<"登录成功！"<<endl;
                    cout<<"请选择您想借阅的图书："<<endl;
                }
                else if(si == 302)
                {
                    cout<<"登录成功！"<<endl;
                    cout<<"请选择您想借阅的图书："<<endl;
                }
                else if(si == 303)
                {
                    cout<<"登录成功！"<<endl;
                    cout<<"请选择您想借阅的图书："<<endl;
                }
                else
                {
                    cout<<"账户名错误"<<endl;
                }
                cleardevice();
                setfillstyle(1,COLOR(230,230,250));
                bar3d(200,100,550,175,25,3);
                bar3d(200,225,550,300,25,3);
                bar3d(200,350,550,425,25,3);
                bar3d(200,475,550,550,25,3);
                bar3d(200,600,550,675,25,3);
                setfillstyle(1,COLOR(240,248,255));
                fillellipse(100,60,75,35);
                settextstyle(8,0,16);
                outtextxy(275,117,"三国演义");
                outtextxy(295,242,"水浒传");
                outtextxy(295,367,"西游记");
                outtextxy(295,492,"红楼梦");
                outtextxy(295,617,"狼王梦");
                settextstyle(8,0,15);
                outtextxy(60,45,"返回");
                while(1)
                {
                    if(ismouseclick(WM_LBUTTONDOWN))
                    {
                        getmouseclick(WM_LBUTTONDOWN,c,d);
                        clearmouseclick(WM_LBUTTONDOWN);
                        if(c >= 25 && c <= 175 && d >= 25 && d <= 95)
                        {
                            goto g_b;
                        }
                        if(c >= 200 && c <= 550 && d >= 100 && d <= 175)//三国演义
                        {
                                if(si == 301)
                                {
                                    s0b0 = 1;
                                    stu[0].setdataprint();
                                    book[0].bookinprint();
                                    cout<<"借书成功！"<<endl;
                                }
                                else if(si == 302)
                                {
                                    s1b0 = 1;
                                    stu[1].setdataprint();
                                    book[0].bookinprint();
                                    cout<<"借书成功！"<<endl;
                                }
                                else if(si == 303)
                                {
                                    s2b0 = 1;
                                    stu[2].setdataprint();
                                    book[0].bookinprint();
                                    cout<<"借书成功！"<<endl;
                                }
                        }
                        if(c >= 200 && c <= 550 && d >= 225 && d <= 300)//水浒传
                        {
                            if(si == 301)
                            {
                                s0b1 = 1;
                                stu[0].setdataprint();
                                book[1].bookinprint();
                                cout<<"借书成功！"<<endl;
                            }
                            else if(si == 302)
                            {
                                s1b1 = 1;
                                stu[1].setdataprint();
                                book[1].bookinprint();
                                cout<<"借书成功！"<<endl;
                            }
                            else if(si == 303)
                            {
                                s2b1 = 1;
                                stu[2].setdataprint();
                                book[1].bookinprint();
                                cout<<"借书成功！"<<endl;
                            }
                        }
                        if(c >= 200 && c <= 550 && d >= 350 && d <= 425)//西游记
                        {
                            if(si == 301)
                            {
                                s0b2 = 1;
                                stu[0].setdataprint();
                                book[2].bookinprint();
                                cout<<"借书成功！"<<endl;
                            }
                            else if(si == 302)
                            {
                                s1b2 = 1;
                                stu[1].setdataprint();
                                book[2].bookinprint();
                                cout<<"借书成功！"<<endl;
                            }
                            else if(si == 303)
                            {
                                s2b2 = 1;
                                stu[2].setdataprint();
                                book[2].bookinprint();
                                cout<<"借书成功！"<<endl;
                            }
                        }
                        if(c >= 200 && c <= 550 && d >= 475 && d <= 550)//红楼梦
                        {
                            if(si == 301)
                            {
                                s0b3 = 1;
                                stu[0].setdataprint();
                                book[3].bookinprint();
                                cout<<"借书成功！"<<endl;
                            }
                            else if(si == 302)
                            {
                                s1b3 = 1;
                                stu[1].setdataprint();
                                book[3].bookinprint();
                                cout<<"借书成功！"<<endl;
                            }
                            else if(si == 303)
                            {
                                s2b3 = 1;
                                stu[2].setdataprint();
                                book[3].bookinprint();
                                cout<<"借书成功！"<<endl;
                            }
                        }
                        if(c >= 200 && c <= 550 && d >= 600 && d <= 675)//狼王梦
                        {
                            if(si == 301)
                            {
                                s0b4 = 1;
                                stu[0].setdataprint();
                                book[4].bookinprint();
                                cout<<"借书成功！"<<endl;
                            }
                            else if(si == 302)
                            {
                                s1b4 = 1;
                                stu[1].setdataprint();
                                book[4].bookinprint();
                                cout<<"借书成功！"<<endl;
                            }
                            else if(si == 303)
                            {
                                s2b4 = 1;
                                stu[2].setdataprint();
                                book[4].bookinprint();
                                cout<<"借书成功！"<<endl;
                            }
                        }
                    }
                }
            }
            if(a >= 400 && a <= 550 && b >= 100 && b <= 175)//还书
            {
                int sir;
                cout<<"请输入你的学号:"<<endl;
                cin>>sir;
                if(sir == 301)
                {
                    cout<<"登录成功！"<<endl;
                    cout<<"请选择您想归还的图书："<<endl;
                }
                else if(sir == 302)
                {
                    cout<<"登录成功！"<<endl;
                    cout<<"请选择您想归还的图书："<<endl;
                }
                else if(sir == 303)
                {
                    cout<<"登录成功！"<<endl;
                    cout<<"请选择您想归还的图书："<<endl;
                }
                else
                {
                    cout<<"账户名错误"<<endl;
                }
                cleardevice();
                setfillstyle(1,COLOR(230,230,250));
                bar3d(200,100,550,175,25,3);
                bar3d(200,225,550,300,25,3);
                bar3d(200,350,550,425,25,3);
                bar3d(200,475,550,550,25,3);
                bar3d(200,600,550,675,25,3);
                setfillstyle(1,COLOR(240,248,255));
                fillellipse(100,60,75,35);
                settextstyle(8,0,16);
                outtextxy(275,117,"三国演义");
                outtextxy(295,242,"水浒传");
                outtextxy(295,367,"西游记");
                outtextxy(295,492,"红楼梦");
                outtextxy(295,617,"狼王梦");
                settextstyle(8,0,15);
                outtextxy(60,45,"返回");
                while(1)
                {
                    if(ismouseclick(WM_LBUTTONDOWN))
                    {
                        getmouseclick(WM_LBUTTONDOWN,c,d);
                        clearmouseclick(WM_LBUTTONDOWN);
                        if(c >= 25 && c <= 175 && d >= 25 && d <= 95)
                        {
                            goto g_b;
                        }
                        if(c >= 200 && c <= 550 && d >= 100 && d <= 175)//三国演义
                        {
                                if(sir == 301)
                                {
                                    s0b0 = 0;
                                    stu[0].setdataprint();
                                    book[0].bookinprint();
                                    cout<<"还书成功！"<<endl;
                                }
                                else if(sir == 302)
                                {
                                    s1b0 = 0;
                                    stu[1].setdataprint();
                                    book[0].bookinprint();
                                    cout<<"还书成功！"<<endl;
                                }
                                else if(sir == 303)
                                {
                                    s2b0 = 0;
                                    stu[2].setdataprint();
                                    book[0].bookinprint();
                                    cout<<"还书成功！"<<endl;
                                }
                        }
                        if(c >= 200 && c <= 550 && d >= 225 && d <= 300)//水浒传
                        {
                            if(sir == 301)
                            {
                                s0b1 = 0;
                                stu[0].setdataprint();
                                book[1].bookinprint();
                                cout<<"还书成功！"<<endl;
                            }
                            else if(sir == 302)
                            {
                                s1b1 = 0;
                                stu[1].setdataprint();
                                book[1].bookinprint();
                                cout<<"还书成功！"<<endl;
                            }
                            else if(sir == 303)
                            {
                                s2b1 = 0;
                                stu[2].setdataprint();
                                book[1].bookinprint();
                                cout<<"还书成功！"<<endl;
                            }
                        }
                        if(c >= 200 && c <= 550 && d >= 350 && d <= 425)//西游记
                        {
                            if(sir == 301)
                            {
                                s0b2 = 0;
                                stu[0].setdataprint();
                                book[2].bookinprint();
                                cout<<"还书成功！"<<endl;
                            }
                            else if(sir == 302)
                            {
                                s1b2 = 0;
                                stu[1].setdataprint();
                                book[2].bookinprint();
                                cout<<"还书成功！"<<endl;
                            }
                            else if(sir == 303)
                            {
                                s2b2 = 0;
                                stu[2].setdataprint();
                                book[2].bookinprint();
                                cout<<"还书成功！"<<endl;
                            }
                        }
                        if(c >= 200 && c <= 550 && d >= 475 && d <= 550)//红楼梦
                        {
                            if(sir == 301)
                            {
                                s0b3 = 0;
                                stu[0].setdataprint();
                                book[3].bookinprint();
                                cout<<"还书成功！"<<endl;
                            }
                            else if(sir == 302)
                            {
                                s1b3 = 0;
                                stu[1].setdataprint();
                                book[3].bookinprint();
                                cout<<"还书成功！"<<endl;
                            }
                            else if(sir == 303)
                            {
                                s2b3 = 0;
                                stu[2].setdataprint();
                                book[3].bookinprint();
                                cout<<"还书成功！"<<endl;
                            }
                        }
                        if(c >= 200 && c <= 550 && d >= 600 && d <= 675)//狼王梦
                        {
                            if(sir == 301)
                            {
                                s0b4 = 0;
                                stu[0].setdataprint();
                                book[4].bookinprint();
                                cout<<"还书成功！"<<endl;
                            }
                            else if(sir == 302)
                            {
                                s1b4 = 0;
                                stu[1].setdataprint();
                                book[4].bookinprint();
                                cout<<"还书成功！"<<endl;
                            }
                            else if(sir == 303)
                            {
                                s2b4 = 0;
                                stu[2].setdataprint();
                                book[4].bookinprint();
                                cout<<"还书成功！"<<endl;
                            }
                        }
                    }
                }
            }
            if(a >= 200 && a <= 550 && b >= 225 && b <= 300)//图书信息管理
            {
                cleardevice();
                setfillstyle(1,COLOR(230,230,250));
                bar3d(200,200,550,275,25,3);
                bar3d(200,350,550,425,25,3);
                outtextxy(225,217,"图书信息录入");
                outtextxy(225,367,"图书信息删除");
                while(1)
                {
                    if(ismouseclick(WM_LBUTTONDOWN))
                    {
                        getmouseclick(WM_LBUTTONDOWN,c,d);
                        clearmouseclick(WM_LBUTTONDOWN);
                        if(c >= 200 && c <= 550 && d >= 200 && d <= 275)//图书信息录入
                        {
                            int num;
                            cout<<"请输入你要录入的书籍数量："<<endl;
                            cin>>num;
                            Book_entry be[num];
                            int i;
                            for(i = 0;i < num;i ++)
                            {
                                be[i].bookin();
                            }
                            for(i = 0;i < num;i ++)
                            {
                                be[i].bookinprint();
                            }
                        }
                        if(c >= 200 && c <= 550 && d >= 350 && d <= 425)//图书信息删除
                        {
                            cout<<"sc";
                        }
                    }
                }
            }
            if(a >= 200 && a <= 550 && b >= 350 && b <= 425)//图书信息查询
            {
                int fbi;
                int m;
                cout<<"请输入你要查找的书籍编号："<<endl;
                cin>>fbi;
                for(m = 0; m < 5; m ++)
                {
                    if(fbi == book[m].bookid)
                    {
                        cout<<"您要查找的"<< fbi <<"号图书信息如下:"<<endl;
                        book[m].bookinprint();
                    }
                }
            }
            if(a >= 200 && a <= 550 && b >= 475 && b <= 550)//图书会员注册
            {
                cout<<"请输入你的学号姓名："<<endl;
                stu[4].setdata();
                cout<<"图书会员注册成功！"<<endl;
                stu[4].setdataprint();
            }
            if(a >= 200 && a <= 550 && b >= 600 && b <= 675)//图书信息统计
            {
                int sum,sy;
                sum = s0b0+s1b0+s2b0+s0b1+s1b1+s2b1+s0b2+s1b2+s2b2+s0b3+s1b3+s2b3+s0b4+s1b4+s2b4;
                sy = 15-sum;
                cout<<"图书库存剩余"<<sy<<"本"<<endl;
                cout<<"已借出图书"<<sum<<"本"<<endl;
            }
        }
    }

    return 0;
}

