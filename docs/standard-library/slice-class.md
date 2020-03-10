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
ms.openlocfilehash: 830e345eb7522cef44dbf6e727a976fb79c1e081
ms.sourcegitcommit: 49cf365176557456f56c994e06ea1a38f73e938b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2020
ms.locfileid: "78937436"
---
# <a name="slice-class"></a>slice Sınıfı

Bir üst valarray 'ın tek boyutlu alt kümelerini tanımlamak için kullanılan valarray için yardımcı program sınıfı. Bir valarray, bir dizideki tüm öğelerle iki boyutlu bir matris olarak kabul edilir, dilim iki boyutlu diziden birindeki bir vektör ayıklar.

## <a name="remarks"></a>Açıklamalar

Sınıfı, sınıf diliminin bir nesnesi [valarray](../standard-library/valarray-class.md#op_at) **\<türü >** bir nesne için bağımsız değişken olarak göründüğünde bir valarray alt kümesi dolaylı olarak oluşturulur [slice_array](../standard-library/slice-array-class.md) bir nesneyi niteleyen parametreleri depolar. Üst valarray seçili alt kümeyi belirten depolanan değerler şunları içerir:

- Valarray başlangıç dizini.

- Dilimdeki Toplam uzunluk veya öğe sayısı.

- Valarray içindeki öğelerin sonraki dizinleri arasında bir ilerleme veya uzaklık.

Bir dilim tarafından tanımlanan küme bir sabit valarray alt kümesiyse, dilim yeni bir valarray. Bir dilim tarafından tanımlanan küme sabit olmayan bir valarray alt kümesiyse, dilimin özgün valarray başvuru semantiğini vardır. Sabit olmayan valarışın için değerlendirme mekanizması zaman ve bellek tasarrufu sağlar.

Valarışın üzerinde işlemler yalnızca, dilimler tarafından tanımlanan kaynak ve hedef alt kümeleri birbirinden farklı olduğunda ve tüm dizinler geçerliyse garanti edilir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|['ın](#slice)|Eşit uzaklıkta olan ve belirtilen bir öğede başlayan bir dizi öğeden oluşan bir `valarray` alt kümesini tanımlar.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[boyutla](#size)|`valarray`bir dilimdeki öğelerin sayısını bulur.|
|[start](#start)|Bir `valarray`diliminin başlangıç dizinini bulur.|
|[adım](#stride)|`valarray`bir dilimdeki öğeler arasındaki mesafeyi bulur.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<valarray >

**Ad alanı:** std

## <a name="size"></a>Slice:: size

Valarray 'in bir dilimdeki öğe sayısını bulur.

```cpp
size_t size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir valarray 'nin bir dilimdeki öğe sayısı.

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

## <a name="slice"></a>Slice:: Slice

Eşit uzaklıkta olan ve belirtilen bir öğede başlayan bir dizi öğeden oluşan bir valarray alt kümesini tanımlar.

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
Alt kümedeki öğelerin sayısı.

*ilerleme*\
Alt kümedeki öğeler arasındaki uzaklık.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan Oluşturucu başlangıç dizini, toplam uzunluğu ve ilerleme için sıfırları depolar. İkinci Oluşturucu başlangıç dizini için *_StartIndex* depolar, Toplam uzunluk için *_Len* ve ilerleme için *ilerleme* .

### <a name="remarks"></a>Açıklamalar

Bu adım negatif olabilir.

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

## <a name="start"></a>Slice:: Start

Bir valarray diliminin başlangıç dizinini bulur.

```cpp
size_t start() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir valarray diliminin başlangıç dizini.

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

## <a name="stride"></a>Slice:: ilerme

Bir valarray Slice içindeki öğeler arasındaki mesafeyi bulur.

```cpp
size_t stride() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir valarray Slice içindeki öğeler arasındaki uzaklık.

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
