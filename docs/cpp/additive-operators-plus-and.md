---
description: 'Daha fazla bilgi edinin: toplama Işleçleri: + ve-'
title: 'Ek İşleçler: + and -'
ms.date: 11/04/2016
f1_keywords:
- +
- '-'
helpviewer_keywords:
- operators [C++], addition
- subtraction operator [C++], additive operators
- + operator [C++], additive operators
- additive operators [C++]
- arithmetic operators [C++], additive operators
- '- operator [C++], additive operators in C++'
ms.assetid: d4afafe7-e201-4c69-a649-37f17756e784
ms.openlocfilehash: f87a8682b6f282668c168262cd28230745cb4402
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288379"
---
# <a name="additive-operators--and--"></a>Ek İşleçler: + and -

## <a name="syntax"></a>Syntax

```
expression + expression
expression - expression
```

## <a name="remarks"></a>Açıklamalar

Toplama işleçleri şunlardır:

- Toplama ( **+** )

- Çıkarma ( **-** )

Bu ikili işleçlerde soldan sağa ilişkilendirilebilirlik vardır.

Adal işleçleri aritmetik veya işaretçi türündeki işlenenleri alır. Toplama () işlecinin sonucu, **+** işlenenlerinin toplamıdır. Çıkarma ( **-** ) işlecinin sonucu işlenen arasındaki farktır. İşlenenlerinin bir veya her ikisi işaretçiler ise, işlevlere değil, nesnelere işaretçiler olmalıdır. Her iki işlenen de işaretçiler ise, her ikisi de aynı dizideki nesnelere işaretçiler olmadığı takdirde sonuçlar anlamlı değildir.

Toplama işleçleri *Aritmetik*, *integral* ve *skaler* türlerin işlenenlerini alır. Bunlar aşağıdaki tabloda tanımlanmıştır.

### <a name="types-used-with-additive-operators"></a>Toplamalı Işleçlerle kullanılan türler

|Tür|Anlamı|
|----------|-------------|
|*tiğinin*|Integral ve kayan türler topluca "aritmetik" türler olarak adlandırılır.|
|*tam*|Her boyuttaki char ve int (Long, short) ve numaralandırmalar türleri "integral" türleridir.|
|*ler*|Skalar işlenenler, aritmetik ya da işaretçi türünün işlenenleri.|

Bu işleçler için yasal birleşimler şunlardır:

*Aritmetik*  +  *Aritmetik*

*skaler*  +  *integral*

*integral*  +  *skaler*

*Aritmetik*  -  *Aritmetik*

*skaler*  -  *skaler*

Toplama ve çıkarma işlemlerinin eşdeğer işlemler olmadığına unutmayın.

Her iki işlenen de aritmetik bir tür ise, [Standart dönüştürmelerde](standard-conversions.md) kapsanan dönüştürmeler işlenenlere uygulanır ve sonuç, dönüştürülmüş tür olur.

## <a name="example"></a>Örnek

```cpp
// expre_Additive_Operators.cpp
// compile with: /EHsc
#include <iostream>
#define SIZE 5
using namespace std;
int main() {
   int i = 5, j = 10;
   int n[SIZE] = { 0, 1, 2, 3, 4 };
   cout  << "5 + 10 = " << i + j << endl
         << "5 - 10 = " << i - j << endl;

   // use pointer arithmetic on array

   cout << "n[3] = " << *( n + 3 ) << endl;
}
```

## <a name="pointer-addition"></a>İşaretçi ekleme

Ek bir işlem içinde, işlenenlerden biri nesneleri içeren bir dizinin işaretçisi ise, diğeri tamsayı türünde olmalıdır. Sonuç, özgün işaretçi ile aynı türde ve başka bir dizi öğesine işaret eden bir işaretçidir. Aşağıdaki kod parçası bu kavramı gösterir:

```cpp
short IntArray[10]; // Objects of type short occupy 2 bytes
short *pIntArray = IntArray;

for( int i = 0; i < 10; ++i )
{
    *pIntArray = i;
    cout << *pIntArray << "\n";
    pIntArray = pIntArray + 1;
}
```

`pIntArray` öğesine tamsayı değeri olarak 1 eklenmiş olmasına rağmen, "adrese 1 ekle" anlamına gelmez; daha çok, "işaretçiyi dizideki sonraki nesneye işaret edecek şekilde ayarla" anlamına gelir, bu da 2 bayt (veya `sizeof( int )`) uzakta olur.

> [!NOTE]
> `pIntArray = pIntArray + 1` formunun kodu C++ programlarında nadiren bulunur; arttırma yapmak için şu formlar tercih edilir: `pIntArray++` veya `pIntArray += 1`.

## <a name="pointer-subtraction"></a>İşaretçi çıkarması

Her iki işlenen de işaretçiyse, çıkarma işleminin sonucu işlenenler arasındaki farktır (dizi öğelerinde). Çıkarma ifadesi, türün işaretli bir integral sonucunu `ptrdiff_t` (Standart içerme dosyasında tanımlanır \<stddef.h> ) verir.

İşlenenlerden biri, ikinci işlenen olduğu takdirde integral türünde olabilir. Çıkarma işleminin sonucu, orijinal işaretçiyle aynı türdendir. Çıkarma değeri, (*n*  -  *i*). Array öğesinin bir işaretçisidir; burada *n* , özgün işaretçinin gösterdiği öğe ve ikinci işlenenin integral değeridir. 

## <a name="see-also"></a>Ayrıca bkz.

[Ikili Işleçlere sahip ifadeler](../cpp/expressions-with-binary-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C eklenebilir Işleçler](../c-language/c-additive-operators.md)
