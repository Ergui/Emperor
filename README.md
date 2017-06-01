#include <stdio.h>
#include <stdlib.h>

#include <windows.h>
#include <mmsystem.h>
#pragma comment(lib,"Winmm.lib")

int emperor()
{
    char emperorName[50]; //用来存放用户输入的皇帝名号
    int choice;
    //姓名数组，最多容纳六个字符，每个字符串的长度为8个字符（英文）
    char names[6][8] = {"西施","貂蝉","王昭君","杨玉环","赵飞燕"};
    //级别数组，最多容纳5个字符，每个字符串的最大长度为8个字符（英文）
    char levelNames[5][8] = {"贵人","嫔妃","贵妃","皇贵妃","皇后"};
    //用来存放每个妃子的等级，与levelName联用，-1表示未启用
    int level[] = {0,0,0,0,0,-1};
    //用来存放每个妃子的好感度,-1表示未启用
    int loves[] = {100,100,100,100,100,-1};
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
    case 1:
        printf("1.皇帝下旨选妃；\t（新增功能）\n");
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
