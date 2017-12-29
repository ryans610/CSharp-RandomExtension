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
```C#
[public double NextDouble(double minValue, double maxValue)](#NextDouble(Double, Double))
public float NextFloat()
public float NextFloat(float minValue, float maxValue)
public decimal NextDecimal()
public decimal NextDecimal(decimal minValue, decimal maxValue)
public byte NextByte()
public byte NextByte(byte maxValue)
public byte NextByte(byte minValue, byte maxValue)
public sbyte NextSByte()
public sbyte NextSByte(sbyte maxValue)
public sbyte NextSByte(sbyte minValue, sbyte maxValue)
public short NextShort()
public short NextShort(short maxValue)
public short NextShort(short minValue, short maxValue)
public ushort NextUShort()
public ushort NextUShort(ushort maxValue)
public ushort NextUShort(ushort minValue, ushort maxValue)
public uint NextUInt()
public uint NextUInt(uint maxValue)
public uint NextUInt(uint minValue, uint maxValue)
public long NextLong()
public long NextLong(long maxValue)
public long NextLong(long minValue, long maxValue)
public ulong NextULong()
public ulong NextULong(ulong maxValue)
public ulong NextULong(ulong minValue, ulong maxValue)
```

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
Returns a random floating-point number that is range from minValue to maxValue. NextDouble() from System.Random is used.
