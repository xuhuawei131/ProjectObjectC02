# ProjectObjectC02

 /** 
 * void* 可以看作是char＊ 表示这个地址是一个字节的长度 因为char是最小的基本单位 一个字节
 
 ＊这样使用数组的时候 可以一个字节一个字节的移动游标
 **/
 
int memoryCopy(void* p1,void*p2,int num,int p2len){
    
    char* charp1=(char*)p1;
    
    char* charp2=(char*)p2;
    
    if(num>p2len){
    
        return 0;
    }else{
        for (int n=0; n<num; n++) {
        
            charp1[n]=charp2[n];
        }
        return num;
    }
    
    
}

int main(int argc, const char * argv[]) {
    
    int n=10;//生命一个int类型开辟4个字节大小  也可以理解为分配了4个 字符
    
    char strChar[]={'a','b','c'};
    
    char* testChar=strChar;
    
    testChar++;//移动一个字节 指针＋＋ 移动的是指针的类型的大小
    
    //如果指针是int＊ 那么移动4个字节  如果是char＊那么移动1个字节
    
    
    void* p=&n;//void* 是万能指针
    
    int* p1=(int*)p;//必须强制类型转换
    
    printf(" testChar:%c p1:%d\n",*testChar,*p1);
    
    
    int n1[]={2,3,4,6,89};
    
    int n2[100];
    
    memoryCopy(n1,n2,sizeof(n1),sizeof(n2));//5*4,100*4
    
    
    char c1[]="hello"; //字符素组或者字符串 结尾会自动添加一个0 是0  不是‘0’ 所以她的大小是6个字节
    
    char c2[100];
    
    memoryCopy(c1,c2,sizeof(c1),sizeof(c2));//6*1  100*1
    
    return 0;
}
