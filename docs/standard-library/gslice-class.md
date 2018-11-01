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
ms.openlocfilehash: bee6fec3e09f7c5758112ba8b0c171a300797f9a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50592172"
---
# <a name="gslice-class"></a>gslice Sınıfı

Çok boyutlu bir valarray kümelerine tanımlamak için kullanılan valarray için yardımcı program sınıfı. Bir valarray bir dizideki tüm öğeler çok boyutlu bir matris olarak kabul edilir, dilim boyutlu bir dizi dışında bir vektör ayıklar.

## <a name="remarks"></a>Açıklamalar

Sınıf türünde bir nesne niteleyen parametreleri depolayan [gslice_array](../standard-library/gslice-array-class.md). Gslice sınıfı bir nesne sınıfının bir nesnesi için bağımsız değişken olarak göründüğünde alt kümesini bir valarray dolaylı olarak oluşturulmuş [valarray](../standard-library/valarray-class.md#op_at)**\<türü >**. Üst valarray Seçili alt küme belirtmeyi depolanan değerler şunlardır:

- Bir başlangıç dizini.

- Sınıfın bir uzunluk vektör `valarray<size_t>`.

- STRIDE vektör sınıfın `valarray<size_t>`.

İki vektörün aynı uzunlukta olmalıdır.

Bir gslice tarafından tanımlanan kümeye bir sabit valarray alt kümesidir, gslice yeni valarray olur. Bir gslice tarafından tanımlanan kümeye nonconstant valarray alt kümesidir, gslice özgün valarray için başvuru semantiği vardır. Değerlendirme mekanizması nonconstant valarrays süresi ve bellek kaydeder.

Valarrays işlemleri yalnızca gslices tarafından tanımlanan kaynak ve hedef kümeleri farklıdır ve tüm dizinleri geçerli garanti edilir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[gslice](#gslice)|Bir alt kümesini tanımlayan bir `valarray` birden çok dilimleri oluşur `valarray` tüm belirtilen bir öğe başlangıç.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Boyutu](#size)|Öğe sayıları genel bir dilim belirten dizi değerlerini bulur bir `valarray`.|
|[Başlangıç](#start)|Genel bir dilimin başlangıç dizini bulur bir `valarray`.|
|[STRIDE](#stride)|Genel bir dilimin öğeler arasındaki uzaklık bulur bir `valarray`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<valarray >

**Namespace:** std

## <a name="gslice"></a>  gslice::gslice

Çok boyutlu bir valarray Kesitler tanımlamak için kullanılan valarray için yardımcı program sınıfı.

```cpp
gslice();

gslice(
    size_t _StartIndex,
    const valarray<size_t>& _LenArray,
    const valarray<size_t>& _IncArray);
```

### <a name="parameters"></a>Parametreler

*_StartIndex*<br/>
Valarray ilk alt öğenin dizini.

*_LenArray*<br/>
Her bir dilimi içinde öğe sayısını belirten bir dizi.

*_IncArray*<br/>
İlerleme her bir dilimi belirten bir dizi.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan Oluşturucu, başlangıç dizini için sıfır ve sıfır uzunluklu vektörleri uzunluğu ve STRIDE vektör depolar. İkinci oluşturucu depoları *_StartIndex* başlangıç dizini için *_LenArray* uzunluk dizisi için ve *_IncArray* STRIDE dizi.

### <a name="remarks"></a>Açıklamalar

**gslice** aynı her bir başlangıç öğesi belirtilen valarray birden çok Kesitler oluşan bir valarray kümesini tanımlar. Birden çok dilim tanımlamak için dizileri kullanabilme arasındaki tek fark olduğu `gslice` ve [slice::slice](../standard-library/slice-class.md#slice). İlk dilim ile bir dizinin ilk öğesinin *_StartIndex*, bir dizi ilk öğesi tarafından belirtilen öğe *_LenArray*ve ilk öğesi tarafından verilen bir adım *_IncArray* . Sonraki dikey dilimleri kümesini ilk dilim tarafından verilen ilk öğesine sahip. İkinci öğesini *_LenArray* öğelerin sayısını belirtir. STRIDE ikinci öğesi tarafından verilen *_IncArray*. Üçüncü boyutu dilim ve iki boyutlu dizi öğelerinin başlangıç öğesi olarak ele öğesine devam edin

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

## <a name="size"></a>  gslice::size

Öğe sayıları bir valarray genel bir dilim belirten dizi değerlerini bulur.

```cpp
valarray<size_t> size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir valarray, genel bir dilim her bir dilimi öğelerin sayısını belirten bir valarray.

### <a name="remarks"></a>Açıklamalar

Üye işlevi dilimleri saklı uzunluklarının döndürür.

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

## <a name="start"></a>  gslice::Start

Genel bir valarray dilimin başlangıç dizini bulur.

```cpp
size_t start() const;
```

### <a name="return-value"></a>Dönüş Değeri

Genel bir valarray dilimin başlangıç dizini.

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

## <a name="stride"></a>  gslice::stride

Genel bir valarray dilimin öğeler arasındaki uzaklık bulur.

```cpp
valarray<size_t> stride() const;
```

### <a name="return-value"></a>Dönüş Değeri

Genel bir diliminin bir valarray, her bir dilimi öğeler arasında uzaklıkları belirten bir valarray.

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

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
