---
title: gslice Sınıfı
ms.date: 11/04/2016
f1_keywords:
- valarray/std::gslice
- valarray/std::gslice::size
- valarray/std::gslice::start
- valarray/std::gslice::stride
helpviewer_keywords:
- std::gslice [C++]
- std::gslice [C++], size
- std::gslice [C++], start
- std::gslice [C++], stride
ms.assetid: f47cffd0-ea59-4b13-848b-7a5ce1d7e2a3
ms.openlocfilehash: 07c987fb08a213bb66da628bec3021a3bf9ba24a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370633"
---
# <a name="gslice-class"></a>gslice Sınıfı

Bir valarray çok boyutlu alt kümeleri tanımlamak için kullanılan valarray için bir yardımcı program sınıfı. Bir valarray bir dizi tüm öğeleri ile çok boyutlu bir matris olarak kabul edilirse, o zaman dilim çok boyutlu dizi bir vektör ayıklar.

## <a name="remarks"></a>Açıklamalar

Sınıf, tür [gslice_array](../standard-library/gslice-array-class.md)bir nesneyi karakterize eden parametreleri depolar. Bir valarray alt kümesi dolaylı olarak sınıf gslice bir nesne sınıf [valarray](../standard-library/valarray-class.md#op_at)**\<Türü>** bir nesne için bir argüman olarak görünür oluşturulur. Üst valarray seçilen alt kümesini belirten depolanan değerler şunlardır:

- Başlangıç indeksi.

- Sınıfın `valarray<size_t>`uzunluk vektörü.

- Sınıfın `valarray<size_t>`bir adım vektörü.

İki vektör aynı uzunlukta olmalıdır.

Bir gslice tarafından tanımlanan küme sabit bir valarray alt kümesi ise, gslice yeni bir valarray olduğunu. Bir gslice tarafından tanımlanan küme sabit olmayan bir valarray alt kümesi ise, gslice orijinal valarray için referans semantiği vardır. Sabit olmayan valarrays için değerlendirme mekanizması zaman ve bellek kazandırır.

Valarrays işlemleri yalnızca gslices tarafından tanımlanan kaynak ve hedef alt kümeleri farklı ve tüm endeksler geçerli yse garanti edilir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[gslice](#gslice)|Tüm başlangıç belirli bir `valarray` öğede `valarray` birden çok dilimden oluşan bir alt kümesi tanımlar.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Boyutu](#size)|Bir `valarray`. genel dilimindeki öğelerin sayılarını belirten dizi değerlerini bulur|
|[Başlatmak](#start)|Bir `valarray`' nin genel diliminin başlangıç dizinini bulur|
|[Adım](#stride)|Bir 'nin genel dilimindeki öğeler `valarray`arasındaki mesafeyi bulur.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<valarray>

**Ad alanı:** std

## <a name="gslicegslice"></a><a name="gslice"></a>gslice::gslice

Bir valarray çok boyutlu dilimlerini tanımlamak için kullanılan valarray için bir yardımcı program sınıfı.

```cpp
gslice();

gslice(
    size_t _StartIndex,
    const valarray<size_t>& _LenArray,
    const valarray<size_t>& _IncArray);
```

### <a name="parameters"></a>Parametreler

*_StartIndex*\
Alt kümedeki ilk öğenin valarray dizini.

*_LenArray*\
Her dilimdeki öğe sayısını belirten bir dizi.

*_IncArray*\
Her dilimdeki adımı belirten bir dizi.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan oluşturucu başlangıç dizini için sıfır, uzunluk ve adım vektörleri için sıfır uzunlukta vektörler depolar. İkinci oluşturucu başlangıç dizini için *_StartIndex,* uzunluk dizisi için *_LenArray* ve adım dizisi için *_IncArray* depolar.

### <a name="remarks"></a>Açıklamalar

**gslice,** her biri aynı belirtilen öğeyle başlayan valarray'in birden çok diliminden oluşan bir valarray alt kümesini tanımlar. Birden çok dilim tanımlamak için dizileri kullanma yeteneği `gslice` ve dilim arasındaki tek [fark::dilim](../standard-library/slice-class.md#slice). İlk *dilim, _StartIndex*dizinli bir ilk elemana sahiptir, *_LenArray*ilk öğesi tarafından belirtilen bir dizi öğe ve *_IncArray*ilk öğesi tarafından verilen bir adım. Ortogonal dilimleri sonraki kümesi ilk dilim tarafından verilen ilk öğeleri vardır. *_LenArray* ikinci öğesi öğe sayısını belirtir. Adım *_IncArray*ikinci elemanı tarafından verilir. Dilimlerin üçüncü bir boyutu başlangıç elemanları olarak iki boyutlu dizinin öğelerini alır ve benzer şekilde devam eder

### <a name="example"></a>Örnek

```cpp
// gslice_ctor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 20 ), vaResult;
   for ( i = 0 ; i < 20 ; i+=1 )
      va [ i ] =  i;

   cout << "The operand valarray va is:" << endl << "(";
   for ( i = 0 ; i < 20 ; i++ )
      cout << " " << va [ i ];
   cout << " )" << endl;

   valarray<size_t> Len ( 2 ), Stride ( 2 );
   Len [0] = 4;
   Len [1] = 4;
   Stride [0] = 7;
   Stride [1] = 4;

   gslice vaGSlice ( 0, Len, Stride );
   vaResult = va [ vaGSlice ];

   cout << "The valarray for vaGSlice is vaResult:" << endl
        << "va[vaGSlice] = (";

   for ( i = 0 ; i < 8 ; i++ )
      cout << " " << vaResult [ i ];
   cout << ")" << endl;
}
```

```Output
The operand valarray va is:
( 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 )
The valarray for vaGSlice is vaResult:
va[vaGSlice] = ( 0 4 8 12 7 11 15 19)
```

## <a name="gslicesize"></a><a name="size"></a>gslice::boyut

Bir valarray genel bir dilimde öğelerin sayılarını belirten dizi değerlerini bulur.

```cpp
valarray<size_t> size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir valarray genel bir dilimin her dilimindeki öğe sayısını belirten bir valarray.

### <a name="remarks"></a>Açıklamalar

Üye işlev, depolanan dilim uzunluklarını döndürür.

### <a name="example"></a>Örnek

```cpp
// gslice_size.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;
   size_t sizeVA;

   valarray<int> va ( 20 ), vaResult;
   for ( i = 0 ; i < 20 ; i+=1 )
      va [ i ] =  i;

   cout << "The operand valarray va is:\n ( ";
      for ( i = 0 ; i < 20 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   sizeVA = va.size ( );
   cout << "The size of the valarray is: "
        << sizeVA << "." << endl << endl;

   valarray<size_t> Len ( 2 ), Stride ( 2 );
   Len [0] = 4;
   Len [1] = 4;
   Stride [0] = 7;
   Stride [1] = 4;

   gslice vaGSlice ( 0, Len, Stride );
   vaResult = va [ vaGSlice ];
   const valarray <size_t> sizeGS = vaGSlice.size ( );

   cout << "The valarray for vaGSlice is vaResult:"
        << "\n va[vaGSlice] = ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaResult [ i ] << " ";
   cout << ")." << endl;

   cout << "The size of vaResult is:"
        << "\n vaGSlice.size ( ) = ( ";
      for ( i = 0 ; i < 2 ; i++ )
         cout << sizeGS[ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The operand valarray va is:
( 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 ).
The size of the valarray is: 20.

The valarray for vaGSlice is vaResult:
va[vaGSlice] = ( 0 4 8 12 7 11 15 19 ).
The size of vaResult is:
vaGSlice.size ( ) = ( 4 4 ).
```

## <a name="gslicestart"></a><a name="start"></a>gslice::başlat

Valarray genel bir dilim başlangıç dizini bulur.

```cpp
size_t start() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir valarray genel bir dilim başlangıç dizini.

### <a name="example"></a>Örnek

```cpp
// gslice_start.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 20 ), vaResult;
   for (i = 0 ; i < 20 ; i+=1 )
      va [ i ] =  i;

   cout << "The operand valarray va is:\n ( ";
      for ( i = 0 ; i < 20 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   valarray<size_t> Len ( 2 ), Stride ( 2 );
   Len [0] = 4;
   Len [1] = 4;
   Stride [0] = 7;
   Stride [1] = 4;

   gslice vaGSlice ( 0, Len, Stride );
   vaResult = va [ vaGSlice ];
   size_t vaGSstart = vaGSlice.start ( );

   cout << "The valarray for vaGSlice is vaResult:"
        << "\n va[vaGSlice] = ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaResult [ i ] << " ";
   cout << ")." << endl;

   cout << "The index of the first element of vaResult is: "
        << vaGSstart << "." << endl;
}
```

```Output
The operand valarray va is:
( 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 ).
The valarray for vaGSlice is vaResult:
va[vaGSlice] = ( 0 4 8 12 7 11 15 19 ).
The index of the first element of vaResult is: 0.
```

## <a name="gslicestride"></a><a name="stride"></a>gslice::adım

Bir valarray genel bir dilim elemanları arasındaki mesafeyi bulur.

```cpp
valarray<size_t> stride() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir valarray genel bir dilimin her dilimindeki öğeler arasındaki mesafeleri belirten bir valarray.

### <a name="example"></a>Örnek

```cpp
// gslice_stride.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 20 ), vaResult;
   for (i = 0 ; i < 20 ; i+=1 )
      va [ i ] =  i;

   cout << "The operand valarray va is:\n ( ";
      for (i = 0 ; i < 20 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   valarray<size_t> Len ( 2 ), Stride ( 2 );
   Len [0] = 4;
   Len [1] = 4;
   Stride [0] = 7;
   Stride [1] = 4;

   gslice vaGSlice ( 0, Len, Stride );
   vaResult = va [ vaGSlice ];
   const valarray <size_t> strideGS = vaGSlice.stride ( );

   cout << "The valarray for vaGSlice is vaResult:"
        << "\n va[vaGSlice] = ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaResult [ i ] << " ";
   cout << ")." << endl;

   cout << "The strides of vaResult are:"
        << "\n vaGSlice.stride ( ) = ( ";
      for ( i = 0 ; i < 2 ; i++ )
         cout << strideGS[ i ] << " ";
   cout << ")." << endl;

}
```

```Output
The operand valarray va is:
( 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 ).
The valarray for vaGSlice is vaResult:
va[vaGSlice] = ( 0 4 8 12 7 11 15 19 ).
The strides of vaResult are:
vaGSlice.stride ( ) = ( 7 4 ).
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
