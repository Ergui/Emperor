#include <stdio.h>
#include <stdlib.h>

#include <windows.h>
#include <mmsystem.h>
#pragma comment(lib,"Winmm.lib")

int emperor()
{
    char emperorName[50]; //用来存放用户输入的皇帝名号
    int choice;
    int i;
    int count=5;//当前未打入冷宫嫔妃人数
    //姓名数组，最多容纳六个字符，每个字符串的长度为8个字符（英文）
    char names[MAX][20] = {"西  施","貂  蝉","王昭君","杨玉环","赵飞燕"};
    //级别数组，最多容纳5个字符，每个字符串的最大长度为8个字符（英文）
    char levelNames[5][10] = {"贵人","嫔妃","贵妃","皇贵妃","皇后"};
    //用来存放每个妃子的等级，与levelName联用，-1表示未启用
    int levels[MAX] = {1,2,0,0,0,-1};
    //用来存放每个妃子的好感度,-1表示未启用
    int loves[MAX] = {100,100,100,100,100,-1};

    //测试代码：查看当前嫔妃状态
    printf("测试：查看当前嫔妃状态\n");
    printf(" 姓名\t级别\t好感度\n");
    for(i=0;i<count;i++)
    {
        printf("%s\t%s\t%d\n",names[i],levelNames[levels[i]],loves[i]);
    }

    printf("当今登基皇帝名号；");
    scanf("%s",emperorName);//输入字符串，不需要&符号
    printf("皇帝《%s》驾到,有事早奏，无事退朝！\n",emperorName);
    printf("1.皇帝下旨选妃；\t（新增功能）\n");
    printf("2.翻牌宠幸；\t\t（修改状态功能）\n");
    printf("3.打入冷宫；\t\t（删除功能）\n");
    printf("4.单独召见去小树林；\n");
    printf("******************\n");
    printf("陛下请选择；");

    scanf("%d",&choice);
    switch(choice)
    {
    case 1://皇帝下旨选妃；\t（新增功能）
        //1.增加数组元素（names,loves,levels)
        //2.判断是否还有空间增加数组元素
        if(count<MAX)//如果当前妃子少于系统最大
        {
            //执行操作
            printf("请输入娘娘的名讳：\n");
            scanf("%s",names[count]);
            //将count个元素初始化
            levels[count]=0;//级别为0
            loves[count]=100;//好感度为100
            count++;//添加人数，计数器增加1



        }else{

            printf("陛下，要注意龙体，后宫已经人满为患！\n添加失败\n");
        }

        break;
    case 2:
        printf("2.翻牌宠幸；\t\t（修改状态功能）\n");
        break;
    case 3:
        printf("3.打入冷宫；\t\t（删除功能）\n");
        break;
    case 4:
        printf("4.单独召见去小树林；\n");
        break;
    default:
        printf("君无戏言，请陛下再次确认！");
    }


    printf("测试：查看当前嫔妃状态\n");
    printf(" 姓名\t级别\t好感度\n");
    for(i=0;i<count;i++)
    {
        printf("%s\t%s\t%d\n",names[i],levelNames[levels[i]],loves[i]);
    }


    //播放音乐
    PlaySound(TEXT("sounds\\选妃.wav"),
              NULL,SND_FILENAME | SND_ASYNC | SND_LOOP);




return 0;
}
























int main()
{
emperor();

return 0;
}
