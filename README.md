# A small C program to print the biggest prime number
Here it is (448 bytes):
'''
int m=1811939329,N=1,t[1<<26]={2},a,*p,i,e=73421233,s,c,U=1;g(d,h){for(i=s;i<1<<
25;i*=2)d=d*1LL*d%m;for(p=t;p<t+N;p+=s)for(i=s,c=1;i;i--)a=p[s]*(h?c:1LL)%m,p[s]
=(m*1U+*p-a)*(h?1LL:c)%m,*p=(a*1U+*p)%m,p++,c=c*1LL*d%m;}main(){while(e/=2){N*=2
;U=U*1LL*(m+1)/2%m;for(s=N;s/=2;)g(136,0);for(p=t;p<t+N;p++)*p=*p*1LL**p%m*U%m;
for(s=1;s<N;s*=2)g(839354248,1);for(a=0,p=t;p<t+N;)a+=*p<<(e&1),*p++=a%10,a/=10;
}while(!*--p);for(t[0]--;p>=t;)putchar(48+*p--);}
'''
This program computes 274207281-1, which was the biggest known prime number in 2016 (about 23 million digits !). For more information about how it was found and who found it, look at the GIMPS Project .

I compiled it successfully with gcc with Linux. In order to compile it, your C compiler must support the 64 bit long long type.

In order to have a small and yet asymptotically efficient code, I decided to do the computation of 2N-1 directly in base 10. The power involves repeated squarings and multiplications by two. The squarings are implemented by doing fast convolutions using a Number Theoretic Transform.

A previous version of this program to compute 26972593-1 won the International Obfuscated C Code Contest of Year 2000.

Thanks to Marco Cecchi who suggested some syntactic changes to save a few characters.

This program is Freeware.