---
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
ms.openlocfilehash: 2601debb0a21c4ab9cdcedb25b26085a1aff0a1b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370202"
---
# <a name="additive-operators--and--"></a>Ek İşleçler: + and -

## <a name="syntax"></a>Sözdizimi

```
expression + expression
expression - expression
```

## <a name="remarks"></a>Açıklamalar

Katkı işleçleri şunlardır:

- İlave (**+**)

- Çıkarma (**-**)

Bu ikili işleçlerde soldan sağa ilişkilendirilebilirlik vardır.

Katkı işleçleri aritmetik veya işaretçi türlerinin operands alır. İlave (**+**) işlecinin sonucu operandların toplamıdır. Çıkarma (**-**) işlecinin sonucu operandlar arasındaki farktır. Operandlardan biri veya her ikisi işaretçiyse, işlevlere değil nesnelere işaretçiler olmalıdır. Her iki operands işaretçiler iseniz, her ikisi de aynı dizideki nesnelerin işaretçileri olmadığı sürece sonuçlar anlamlı değildir.

Katkı işleçleri *aritmetik,* *integral*ve *skaler* türlerin operands alır. Bunlar aşağıdaki tabloda tanımlanır.

### <a name="types-used-with-additive-operators"></a>Katkı Operatörlerinde Kullanılan Tipler

|Tür|Anlamı|
|----------|-------------|
|*Aritmetik*|İntegral ve kayan türleri topluca "aritmetik" türleri olarak adlandırılır.|
|*Integral*|Tüm boyutların (uzun, kısa) ve numaralandırmalarının char ve int türleri "integral" türleridir.|
|*Skalar*|Skaler operands aritmetik veya işaretçi türünde operands vardır.|

Bu işleçler için yasal kombinasyonlar şunlardır:

*aritmetik* + *aritmetik*

*skaler* + *integral*

*integral* + *skaler*

*aritmetik* - *aritmetik*

*skaler* - *skaler*

Ekleme ve çıkarmanın eşdeğer işlemler olmadığını unutmayın.

Her iki operandarit türündeise, [Standart Dönüşümler](standard-conversions.md) kapsamındaki dönüşümler operandlara uygulanır ve sonuç dönüştürülmüş türe ait olur.

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

Her iki işlenen de işaretçiyse, çıkarma işleminin sonucu işlenenler arasındaki farktır (dizi öğelerinde). Çıkarma ifadesi, türün `ptrdiff_t` imzalı bir integral sonucu verir (standartta tanımlanan dosya \<stddef.h> içerir).

İşlenenlerden biri, ikinci işlenen olduğu takdirde integral türünde olabilir. Çıkarma işleminin sonucu, orijinal işaretçiyle aynı türdendir. Çıkarma nın değeri , (*n* - *i*)th dizi öğesine işaretçidir, *burada n* özgün işaretçi tarafından işaret edilen öğedir ve *i* ikinci operandUn integral değeridir.

## <a name="see-also"></a>Ayrıca bkz.

[İkili İşleçli İfadeler](../cpp/expressions-with-binary-operators.md)<br/>
[C++ Yerleşik İşleçler, Öncelik ve İlişkisellik](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C Katkı Operatörleri](../c-language/c-additive-operators.md)
