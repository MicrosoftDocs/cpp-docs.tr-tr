---
description: 'Daha fazla bilgi edinin: gslice sınıfı'
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
ms.openlocfilehash: 92bb8d56df40a7d59c5414aca3e0d5846401e805
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324154"
---
# <a name="gslice-class"></a>gslice Sınıfı

Bir valarray 'ın çok boyutlu alt kümelerini tanımlamak için kullanılan valarray için yardımcı program sınıfı. Bir valarray, bir dizideki tüm öğelerle çok boyutlu bir matris olarak kabul edilir, dilim çok boyutlu dizinin bir vektörünü ayıklar.

## <a name="remarks"></a>Açıklamalar

Sınıfı, [gslice_array](../standard-library/gslice-array-class.md)türünde bir nesne niteleyen parametreleri depolar. Bir valarray alt kümesi, gslice sınıfının bir nesnesi [valarray](../standard-library/valarray-class.md#op_at)sınıfının bir nesnesi için bağımsız değişken olarak göründüğünde dolaylı olarak oluşturulur **\<Type>** . Üst valarray seçili alt kümeyi belirten depolanan değerler şunları içerir:

- Başlangıç dizini.

- Sınıfın uzunluk vektörü `valarray<size_t>` .

- Sınıfın bir adım vektörü `valarray<size_t>` .

İki vektörün aynı uzunlukta olması gerekir.

Bir gslice tarafından tanımlanan küme bir sabit valarray alt kümesiyse, gslice yeni bir valarray. Bir gslice tarafından tanımlanan küme, sabit olmayan bir valarray 'nin alt kümesiyse, gslice 'ın özgün valarray başvuru semantiğini vardır. Sabit olmayan valarışın için değerlendirme mekanizması zaman ve bellek tasarrufu sağlar.

Valarışın üzerinde işlemler yalnızca, gslices tarafından tanımlanan kaynak ve hedef alt kümeleri birbirinden farklı olduğunda ve tüm dizinler geçerliyse garanti edilir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[gslice](#gslice)|`valarray`Belirtilen bir öğe ile başlayan birden çok diliminden oluşan bir alt kümesini tanımlar `valarray` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[boyutla](#size)|Genel bir diliminizdeki öğe sayılarını belirten dizi değerlerini bulur `valarray` .|
|[başından](#start)|A 'nın genel diliminin başlangıç dizinini bulur `valarray` .|
|[adım](#stride)|Bir genel dilimi içindeki öğeler arasındaki mesafeyi bulur `valarray` .|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<valarray>

**Ad alanı:** std

## <a name="gslicegslice"></a><a name="gslice"></a> gslice:: gslice

Bir valarray 'ın çok boyutlu dilimlerini tanımlamak için kullanılan valarray için yardımcı program sınıfı.

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
Her bir dilimdeki öğelerin sayısını belirten bir dizi.

*_IncArray*\
Her bir dilimde bir adım belirten dizi.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan Oluşturucu başlangıç dizini için sıfır, uzunluk ve ilerleme vektörlerine yönelik sıfır uzunluklu vektörler depolar. İkinci Oluşturucu başlangıç dizini için *_StartIndex* , uzunluk dizisi için *_LenArray* ve ilerme dizisine yönelik *_IncArray* depolar.

### <a name="remarks"></a>Açıklamalar

**gslice** , her biri belirtilen öğede başlayan valarray birden çok diliminden oluşan bir valarray alt kümesini tanımlar. Birden çok dilimi tanımlamak için dizileri kullanma yeteneği, `gslice` ve [Slice:: Slice](../standard-library/slice-class.md#slice)arasındaki tek farktır. İlk dilimde *_StartIndex* dizinine sahip bir ilk öğe, *_LenArray* ilk öğesi tarafından belirtilen bir dizi öğe ve *_IncArray* ilk öğesi tarafından verilen bir adım vardır. Dikgen dilimlerin sonraki kümesinde ilk dilim tarafından verilen ilk öğe vardır. *_LenArray* ikinci öğesi öğelerin sayısını belirtir. Bu adım *_IncArray* ikinci öğesi tarafından verilir. Üçüncü bir dilim boyutu, iki boyutlu dizinin öğelerini başlangıç öğeleri olarak alır ve anormal olarak devam edecektir

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

## <a name="gslicesize"></a><a name="size"></a> gslice:: size

Bir valarray genel diliminizdeki öğe sayılarını belirten dizi değerlerini bulur.

```cpp
valarray<size_t> size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir valarray 'ın genel diliminin her bir diliminizdeki öğe sayısını belirten bir valarray.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, dilimlerin saklı uzunluklarını döndürür.

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

## <a name="gslicestart"></a><a name="start"></a> gslice:: Start

Bir valarray genel diliminin başlangıç dizinini bulur.

```cpp
size_t start() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir valarray genel diliminin başlangıç dizini.

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

## <a name="gslicestride"></a><a name="stride"></a> gslice:: ilerme

Bir valarray genel diliminden öğeler arasındaki mesafeyi bulur.

```cpp
valarray<size_t> stride() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir valarray 'ın genel diliminin her bir diliminizdeki öğeler arasındaki uzaklıkları belirten bir valarray.

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

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
