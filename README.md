# CSharp-RandomExtension
A light weight C# extension of random method for all numeric type.

## Language and Framework
C# .NET 4.5 above

## How to Use
### Install
Chose one in the following:
- Search nuget for "RandomExtension"
- Run the following command in the Package Manager Console:
```
PM> Install-Package RandomExtension
```
- Download RandomExtension.dll and add referance to project.
- Download RandomExtension.cs file and add it into project.(C# 6 above)

### NameSpace
```C#
using System.RandomExtension;
```

### Use Extension
All extension method can be use like default method of System.Random, for example:
```C#
Random rnd = new Random();
int randomInt = rnd.Next();
ulong randomULong = rnd.NextULong();
sbyte randomSByte = rnd.NextSByte(50);
decimal randomDecimal = rnd.NextDecimal(-3.5m, 8.55m);
```
For more detail, see document in ***Document of All Method*** section below.

### List of Extension Method of System.Random
- [public double NextDouble(double minValue, double maxValue)](#nextdoubledouble-double)
- [public float NextFloat()](#nextfloat)
- [public float NextFloat(float minValue, float maxValue)](#nextfloatfloat-float)
- [public decimal NextDecimal()](#nextdecimal)
- [public decimal NextDecimal(decimal minValue, decimal maxValue)](#nextdecimaldecimal-decimal)
- [public byte NextByte()](#nextbyte)
- [public byte NextByte(byte maxValue)](#nextbytebyte)
- [public byte NextByte(byte minValue, byte maxValue)](#nextbytebyte-byte)
- [public sbyte NextSByte()](#nextsbyte)
- [public sbyte NextSByte(sbyte maxValue)](#nextsbytesbyte)
- [public sbyte NextSByte(sbyte minValue, sbyte maxValue)](#nextsbytesbyte-sbyte)
- [public short NextShort()](#nextshort)
- [public short NextShort(short maxValue)](#nextshortshort)
- [public short NextShort(short minValue, short maxValue)](#nextshortshort-short)
- [public ushort NextUShort()](#nextushort)
- [public ushort NextUShort(ushort maxValue)](#nextushortushort)
- [public ushort NextUShort(ushort minValue, ushort maxValue)](#nextushortushort-ushort)
- [public uint NextUInt()](#nextuint)
- [public uint NextUInt(uint maxValue)](#nextuintuint)
- [public uint NextUInt(uint minValue, uint maxValue)](#nextuintuint-uint)
- [public long NextLong()](#nextlong)
- [public long NextLong(long maxValue)](#nextlonglong)
- [public long NextLong(long minValue, long maxValue)](#nextlonglong-long)
- [public ulong NextULong()](#nextulong)
- [public ulong NextULong(ulong maxValue)](#nextulongulong)
- [public ulong NextULong(ulong minValue, ulong maxValue)](#nextulongulong-ulong)

### Custom Random
For custom random algorithm or behavior, any class that inherit from System.Random can use these extension method too, and for those custom random class that override default random method(Next(), NextDouble(), NextBytes()), the behavior for method in this extension will also change, for example:
```C#
using System;
using System.RandomExtension;

namespace RandomExtensionExample
{
    public class MyRandom : System.Random
    {
        public MyRandom() : base() { }
        public MyRandom(int Seed) : base(Seed) { }

        public override int Next(int minValue, int maxValue)
        {
            return 100;
        }
    }

    public class Example
    {
        public static void Main()
        {
            MyRandom() rnd = new MyRandom();
            byte b = rnd.NextByte();    //100
        }
    }
}
```

# Document of All Method
## NextDouble(Double, Double)
```C#
public double NextDouble(
    double minValue,
    double maxValue
)
```
### Parameter
*minValue*
> Type: System.Double  
> The inclusive lower bound of the random number returned.

*maxValue*
> Type: System.Double  
> The exclusive upper bound of the random number returned. maxValue must be greater than or equal to minValue.

### Return
> Type: System.Double  
> A double-precision floating point number that is greater than or equal to minValue, and less than maxValue.

### Exception
**ArgumentOutOfRangeException**
> minValue is greater than maxValue.

### Summary
Returns a random floating-point number that is range from minValue to maxValue. If maxValue equals minValue, the method returns minValue. NextDouble() from System.Random is used.

## NextFloat()
```C#
public float NextFloat()
```
### Return
> Type: System.Single  
> A single-precision floating point number that is greater than or equal to 0.0f, and less than 1.0f.

### Summary
Returns a random floating-point number that is range from 0.0f to 1.0f. NextDouble() from System.Random is used.

## NextFloat(Float, Float)
```C#
public float NextFloat(
    float minValue,
    float maxValue
)
```
### Parameter
*minValue*
> Type: System.Single  
> The inclusive lower bound of the random number returned.

*maxValue*
> Type: System.Single  
> The exclusive upper bound of the random number returned. maxValue must be greater than or equal to minValue.

### Return
> Type: System.Single  
> A single-precision floating point number that is greater than or equal to minValue, and less than maxValue.

### Exception
**ArgumentOutOfRangeException**
> minValue is greater than maxValue.

### Summary
Returns a random floating-point number that is range from minValue to maxValue. If maxValue equals minValue, the method returns minValue. NextDouble() from System.Random is used.

## NextDecimal()
```C#
public decimal NextDecimal()
```
### Return
> Type: System.Decimal  
> A decimal number that is greater than or equal to 0.0m, and less than 1.0m.

### Summary
Returns a random decimal number that is range from 0.0m to 1.0m. Next(Int32) from System.Random is used.

## NextDecimal(Decimal, Decimal)
```C#
public decimal NextDecimal(
    decimal minValue,
    decimal maxValue
)
```
### Parameter
*minValue*
> Type: System.Decimal  
> The inclusive lower bound of the random number returned.

*maxValue*
> Type: System.Decimal  
> The exclusive upper bound of the random number returned. maxValue must be greater than or equal to minValue.

### Return
> Type: System.Decimal  
> A decimal number that is greater than or equal to minValue, and less than maxValue.

### Exception
**ArgumentOutOfRangeException**
> minValue is greater than maxValue.

### Summary
Returns a random decimal number that is range from minValue to maxValue. If maxValue equals minValue, the method returns minValue. Next(Int32) from System.Random is used.
