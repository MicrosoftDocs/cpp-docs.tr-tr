---
title: slice Sınıfı
ms.date: 11/04/2016
f1_keywords:
- valarray/std::slice
- valarray/std::slice::size
- valarray/std::slice::start
- valarray/std::slice::stride
helpviewer_keywords:
- std::slice [C++]
- std::slice [C++], size
- std::slice [C++], start
- std::slice [C++], stride
ms.assetid: 00f0b03d-d657-4b81-ba53-5a9034bb2bf2
ms.openlocfilehash: 05f87cbb6061e205f9731d2a903ce52a2482b214
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336716"
---
# <a name="slice-class"></a>slice Sınıfı

Bir üst valarray tek boyutlu alt kümeleri tanımlamak için kullanılan valarray için bir yardımcı program sınıfı. Bir valarray bir dizi deki tüm öğeleri içeren iki boyutlu bir matris olarak kabul edilirse, dilim iki boyutlu diziden bir boyutta bir vektör ayıklar.

## <a name="remarks"></a>Açıklamalar

Sınıf, tür [nesnesini](../standard-library/slice-array-class.md) karakterize eden parametreleri depolar slice_array Bir valarray alt kümesi dolaylı olarak sınıf dilimi nin bir nesnesi sınıf [valarray](../standard-library/valarray-class.md#op_at)**\<Type>** bir nesne için bir argüman olarak göründüğünde oluşturulur. Üst valarray seçilen alt kümesini belirten depolanan değerler şunlardır:

- Valarray bir başlangıç indeksi.

- Toplam uzunluk veya dilimdeki öğe sayısı.

- Valarray öğelerinin sonraki endeksleri arasında bir adım veya mesafe.

Bir dilim tarafından tanımlanan küme sabit bir valarray alt kümesi ise, dilim yeni bir valarray olduğunu. Dilim tarafından tanımlanan küme sabit olmayan bir valarray alt kümesi ise, dilim orijinal valarray için referans semantiği vardır. Sabit olmayan valarrays için değerlendirme mekanizması zaman ve bellek kazandırır.

Valarrays işlemleri yalnızca dilimler tarafından tanımlanan kaynak ve hedef alt kümeleri farklı ysa ve tüm endeksler geçerliyse garanti edilir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Dilim](#slice)|Eşit mesafede ve belirli `valarray` bir öğede başlayan bir dizi öğeden oluşan bir alt kümesini tanımlar.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Boyutu](#size)|Bir dilimdeki öğe sayısını `valarray`bulur.|
|[Başlatmak](#start)|Bir dilimin başlangıç dizinini `valarray`bulur.|
|[Adım](#stride)|Bir dilimdeki öğeler arasındaki mesafeyi `valarray`bulur.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<valarray>

**Ad alanı:** std

## <a name="slicesize"></a><a name="size"></a>dilim::boyut

Bir valarray bir dilim deki öğelerin sayısını bulur.

```cpp
size_t size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir valarray bir dilim elemanların sayısı.

### <a name="example"></a>Örnek

```cpp
// slice_size.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;
   size_t sizeVA, sizeVAR;

   valarray<int> va ( 20 ), vaResult;
   for ( i = 0 ; i < 20 ; i += 1 )
      va [ i ] =  i+1;

   cout << "The operand valarray va is:\n ( ";
      for ( i = 0 ; i < 20 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   sizeVA = va.size ( );
   cout << "The size of the valarray is: "
        << sizeVA << "." << endl << endl;

   slice vaSlice ( 3 , 6 , 3 );
   vaResult = va [ vaSlice ];

   cout << "The slice of valarray va is vaResult = "
        << "va[slice( 3, 6, 3)] =\n ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaResult [ i ] << " ";
   cout << ")." << endl;

   sizeVAR = vaSlice.size ( );
   cout << "The size of slice vaSlice is: "
        << sizeVAR << "." << endl;
}
```

```Output
The operand valarray va is:
( 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 ).
The size of the valarray is: 20.

The slice of valarray va is vaResult = va[slice( 3, 6, 3)] =
( 4 7 10 13 16 19 ).
The size of slice vaSlice is: 6.
```

## <a name="sliceslice"></a><a name="slice"></a>dilim::dilim

Eşit mesafede ve belirli bir öğeyle başlayan bir dizi öğeden oluşan bir valarray alt kümesini tanımlar.

```cpp
slice();

slice(
    size_t _StartIndex,
    size_t _Len,
    size_t stride);
```

### <a name="parameters"></a>Parametreler

*_StartIndex*\
Alt kümedeki ilk öğenin valarray dizini.

*_Len*\
Alt kümedeki öğe sayısı.

*Adım*\
Alt kümedeki öğeler arasındaki uzaklık.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan oluşturucu başlangıç dizini, toplam uzunluk ve adım için sıfırları depolar. İkinci yapıcı, başlangıç indeksi için *_StartIndex,* toplam uzunluk için *_Len* ve adım için *adım* depolar.

### <a name="remarks"></a>Açıklamalar

Adım olumsuz olabilir.

### <a name="example"></a>Örnek

```cpp
// slice_ctor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 20 ), vaResult;
   for ( i = 0 ; i < 20 ; i+=1 )
      va [ i ] =  2 * (i + 1 );

   cout << "The operand valarray va is:\n( ";
      for ( i = 0 ; i < 20 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   slice vaSlice ( 1 , 7 , 3 );
   vaResult = va [ vaSlice ];

   cout << "\nThe slice of valarray va is vaResult:"
        << "\nva[slice( 1, 7, 3)] = ( ";
      for ( i = 0 ; i < 7 ; i++ )
         cout << vaResult [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The operand valarray va is:
( 2 4 6 8 10 12 14 16 18 20 22 24 26 28 30 32 34 36 38 40 ).

The slice of valarray va is vaResult:
va[slice( 1, 7, 3)] = ( 4 10 16 22 28 34 40 ).
```

## <a name="slicestart"></a><a name="start"></a>dilim::başlat

Bir valarray bir dilim başlangıç dizini bulur.

```cpp
size_t start() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir valarray bir dilim başlangıç dizini.

### <a name="example"></a>Örnek

```cpp
// slice_start.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;
   size_t startVAR;

   valarray<int> va ( 20 ), vaResult;
   for ( i = 0 ; i < 20 ; i += 1 )
      va [ i ] = i+1;

   cout << "The operand valarray va is:\n ( ";
      for ( i = 0 ; i < 20 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   slice vaSlice ( 3 , 6 , 3 );
   vaResult = va [ vaSlice ];

   cout << "The slice of valarray va is vaResult = "
        << "va[slice( 3, 6, 3)] =\n ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaResult [ i ] << " ";
   cout << ")." << endl;

   startVAR = vaSlice.start ( );
   cout << "The start index of slice vaSlice is: "
        << startVAR << "." << endl;
}
```

```Output
The operand valarray va is:
( 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 ).
The slice of valarray va is vaResult = va[slice( 3, 6, 3)] =
( 4 7 10 13 16 19 ).
The start index of slice vaSlice is: 3.
```

## <a name="slicestride"></a><a name="stride"></a>dilim::adım

Bir valarray bir dilim elemanları arasındaki mesafeyi bulur.

```cpp
size_t stride() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir valarray bir dilim elemanları arasındaki mesafe.

### <a name="example"></a>Örnek

```cpp
// slice_stride.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;
   size_t strideVAR;

   valarray<int> va ( 20 ), vaResult;
   for ( i = 0 ; i < 20 ; i += 1 )
      va [ i ] =  3 * ( i + 1 );

   cout << "The operand valarray va is:\n ( ";
      for ( i = 0 ; i < 20 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   slice vaSlice ( 4 , 5 , 3 );
   vaResult = va [ vaSlice ];

   cout << "The slice of valarray va is vaResult = "
        << "va[slice( 4, 5, 3)] =\n ( ";
      for ( i = 0 ; i < 5 ; i++ )
         cout << vaResult [ i ] << " ";
   cout << ")." << endl;

   strideVAR = vaSlice.stride ( );
   cout << "The stride of slice vaSlice is: "
        << strideVAR << "." << endl;
}
```

```Output
The operand valarray va is:
( 3 6 9 12 15 18 21 24 27 30 33 36 39 42 45 48 51 54 57 60 ).
The slice of valarray va is vaResult = va[slice( 4, 5, 3)] =
( 15 24 33 42 51 ).
The stride of slice vaSlice is: 3.
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
