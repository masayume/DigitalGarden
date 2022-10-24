## TAGS:
- [#pico8](https://twitter.com/hashtag/pico8)
- [#tweetcart](https://twitter.com/hashtag/tweetcart)

## AUTHORS:
- [Paul Hammond](https://www.lexaloffle.com/bbs/?uid=33292)
- [2darray](https://www.lexaloffle.com/bbs/?uid=16330)
- [Niall Chandler](https://www.lexaloffle.com/bbs/?uid=46865)

## CODE EXAMPLES
- [magnify](https://twitter.com/SkyBerron/status/1581899124139786242)
```
function z(a,b)e=a-x
f=b-y
g=16-e*e-f*f
if(g>0)g/=32a+=g*e b+=g*f
return a*8,b*8end::_::a=t()*2%16a=min(a,16-a)b=a%4-2x=a+4y=b*b*2+4circfill(x*8,y*8,32,5)srand()for i=0,255do
a=i%16b=i\16e=rnd(2)\1*2-1c,d=z(a+max(e),b+max(-e))a,b=z(a,b)line(a,b,c,d,6+i%7)end?"\^1\^c1"
goto _
```

- [rotozoomer](https://twitter.com/SkyBerron/status/1581545882927104000)
```
pal({-4,-2,-5,-2,-6,-9},1)r=cos s=sin::_::cls()for i=0,127do
a=i%8*32+i\8%2*16-128b=i\8*24-160c=t()/8k=s(c)+1.6a,b=64+a*k*r(c)+b*k*s(c),64-a*k*s(c)+b*k*r(c)e=s(i/10+t()/8)for l=.5,1,.5do
line()for j=0,10do
c=k*l*(4+j%2*4)d=j/10-e
line(a+c*r(d),b+c*s(d),i)end
end
end
flip()goto _
```

- [telescope](https://twitter.com/btsherratt/status/1582032775867420672)
```
l=line
a=999s=sin
b=a/2r=rnd
function ★(x,y,o,p,c)u=(abs(s((z/p+o)%1))*4)\1v=u\3l(x-u,y,x+u,y,c)l(x,y-u,x,y+u,c)l(x-v,y-v,x+v,y+v,c)l(x+v,y-v,x-v,y+v,c)end::l::?"⁶1⁶c"
srand()z=t()u=z/40camera(s(u+u)^2*99,s(u)*99)for i=0,a do
x=r(a)-b y=r(a)-b ★(x,y,r()+2,r(5)+2,7)end
goto l
```

- [fans out of sync](https://twitter.com/SkyBerron/status/1580424525627371522)
```
::_::b=2^(t()*8\1%4)poke(24414,b|(b<<4))rectfill(0,0,127,127,0)for j=0,9do
for i=0,8do
k=(t()+i)%8x=8+min(k,8-k)+i*16-j%2*8y=8+j*12for r=1,3do
k=r/3+sin((t()/4+i+j)/8)line(x,y,x+7*cos(k),y+7*sin(k),15)end
end
end
pal({5,5,13,5,13,13,6,5,13,13,6,13,6,6,7},1)flip()goto _
```

- [cake 3D](https://twitter.com/2DArray/status/1581120428684111872)
```
::_::w=t()/8?"⁶1⁶c"
for j=0,1999do
y=j/999a=w+j*.618r=32c=cos(a)s=sin(a)p=6.7+(c+s)/2if(y>1)r*=y-1y=1p=7
circfill(64.5+c*r,84-y*24+s*r/2,2,p)end
for i=0,13do
for j=0,8do
a=w+j/9for k=0,1do
circ(64+k+cos(a)*26+i\9*sin(a*16-i/4),59+sin(a)*13-i,1,8+i\9+k)end
end
end
goto _
```

- [vortex](https://twitter.com/2DArray/status/1582499981256458240)
```
cls()?"\^!5f100█ˇ5●67"
::_::srand()w=t()/8o=w-.005for i=0,1100do
z=rnd()g=rnd()p=(z-w)%1q=(z-o)%1
a=g+1-(1-p)^4*8b=g+1-(1-q)^4*8r=p*p+.1x=r*cos(a)y=sin(a)*r+2u=r*cos(b)v=sin(b)*r+2c=180/y
d=180/v
if(r<1)line(64+x*c,c-30,64+u*d,d-30,rnd(8)*(1-p*p))end
flip()goto _
```

- [color spiral](https://twitter.com/SkyBerron/status/1583730187883016192)
```
n=20r=cos
s=sin::_::for j=2,4,.05do
m=t()/2+j/8a=r(m*.7)b=s(m)c=r(m)d=s(m)for i=0,n do
z=2*i/n-1k=i*.382l=(1-z*z)^.5x=l*r(k)y=l*s(k)
x,z=c*x-d*z,c*z+d*x
x,y=a*x-b*y,b*x+a*y+1.5k=j*n/y
x=k*x+64y=k*z+64poke(24414,17<<i%4)circfill(x,y,k/16,15)end
end?"\^1\^c"
pal({-4,-9,-7},1)goto _
```

- [swirls](https://twitter.com/SkyBerron/status/1582370900980080641)
```
h=64t=0::_::cls()t+=.005for j=1,16do
l=1+j/15for i=0,128do
k=i/128a=k+l*t
x=l*cos(a)y=l*sin(a)z=sin(k+t)k=h/(3+y)x=h+k*x
y=h+k*z
m=j%7+2if(i>0and i&m==m)line(u,v,x,y,1+j%15)
u=x
v=y
end
end
pal({3,-2,-5,-1,-6,-9,6},1)flip()goto _
```

- [rendering sphere]()
```
▒=rnd?"█\^!5f100█ˇ5●67█REDACTED"
█s=sqrt::█::█=▒(4)-2██=▒(4)-2███=2/██
c=6-mid(███,6)if(██<0)c=0
r=█s((█-1)^2+(███-.5)^2)if(██>0and r<1+▒(.2))c/=2
r=█s(█*█+██*██)if(r<1)c=3-█-██*2+█s(1-r*r)*2
pset(█*32+64,██*32+64,c+▒())goto █
```
