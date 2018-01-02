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
//Random rnd = new Random(seed);    //with seed
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
- [public short NextShort(short maxValue)](#nextshortint16)
- [public short NextShort(short minValue, short maxValue)](#nextshortint16-int16)
- [public ushort NextUShort()](#nextushort)
- [public ushort NextUShort(ushort maxValue)](#nextushortuint16)
- [public ushort NextUShort(ushort minValue, ushort maxValue)](#nextushortuint16-uint16)
- [public uint NextUInt()](#nextuint)
- [public uint NextUInt(uint maxValue)](#nextuintuint32)
- [public uint NextUInt(uint minValue, uint maxValue)](#nextuintuint32-uint32)
- [public long NextLong()](#nextlong)
- [public long NextLong(long maxValue)](#nextlongint64)
- [public long NextLong(long minValue, long maxValue)](#nextlongint64-int64)
- [public ulong NextULong()](#nextulong)
- [public ulong NextULong(ulong maxValue)](#nextulonguint64)
- [public ulong NextULong(ulong minValue, ulong maxValue)](#nextulonguint64-uint64)

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
            //MyRandom rnd = new MyRandom(seed);    //with seed
            byte b = rnd.NextByte(0, 50);    //100
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
> The exclusive upper bound of the random number returned. *maxValue* must be greater than or equal to *minValue*.

### Return
> Type: System.Double  
> A double-precision floating point number that is greater than or equal to *minValue*, and less than *maxValue*.

### Exception
**ArgumentOutOfRangeException**
> *minValue* is greater than *maxValue*.

### Summary
The NextDouble(Double, Double) overload returns a random floating-point number that is greater than or equal to *minValue*, and less than *maxValue*. If *maxValue* equals *minValue*, the method returns *minValue*. NextDouble() from System.Random is used.

## NextFloat()
```C#
public float NextFloat()
```
### Return
> Type: System.Single  
> A single-precision floating point number that is greater than or equal to 0.0f, and less than 1.0f.

### Summary
The NextFloat() extend method returns a random floating-point number that is greater than or equal to 0.0f, and less than 1.0f. NextDouble() from System.Random is used. To retrieve random floating point values within a range other than 0.0f and 1.0f, use the NextFloat(Float, Float) method overload.

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
> The exclusive upper bound of the random number returned. *maxValue* must be greater than or equal to *minValue*.

### Return
> Type: System.Single  
> A single-precision floating point number that is greater than or equal to *minValue*, and less than *maxValue*.

### Exception
**ArgumentOutOfRangeException**
> *minValue* is greater than *maxValue*.

### Summary
The NextFloat(Float, Float) overload returns a random floating-point number that is greater than or equal to *minValue*, and less than *maxValue*. If *maxValue* equals *minValue*, the method returns *minValue*. NextDouble() from System.Random is used.

## NextDecimal()
```C#
public decimal NextDecimal()
```
### Return
> Type: System.Decimal  
> A decimal number that is greater than or equal to 0.0m, and less than 1.0m.

### Summary
The NextDecimal() extend method returns a random decimal number that is greater than or equal to 0.0m, and less than 1.0m. Next(Int32) from System.Random is used. To retrieve random decimal values within a range other than 0.0m and 1.0m, use the NextDecimal(Decimal, Decimal) method overload.

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
> The exclusive upper bound of the random number returned. *maxValue* must be greater than or equal to *minValue*.

### Return
> Type: System.Decimal  
> A decimal number that is greater than or equal to *minValue*, and less than *maxValue*.

### Exception
**ArgumentOutOfRangeException**
> *minValue* is greater than *maxValue*.

### Summary
The NextDecimal(Decimal, Decimal) overload returns a random decimal number that is greater than or equal to *minValue*, and less than *maxValue*. If *maxValue* equals *minValue*, the method returns *minValue*. Next(Int32) from System.Random is used.

## NextByte()
```C#
public byte NextByte()
```
### Return
> Type: System.Byte  
> A 8-bit unsigned integer that is greater than or equal to 0 and less than MaxValue.

### Summary
The NextByte() extend method returns a random byte number that is range from 0 to Byte.MaxValue-1. Next(Int32) from System.Random is used. To generate a random byte number whose value ranges from 0 to some other byte number, use the NextByte(Byte) method overload. To generate a random byte number within a different range, use the NextByte(Byte, Byte) method overload.

## NextByte(Byte)
```C#
public byte NextByte(
    byte maxValue
)
```
### Parameter
*maxValue*
> Type: System.Byte  
> The exclusive upper bound of the random number returned.

### Return
> Type: System.Byte  
> A 8-bit unsigned integer that is greater than or equal to 0 and less than *maxValue*; that is, the range of return values ordinarily inclueds 0 but not *maxValue*. However, if *maxValue* equals 0, *maxValue* is return.

### Summary
The NextByte(Byte) overload returns a random byte number that is range from 0 to *maxValue*-1. If *maxValue* is 0, the method returns 0. Next(Int32) from System.Random is used.

## NextByte(Byte, Byte)
```C#
public byte NextByte(
    byte minValue,
    byte maxValue
)
```
### Parameter
*minValue*
> Type: System.Byte  
> The inclusive lower bound of the random number returned.

*maxValue*
> Type: System.Byte  
> The exclusive upper bound of the random number returned. *maxValue* must be greater than or equal to *minValue*.

### Return
> Type: System.Byte  
> A 8-bit unsigned integer greater than or equal to *minValue* and less than *maxValue*; that is, the range of return values includes *minValue* but not *maxValue*. If *minValue* equals *maxValue*, *minValue* is returned.

### Exception
**ArgumentOutOfRangeException**
> *minValue* is greater than *maxValue*.

### Summary
The NextByte(Byte, Byte) overload returns a random byte number that is range from *minValue* to *maxValue*. If *maxValue* equals *minValue*, the method returns *minValue*. Next(Int32, Int32) from System.Random is used.

## NextSByte()
```C#
public sbyte NextSByte()
```
### Return
> Type: System.SByte  
> A 8-bit signed integer that is greater than or equal to 0 and less than MaxValue.

### Summary
The NextSByte() extend method returns a random sbyte number that is range from 0 to SByte.MaxValue-1. Next(Int32) from System.Random is used. To generate a random sbyte number whose value ranges from 0 to some other positive sbyte number, use the NextSByte(SByte) method overload. To generate a random sbyte number within a different range, use the NextSByte(SByte, SByte) method overload.

## NextSByte(SByte)
```C#
public sbyte NextSByte(
    sbyte maxValue
)
```
### Parameter
*maxValue*
> Type: System.SByte  
> The exclusive upper bound of the random number returned. *maxValue* must be greater than or equal to 0.

### Return
> Type: System.SByte  
> A 8-bit signed integer that is greater than or equal to 0 and less than *maxValue*; that is, the range of return values ordinarily inclueds 0 but not *maxValue*. However, if *maxValue* equals 0, *maxValue* is return.

### Exception
**ArgumentOutOfRangeException**
> *maxValue* is less than 0.

### Summary
The NextSByte(SByte) overload returns a random sbyte number that is range from 0 to *maxValue*-1. If *maxValue* is 0, the method returns 0. Next(Int32) from System.Random is used.

## NextSByte(SByte, SByte)
```C#
public sbyte NextSByte(
    sbyte minValue,
    sbyte maxValue
)
```
### Parameter
*minValue*
> Type: System.SByte  
> The inclusive lower bound of the random number returned.

*maxValue*
> Type: System.SByte  
> The exclusive upper bound of the random number returned. *maxValue* must be greater than or equal to *minValue*.

### Return
> Type: System.SByte  
> A 8-bit signed integer greater than or equal to *minValue* and less than *maxValue*; that is, the range of return values includes *minValue* but not *maxValue*. If *minValue* equals *maxValue*, *minValue* is returned.

### Exception
**ArgumentOutOfRangeException**
> *minValue* is greater than *maxValue*.

### Summary
The NextSByte(SByte, SByte) overload returns a random sbyte number that is range from *minValue* to *maxValue*. If *maxValue* equals *minValue*, the method returns *minValue*. Next(Int32, Int32) from System.Random is used.

## NextShort()
```C#
public short NextShort()
```
### Return
> Type: System.Int16  
> A 16-bit signed integer that is greater than or equal to 0 and less than MaxValue.

### Summary
The NextShort() extend method returns a random short number that is range from 0 to Int16.MaxValue-1. Next(Int32) from System.Random is used. To generate a random short number whose value ranges from 0 to some other positive short number, use the NextShort(Int16) method overload. To generate a random short number within a different range, use the NextShort(Int16, Int16) method overload.

## NextShort(Int16)
```C#
public short NextShort(
    short maxValue
)
```
### Parameter
*maxValue*
> Type: System.Int16  
> The exclusive upper bound of the random number returned. *maxValue* must be greater than or equal to 0.

### Return
> Type: System.Int16  
> A 16-bit signed integer that is greater than or equal to 0 and less than *maxValue*; that is, the range of return values ordinarily inclueds 0 but not *maxValue*. However, if *maxValue* equals 0, *maxValue* is return.

### Exception
**ArgumentOutOfRangeException**
> *maxValue* is less than 0.

### Summary
The NextShort(Int16) overload returns a random short number that is range from 0 to *maxValue*-1. If *maxValue* is 0, the method returns 0. Next(Int32) from System.Random is used.

## NextShort(Int16, Int16)
```C#
public short NextShort(
    short minValue,
    short maxValue
)
```
### Parameter
*minValue*
> Type: System.Int16  
> The inclusive lower bound of the random number returned.

*maxValue*
> Type: System.Int16  
> The exclusive upper bound of the random number returned. *maxValue* must be greater than or equal to *minValue*.

### Return
> Type: System.Int16  
> A 16-bit signed integer greater than or equal to *minValue* and less than *maxValue*; that is, the range of return values includes *minValue* but not *maxValue*. If *minValue* equals *maxValue*, *minValue* is returned.

### Exception
**ArgumentOutOfRangeException**
> *minValue* is greater than *maxValue*.

### Summary
The NextShort(Int16, Int16) overload returns a random short number that is range from *minValue* to *maxValue*. If *maxValue* equals *minValue*, the method returns *minValue*. Next(Int32, Int32) from System.Random is used.

## NextUShort()
```C#
public ushort NextUShort()
```
### Return
> Type: System.UInt16  
> A 16-bit unsigned integer that is greater than or equal to 0 and less than MaxValue.

### Summary
The NextUShort() extend method returns a random ushort number that is range from 0 to UInt16.MaxValue-1. Next(Int32) from System.Random is used. To generate a random ushort number whose value ranges from 0 to some other ushort number, use the NextUShort(UInt16) method overload. To generate a random ushort number within a different range, use the NextUShort(UInt16, UInt16) method overload.

## NextUShort(UInt16)
```C#
public ushort NextUShort(
    ushort maxValue
)
```
### Parameter
*maxValue*
> Type: System.UInt16  
> The exclusive upper bound of the random number returned.

### Return
> Type: System.UInt16  
> A 16-bit unsigned integer that is greater than or equal to 0 and less than *maxValue*; that is, the range of return values ordinarily inclueds 0 but not *maxValue*. However, if *maxValue* equals 0, *maxValue* is return.

### Summary
The NextUShort(UInt16) overload returns a random ushort number that is range from 0 to *maxValue*-1. If *maxValue* is 0, the method returns 0. Next(Int32) from System.Random is used.

## NextUShort(UInt16, UInt16)
```C#
public ushort NextUShort(
    ushort minValue,
    ushort maxValue
)
```
### Parameter
*minValue*
> Type: System.UInt16  
> The inclusive lower bound of the random number returned.

*maxValue*
> Type: System.UInt16  
> The exclusive upper bound of the random number returned. *maxValue* must be greater than or equal to *minValue*.

### Return
> Type: System.UInt16  
> A 16-bit unsigned integer greater than or equal to *minValue* and less than *maxValue*; that is, the range of return values includes *minValue* but not *maxValue*. If *minValue* equals *maxValue*, *minValue* is returned.

### Exception
**ArgumentOutOfRangeException**
> *minValue* is greater than *maxValue*.

### Summary
The NextUShort(UInt16, UInt16) overload returns a random ushort number that is range from *minValue* to *maxValue*. If *maxValue* equals *minValue*, the method returns *minValue*. Next(Int32, Int32) from System.Random is used.

## NextUInt()
```C#
public uint NextUInt()
```
### Return
> Type: System.UInt32  
> A 32-bit unsigned integer that is greater than or equal to 0 and less than MaxValue.

### Summary
The NextUInt() extend method returns a random uint number that is range from 0 to UInt32.MaxValue-1. NextBytes(Byte[]) from System.Random is used. To generate a random uint number whose value ranges from 0 to some other uint number, use the NextUInt(UInt32) method overload. To generate a random uint number within a different range, use the NextUInt(UInt32, UInt32) method overload.

## NextUInt(UInt32)
```C#
public uint NextUInt(
    uint maxValue
)
```
### Parameter
*maxValue*
> Type: System.UInt32  
> The exclusive upper bound of the random number returned.

### Return
> Type: System.UInt32  
> A 32-bit unsigned integer that is greater than or equal to 0 and less than *maxValue*; that is, the range of return values ordinarily inclueds 0 but not *maxValue*. However, if *maxValue* equals 0, *maxValue* is return.

### Summary
The NextUInt(UInt32) overload returns a random uint number that is range from 0 to *maxValue*-1. If *maxValue* is 0, the method returns 0. NextBytes(Byte[]) from System.Random is used.

## NextUInt(UInt32, UInt32)
```C#
public uint NextUInt(
    uint minValue,
    uint maxValue
)
```
### Parameter
*minValue*
> Type: System.UInt32  
> The inclusive lower bound of the random number returned.

*maxValue*
> Type: System.UInt32  
> The exclusive upper bound of the random number returned. *maxValue* must be greater than or equal to *minValue*.

### Return
> Type: System.UInt32  
> A 32-bit unsigned integer greater than or equal to *minValue* and less than *maxValue*; that is, the range of return values includes *minValue* but not *maxValue*. If *minValue* equals *maxValue*, *minValue* is returned.

### Exception
**ArgumentOutOfRangeException**
> *minValue* is greater than *maxValue*.

### Summary
The NextUInt(UInt32, UInt32) overload returns a random uint number that is range from *minValue* to *maxValue*. If *maxValue* equals *minValue*, the method returns *minValue*. NextBytes(Byte[]) from System.Random is used.

## NextLong()
```C#
public long NextLong()
```
### Return
> Type: System.Int64  
> A 64-bit signed integer that is greater than or equal to 0 and less than MaxValue.

### Summary
The NextLong() extend method returns a random long number that is range from 0 to Int64.MaxValue-1. NextBytes(Byte[]) from System.Random is used. To generate a random long number whose value ranges from 0 to some other positive long number, use the NextLong(Int64) method overload. To generate a random long number within a different range, use the NextLong(Int64, Int64) method overload.

## NextLong(Int64)
```C#
public long NextLong(
    long maxValue
)
```
### Parameter
*maxValue*
> Type: System.Int64  
> The exclusive upper bound of the random number returned. *maxValue* must be greater than or equal to 0.

### Return
> Type: System.Int64  
> A 64-bit signed integer that is greater than or equal to 0 and less than *maxValue*; that is, the range of return values ordinarily inclueds 0 but not *maxValue*. However, if *maxValue* equals 0, *maxValue* is return.

### Exception
**ArgumentOutOfRangeException**
> *maxValue* is less than 0.

### Summary
The NextLong(Int64) overload returns a random long number that is range from 0 to *maxValue*-1. If *maxValue* is 0, the method returns 0. NextBytes(Byte[]) from System.Random is used.

## NextLong(Int64, Int64)
```C#
public long NextLong(
    long minValue,
    long maxValue
)
```
### Parameter
*minValue*
> Type: System.Int64  
> The inclusive lower bound of the random number returned.

*maxValue*
> Type: System.Int64  
> The exclusive upper bound of the random number returned. *maxValue* must be greater than or equal to *minValue*.

### Return
> Type: System.Int64  
> A 64-bit signed integer greater than or equal to *minValue* and less than *maxValue*; that is, the range of return values includes *minValue* but not *maxValue*. If *minValue* equals *maxValue*, *minValue* is returned.

### Exception
**ArgumentOutOfRangeException**
> *minValue* is greater than *maxValue*.

### Summary
The NextLong(Int64, Int64) overload returns a random long number that is range from *minValue* to *maxValue*. If *maxValue* equals *minValue*, the method returns *minValue*. Next(Int64, Int64) from System.Random is used.

## NextULong()
```C#
public ulong NextULong()
```
### Return
> Type: System.UInt64  
> A 64-bit unsigned integer that is greater than or equal to 0 and less than MaxValue.

### Summary
The NextULong() extend method returns a random ulong number that is range from 0 to UInt64.MaxValue-1. NextBytes(Byte[]) from System.Random is used. To generate a random ulong number whose value ranges from 0 to some other ulong number, use the NextULong(UInt64) method overload. To generate a random ulong number within a different range, use the NextULong(UInt64, UInt64) method overload.

## NextULong(UInt64)
```C#
public ulong NextULong(
    ulong maxValue
)
```
### Parameter
*maxValue*
> Type: System.UInt64  
> The exclusive upper bound of the random number returned.

### Return
> Type: System.UInt64  
> A 64-bit unsigned integer that is greater than or equal to 0 and less than *maxValue*; that is, the range of return values ordinarily inclueds 0 but not *maxValue*. However, if *maxValue* equals 0, *maxValue* is return.

### Summary
The NextULong(UInt64) overload returns a random ulong number that is range from 0 to *maxValue*-1. If *maxValue* is 0, the method returns 0. NextBytes(Byte[]) from System.Random is used.

## NextULong(UInt64, UInt64)
```C#
public ulong NextULong(
    ulong minValue,
    ulong maxValue
)
```
### Parameter
*minValue*
> Type: System.UInt64  
> The inclusive lower bound of the random number returned.

*maxValue*
> Type: System.UInt64  
> The exclusive upper bound of the random number returned. *maxValue* must be greater than or equal to *minValue*.

### Return
> Type: System.UInt64  
> A 64-bit unsigned integer greater than or equal to *minValue* and less than *maxValue*; that is, the range of return values includes *minValue* but not *maxValue*. If *minValue* equals *maxValue*, *minValue* is returned.

### Exception
**ArgumentOutOfRangeException**
> *minValue* is greater than *maxValue*.

### Summary
The NextULong(UInt64, UInt64) overload returns a random ulong number that is range from *minValue* to *maxValue*. If *maxValue* equals *minValue*, the method returns *minValue*. NextBytes(Byte[]) from System.Random is used.