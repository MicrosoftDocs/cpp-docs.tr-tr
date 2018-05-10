---
title: slice sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- valarray/std::slice
- valarray/std::slice::size
- valarray/std::slice::start
- valarray/std::slice::stride
dev_langs:
- C++
helpviewer_keywords:
- std::slice [C++]
- std::slice [C++], size
- std::slice [C++], start
- std::slice [C++], stride
ms.assetid: 00f0b03d-d657-4b81-ba53-5a9034bb2bf2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d17dc3e53504add2507617c95439fa7d32565a53
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="slice-class"></a>slice Sınıfı

Tek boyutlu bir üst valarray kümelerine tanımlamak için kullanılan valarray için yardımcı sınıfı. Bir valarray iki boyutlu bir matris bir dizinin tüm öğeleri olarak kabul edilir, dilim iki boyutlu dizi dışında bir boyuttaki bir vektör ayıklar.

## <a name="remarks"></a>Açıklamalar

Türünde bir nesne niteleyen parametreleri sınıfı depolar [slice_array](../standard-library/slice-array-class.md) sınıfın bir nesnesi için bağımsız değişken olarak bir nesne sınıfı dilimin görüntülendiğinde, bir valarray alt dolaylı olarak oluşturulan [valarray ](../standard-library/valarray-class.md#op_at)  **\<Türü >**. Üst valarray Seçili alt belirtin depolanan değerleri şunlardır:

- Valarray bir başlangıç dizini.

- Bir toplam uzunluğu veya dilim öğe sayısı.

- Bir adım veya valarray'ndaki öğelerin sonraki dizinler arasındaki uzaklığı.

Bir dilim tarafından tanımlanan bir sabit valarray alt kümesidir, dilim yeni valarray olur. Bir dilim tarafından tanımlanan alt kümesini nonconstant valarray ayarlanırsa, dilim özgün valarray başvuru semantik vardır. Nonconstant valarrays için değerlendirme mekanizması süresi ve bellek kaydeder.

Valarrays işlemleri yalnızca dilimler tarafından tanımlanan kaynak ve hedef alt kümelerini farklıdır ve tüm dizinleri geçerli sağlanır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Dilim](#slice)|Bir alt kümesini tanımlar bir `valarray` bir eşit uzaklıkta olan ve belirtilen bir öğede Başlat öğeleri sayısının oluşur.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Boyutu](#size)|Dilimin öğe sayısını bulur bir `valarray`.|
|[Başlat](#start)|Bir dilimin başlangıç dizinini bulur bir `valarray`.|
|[STRIDE](#stride)|Bir dilimin öğeler arasındaki mesafeyi bulur bir `valarray`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<valarray >

**Namespace:** std

## <a name="size"></a>  Slice::size

Dilimi bir valarray öğe sayısını bulur.

```cpp
size_t size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir valarray dilimin öğe sayısı.

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

## <a name="slice"></a>  Slice::slice

Bir eşit uzaklıkta olan ve belirtilen bir öğede Başlat öğe sayısı oluşan bir valarray kümesini tanımlar.

```cpp
slice();

slice(
    size_t _StartIndex,
    size_t _Len,
    size_t stride);
```

### <a name="parameters"></a>Parametreler

`_StartIndex` Alt ilk öğe valarray dizini.

`_Len` Alt öğe sayısı.

`stride` Alt öğeler arasındaki uzaklığı.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan Oluşturucu sıfır başlangıç dizini, toplam uzunluğu ve STRIDE depolar. İkinci oluşturucu depoları `_StartIndex` başlangıç dizini için `_Len` toplam uzunluğu ve `stride` STRIDE için.

### <a name="remarks"></a>Açıklamalar

STRIDE negatif olabilir.

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

## <a name="start"></a>  Slice::Start

Bir valarray dilimin başlangıç dizinini bulur.

```cpp
size_t start() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir valarray dilimin başlangıç dizini.

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

## <a name="stride"></a>  Slice::stride

Bir valarray dilimin öğeler arasındaki mesafeyi bulur.

```cpp
size_t stride() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir valarray dilimin öğeler arasındaki uzaklığı.

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

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
