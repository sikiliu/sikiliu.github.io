---
layout:     post
title:      一个int的binary中1的num
category: blog
description: Algorithms
---
一、 Quick Func
----------------
int BitCount2(unsigned int n)
{
    unsigned int c =0 ;
    for (c =0; n; ++c)
    {
        n &= (n -1) ; // 清除最低位的1
    }
    return c ;
}
为什么呢？Assume 110011101 是我们需要count的binary,那么他减去1就是110011100,
(n)111110			110011101
(n-1)111101			110011100
上面两个栗子，当减1的时候是去消费最右侧最低1位非0的1的个数；

二、 建表法
----------------
1.如果它是偶数，那么n的二进制中1的个数与n/2中1的个数是相同的，比如4和2的二进制中都有一个1，6和3的二进制中都有两个1。为啥？因为n是由n/2左移一位而来，而移位并不会增加1的个数。

2.如果n是奇数，那么n的二进制中1的个数是n/2中1的个数+1，比如7的二进制中有三个1，7/2 = 3的二进制中有两个1。为啥？因为当n是奇数时，n相当于n/2左移一位再加1。
