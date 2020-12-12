---
description: 'Daha fazla bilgi edinin: &lt; valarray &gt; işleçleri'
title: '&lt;valarray &gt; işleçleri'
ms.date: 03/27/2019
f1_keywords:
- valarray/std::operator!=
- valarray/std::operator%
- valarray/std::operator&amp;
- valarray/std::operator&amp;&amp;
- valarray/std::operator&gt;
- valarray/std::operator&gt;&gt;
- valarray/std::operator&gt;=
- valarray/std::operator&lt;
- valarray/std::operator&lt;&lt;
- valarray/std::operator&lt;=
- valarray/std::operator*
- valarray/std::operator+
- valarray/std::operator-
- valarray/std::operator/
- valarray/std::operator==
- valarray/std::operator^
- valarray/std::operator|
- valarray/std::operator||
ms.assetid: 8a53562c-90ab-4eb3-85d3-ada5259d90b0
helpviewer_keywords:
- std::operator!= (valarray), std::operator&amp; (valarray)
- std::operator&amp;&amp; (valarray)
- std::operator&gt; (valarray)
- std::operator&gt;&gt; (valarray)
- std::operator&gt;= (valarray)
- std::operator&lt; (valarray)
- std::operator&lt;&lt; (valarray)
- std::operator&lt;= (valarray), std::operator== (valarray)
ms.openlocfilehash: 574d0b67910b79941431f3ee8c1f9e3118de35a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321471"
---
# <a name="ltvalarraygt-operators"></a>&lt;valarray &gt; işleçleri

## <a name="operator"></a><a name="op_neq"></a> işleç! =

Eşit olarak boyutlandırılmış iki valarışın öğesine karşılık gelen öğelerin eşit olup olmadığını veya bir valarray öğesinin tüm öğelerinin belirtilen değerin eşit olmadığını sınar.

```cpp
template <class Type>
valarray<bool>
operator!=(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator!=(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator!=(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Öğeleri eşitsizlik için test edilecek olan iki valarışın ilki.

*Right*\
Öğelerinin eşitsizlik için test edileceği iki valarışın ikinci adı.

### <a name="return-value"></a>Dönüş Değeri

Boolean değerlerinin bir valarray, her biri:

- **`true`** karşılık gelen öğeler eşit değilse.

- **`false`** karşılık gelen öğeler eşit değilse.

### <a name="remarks"></a>Açıklamalar

İlk şablon işleci, öğelerinin her biri olan [ \<bool> valarray](../standard-library/valarray-bool-class.md)sınıfının bir nesnesini döndürür `I` `left[I] != right[I]` .

İkinci şablon işleci öğesi içinde depolanır `I` `left[I] != right` .

Üçüncü şablon işleci öğesi içinde depolanır `I` `left != right[I]` .

### <a name="example"></a>Örnek

```cpp
// valarray_op_ne.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL != vaR );
   cout << "The element-by-element result of "
        << "the not equal comparison test is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the not equal comparison test is the
valarray: ( 0 0 1 0 1 0 1 0 1 0 ).
```

## <a name="operator"></a><a name="op_mod"></a> işlecinde

İki eşit ölçekli valarışın karşılık gelen öğelerin bölünmesinin veya bir valarray belirtilen bir değere göre bölünmesinin veya bir valarray tarafından belirtilen bir değeri bölen geri kalanını edinir.

```cpp
template <class Type>
valarray<Type>
operator%(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator%(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator%(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Başka bir değer veya valarray bölünecek olan bölünen olarak işlev gören bir değer veya valarray.

*Right*\
Bölen olarak işlev gören ve başka bir değeri veya valarray ayıran bir değer veya valarray.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri, *sağdan* *sola* bölünen öğe temelinde kalanları olan bir valarray.

### <a name="example"></a>Örnek

```cpp
// valarray_op_rem.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 6 ), vaR ( 6 );
   valarray<int> vaREM ( 6 );
   for ( i = 0 ; i < 6 ; i += 2 )
      vaL [ i ] =  53;
   for ( i = 1 ; i < 6 ; i += 2 )
      vaL [ i ] =  -67;
   for ( i = 0 ; i < 6 ; i++ )
      vaR [ i ] =  3*i+1;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaREM = ( vaL % vaR );
   cout << "The remainders from the element-by-element "
        << "division is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaREM [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 53 -67 53 -67 53 -67 ).
The initial Right valarray is: ( 1 4 7 10 13 16 ).
The remainders from the element-by-element division is the
valarray: ( 0 -3 4 -7 1 -3 ).
```

## <a name="operatoramp"></a><a name="op_amp"></a> işlecinde&amp;

İki eşit ölçekli valarışın veya bir valarray ile belirtilen öğe türü arasında karşılık gelen öğeler arasında bit düzeyinde **ve** arasında bir değer alır.

```cpp
template <class Type>
valarray<Type>
operator&(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator&(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator&(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
İlgili öğeleri, `AND` bir valarray öğesinin her öğesiyle bit düzeyinde birleştirilecek olan öğe türü bit düzeyinde veya belirtilen bir değerle birleştirilecek olan iki valarışın ilki.

*Right*\
İlgili öğeleri, `AND` bir valarray öğesinin her öğesiyle bit düzeyinde birleştirilecek bir öğe türü bit düzeyinde veya belirtilen değerle birleştirilecek olan iki valarışın ikinci değeri.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri, *sol* ve *sağ* bit seviyesinde ve işleminin öğe temelinde birleşimi olan bir valarray.

### <a name="remarks"></a>Açıklamalar

Bit düzeyinde bir işlem yalnızca,, **`char`** **`int`** **`float`** **`double`** **longdouble**, **`void`** , **`bool`** veya diğer daha karmaşık veri türlerinde değil, BITS içindeki ve veri türlerindeki ve varyantları işlemek için kullanılabilir.

Bit düzeyinde `AND` mantıksal olarak aynı Truth tablosu vardır, `AND` ancak tek tek bitlerin düzeyindeki veri türü için geçerli olur. [İşleç&&](#op_amp_amp) , öğe düzeyinde uygulanır, sıfır olmayan tüm değerler doğru olarak ve sonuç Boolean değerlerinin bir valarray. Bit düzeyinde `AND` [işleç&](#op_amp), buna karşılık olarak, bit düzeyinde işlemin sonucuna bağlı olarak 0 veya 1 ' den farklı değerlerin valarray oluşmasına neden olabilir.

### <a name="example"></a>Örnek

```cpp
// valarray_op_bitand.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<int> vaBWA ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i+1;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaBWA = ( vaL & vaR );
   cout << "The element-by-element result of "
        << "the bitwise operator & is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaBWA [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is:  ( 0 2 0 4 0 6 0 8 0 10 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the bitwise operator & is the
valarray: ( 0 0 0 0 0 4 0 0 0 8 ).
```

## <a name="operatorampamp"></a><a name="op_amp_amp"></a> işlecinde&amp;&amp;

İki eşit ölçekli valarışın karşılık gelen öğeleri veya bir valarray ile valarray öğesinin öğe türünün belirtilen değeri arasında mantıksal **ve** arasında bir değer alır.

```cpp
template <class Type>
valarray<bool>
operator&&(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator&&(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator&&(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
İlgili öğeleri, `AND` bir valarray öğesinin her öğesiyle birleştirilecek olan öğe türünün mantıksal veya belirtilen değeri ile birleştirilecek olan iki valarışın ilki.

*Right*\
İlgili öğeleri `AND` bir valarray öğesinin her öğesiyle birleştirilecek olan öğe türünün mantıksal veya belirtilen değeriyle birleştirilecek olan iki valarışın ikinci değeri.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri bool türünde olan ve `AND` *sol* ve *sağ* mantıksal işleminin öğe temelinde birleşimi olan bir valarray.

### <a name="remarks"></a>Açıklamalar

Mantıksal `ANDoperator&&` bir öğe düzeyinde uygulanır, sıfır olmayan tüm değerler doğru olarak ve sonuç Boolean değerlerinin bir valarray. Bit düzeyinde `AND` işlemin sonucuna bağlı olarak, [işleç&,, işlecin](#op_amp)bit düzeyinde sürümü, 0 veya 1 ' den farklı değerlerin valarray oluşmasına neden olabilir.

### <a name="example"></a>Örnek

```cpp
// valarray_op_logand.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaLAA ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is:  ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaLAA = ( vaL && vaR );
   cout << "The element-by-element result of "
        << "the logical AND operator&& is the\n"
        << "valarray: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaLAA [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the logical AND operator&& is the
valarray: ( 0 0 0 1 0 1 0 1 0 1 ).
```

## <a name="operatorgt"></a><a name="op_gt"></a> işlecinde&gt;

Bir valarray öğelerinin eşit boyutlu bir valarray öğelerinden büyük olup olmadığını veya bir valarray tüm öğelerinin belirtilen değerden büyük veya küçük olup olmadığını sınar.

```cpp
template <class Type>
valarray<bool>
operator>(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator>(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator>(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Öğeleri karşılaştırılacak olan iki valarışın veya bir valarray öğesinin her öğesiyle Karşılaştırılacak belirtilen bir değer.

*Right*\
Öğeleri Karşılaştırılacak iki valarışın veya bir valarray öğesinin her öğesiyle Karşılaştırılacak belirtilen bir değer.

### <a name="return-value"></a>Dönüş Değeri

Boolean değerlerinin bir valarray, her biri:

- **`true`***sol* öğe veya değer karşılık gelen *sağ* öğe veya değerden daha büyükse.

- **`false`***sol* öğe veya değer karşılık gelen *sağ* öğe veya değerden daha büyük değilse.

### <a name="remarks"></a>Açıklamalar

İki valarışın öğe sayısı eşitse, sonuç tanımsızdır.

### <a name="example"></a>Örnek

```cpp
// valarray_op_gt.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i - 1;

   cout << "The initial Left valarray is: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL > vaR );
   cout << "The element-by-element result of "
        << "the greater than comparison test is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( -1 0 1 2 3 4 5 6 7 8 ).
The element-by-element result of the greater than comparison test is the
valarray: ( 1 1 0 1 0 1 0 1 0 1 ).
```

## <a name="operatorgt"></a><a name="op_gt_eq"></a> işlecinde&gt;=

Bir valarray öğelerinin eşit boyutlu bir valarray öğesinden büyük veya ona eşit olup olmadığını ya da bir valarray öğelerinin, belirtilen bir değerden büyük veya ona eşit veya ondan büyük veya ona eşit olup olmadığını sınar.

```cpp
template <class Type>
valarray<bool>
operator>=(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator>=(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator>=(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Öğeleri karşılaştırılacak olan iki valarışın veya bir valarray öğesinin her öğesiyle Karşılaştırılacak belirtilen bir değer.

*Right*\
Öğeleri Karşılaştırılacak iki valarışın veya bir valarray öğesinin her öğesiyle Karşılaştırılacak belirtilen bir değer.

### <a name="return-value"></a>Dönüş Değeri

Boolean değerlerinin bir valarray, her biri:

- **`true`***sol* öğe veya değer, karşılık gelen *sağ* öğe veya değerden büyükse veya buna eşitse.

- **`false`***sol* öğe veya değer karşılık gelen *sağ* öğe veya değerden küçükse.

### <a name="remarks"></a>Açıklamalar

İki valarışın öğe sayısı eşitse, sonuç tanımsızdır.

### <a name="example"></a>Örnek

```cpp
// valarray_op_ge.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i - 1;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL >= vaR );
   cout << "The element-by-element result of "
        << "the greater than or equal test is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( -1 0 1 2 3 4 5 6 7 8 ).
The element-by-element result of the greater than or equal test is the
valarray: ( 1 1 0 1 0 1 0 1 0 1 ).
```

## <a name="operatorgtgt"></a><a name="op_gt_gt"></a> işlecinde&gt;&gt;

Bir valarray öğesinin her öğesi için bitleri, belirtilen sayıda konum veya bir ikinci valarray tarafından belirtilen öğe temelinde bir miktar ile sağa kaydırır.

```cpp
template <class Type>
valarray<Type>
operator>>(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator>>(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator>>(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Kaydırılan değer veya öğeleri kaydırılacağı valarray.

*Right*\
Öğesi, sağ SHIFT veya valarray öğelerinin öğe temelinde sağ SHIFT miktarını belirten değer.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri belirtilen miktarda sağa kaydırılan bir valarray.

### <a name="remarks"></a>Açıklamalar

İmzalı sayıların işaretleri korunur.

### <a name="example"></a>Örnek

```cpp
// valarray_op_rs.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   valarray<int> vaNE ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  64;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -64;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL >> vaR );
   cout << "The element-by-element result of "
        << "the right shift is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 64 -64 64 -64 64 -64 64 -64 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the right shift is the
valarray: ( 64 -32 16 -8 4 -2 1 -1 ).
```

## <a name="operatorlt"></a><a name="op_lt"></a> işlecinde&lt;

Bir valarray öğelerinin eşit boyutlu bir valarray öğelerinden daha küçük olup olmadığını veya bir valarray tüm öğelerinin belirtilen değerden büyük veya küçük olup olmadığını sınar.

```cpp
template <class Type>
valarray<bool>
operator<(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator<(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator<(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Öğeleri karşılaştırılacak olan iki valarışın veya bir valarray öğesinin her öğesiyle Karşılaştırılacak belirtilen bir değer.

*Right*\
Öğeleri Karşılaştırılacak iki valarışın veya bir valarray öğesinin her öğesiyle Karşılaştırılacak belirtilen bir değer.

### <a name="return-value"></a>Dönüş Değeri

Boolean değerlerinin bir valarray, her biri:

- **`true`***sol* öğe veya değer karşılık gelen *sağ* öğe veya değerden küçükse.

- **`false`***sol* öğe veya değer karşılık gelen *sağ* öğe veya değerden küçük değilse.

### <a name="remarks"></a>Açıklamalar

Öğe sayısı iki valarışın eşitse, sonuç tanımsızdır.

### <a name="example"></a>Örnek

```cpp
// valarray_op_lt.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL < vaR );
   cout << "The element-by-element result of "
        << "the less-than comparson test is the\n"
        << "valarray: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the less-than comparson test is the
valarray: ( 0 0 1 0 1 0 1 0 1 0 ).
```

## <a name="operatorlt"></a><a name="op_lt_eq"></a> işlecinde&lt;=

Bir valarray öğelerinin eşit boyutlu bir valarray öğesinden küçük veya ona eşit olup olmadığını ya da bir valarray öğelerinin, belirtilen bir değerden büyük veya ona eşit veya ondan daha büyük veya ona eşit olup olmadığını sınar.

```cpp
template <class Type>
valarray<bool>
operator<=(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator<=(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator<=(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Öğeleri karşılaştırılacak olan iki valarışın veya bir valarray öğesinin her öğesiyle Karşılaştırılacak belirtilen bir değer.

*Right*\
Öğeleri Karşılaştırılacak iki valarışın veya bir valarray öğesinin her öğesiyle Karşılaştırılacak belirtilen bir değer.

### <a name="return-value"></a>Dönüş Değeri

Boolean değerlerinin bir valarray, her biri:

- **`true`***sol* öğe veya değer, karşılık gelen *sağ* öğe veya değerden küçük veya bu değere eşit ise.

- **`false`***sol* öğe veya değer karşılık gelen *sağ* öğe veya değerden daha büyükse.

### <a name="remarks"></a>Açıklamalar

Öğe sayısı iki valarışın eşitse, sonuç tanımsızdır.

### <a name="example"></a>Örnek

```cpp
// valarray_op_le.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i - 1;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL <= vaR );
   cout << "The element-by-element result of "
        << "the less than or equal test is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( -1 0 1 2 3 4 5 6 7 8 ).
The element-by-element result of the less than or equal test is the
valarray: ( 0 0 1 0 1 0 1 0 1 0 ).
```

## <a name="operatorltlt"></a><a name="op_lt_lt"></a> işlecinde&lt;&lt;

Sol, bir valarray öğesinin her öğesi için bitleri belirtilen sayıda konum veya bir ikinci valarray tarafından belirtilen öğe temelinde bir sayı ile kaydırır.

```cpp
template <class Type>
valarray<Type>
operator<<(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator<<(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator<<(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Kaydırılan değer veya öğeleri kaydırılacağı valarray.

*Right*\
Öğeleri, sol SHIFT veya valarray öğelerinin öğe temelinde sol SHIFT miktarını belirten değer.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri belirtilen miktarda sola kaydırılan bir valarray.

### <a name="remarks"></a>Açıklamalar

İmzalı sayıların işaretleri korunur.

### <a name="example"></a>Örnek

```cpp
// valarray_op_ls.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   valarray<int> vaNE ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  1;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL << vaR );
   cout << "The element-by-element result of "
        << "the left shift is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 1 -1 1 -1 1 -1 1 -1 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the left shift is the
valarray: ( 1 -2 4 -8 16 -32 64 -128 ).
```

## <a name="operator"></a><a name="op_star"></a> işlecinde

İki eşit ölçekli valarışın veya valarray belirtilen bir değer arasındaki karşılık gelen öğeler arasında öğe temelinde ürün edinir.

```cpp
template <class Type>
valarray<Type>
operator*(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator*(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator*(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Öğelerinin çarpılacağı veya belirtilen değerin bir valarray öğesinin her öğesiyle çarpılacağı iki valarışın ilki.

*Right*\
Öğelerinin çarpılacağı veya belirtilen değerin bir valarray öğesinin her öğesiyle çarpılacağı iki valarışın ikinci değeri.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri *sol* ve *sağ* öğe temelinde olan bir valarray.

### <a name="example"></a>Örnek

```cpp
// valarray_op_eprod.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   valarray<int> vaNE ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  2;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL * vaR );
   cout << "The element-by-element result of "
        << "the multiplication is the\n"
        << "valarray: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the multiplication is the
valarray: ( 0 -1 4 -3 8 -5 12 -7 ).
```

## <a name="operator"></a><a name="op_add"></a> işleç +

İki eşit ölçekli valarışın veya valarray belirtilen bir değer arasındaki karşılık gelen öğeler arasındaki öğe temelinde toplamı edinir.

```cpp
template <class Type>
valarray<Type>
operator+(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator+(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator+(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Öğeleri eklenecek olan iki valarışının ilki veya bir valarray öğesinin her öğesiyle birlikte eklenmek üzere belirtilen bir değer.

*Right*\
Öğeleri eklenecek iki valarışının ikinci değeri veya bir valarray öğesinin her öğesiyle birlikte eklenmek üzere belirtilen bir değer.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri *sol* ve *sağ* öğesinin öğe temelinde toplamı olan bir valarray.

### <a name="example"></a>Örnek

```cpp
// valarray_op_esum.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   valarray<int> vaNE ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  2;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL + vaR );
   cout << "The element-by-element result of "
        << "the sum is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the sum is the
valarray: ( 2 0 4 2 6 4 8 6 ).
```

## <a name="operator-"></a><a name="operator-"></a> işlecinde

İki eşit ölçekli valarışın veya valarray belirtilen bir değer arasındaki karşılık gelen öğeler arasındaki öğe temelinde farkı edinir.

```cpp
template <class Type>
valarray<Type>
operator-(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator-(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator-(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Diğer değerlerin veya valarışın, farkı ortaya çıkarılan bir eksilen görevi gören bir değer veya valarray.

*Right*\
Farkı oluşturan diğer değerlerden veya valarışın çıkarılacak olan çıkarılan olarak hizmet veren bir değer veya valarray.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri *sol* ve *sağ* öğesinin öğe temelinde fark olan bir valarray.

### <a name="remarks"></a>Açıklamalar

Çıkarma açıklamak için kullanılan aritmetik terminoloji:

fark = eksilen-çıkarılan

### <a name="example"></a>Örnek

```cpp
// valarray_op_ediff.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   valarray<int> vaNE ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  10;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL - vaR );
   cout << "The element-by-element result of "
        << "the difference is the\n"
        << "valarray: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 10 0 10 0 10 0 10 0 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the difference is the
valarray: ( 10 -1 8 -3 6 -5 4 -7 ).
```

## <a name="operator"></a><a name="op_div"></a> işlecinde

İki eşit ölçekli valarışın veya valarray belirtilen bir değer arasındaki karşılık gelen öğeler arasında öğe temelinde bölüm edinir.

```cpp
template <class Type>
valarray<Type>
operator/(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator/(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator/(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Başka bir değer veya valarray, bölüm oluşturulurken bölünecek olan bölünen olarak işlev gören bir değer veya valarray.

*Right*\
Bölen olarak işlev gören ve bölümü oluşturan başka bir değeri veya valarray ayıran bir değer veya valarray.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri sol *tarafta* *sola* bölünen öğe temelinde olan bir valarray.

### <a name="remarks"></a>Açıklamalar

Bir bölümü açıklamak için kullanılan aritmetik terminoloji:

Bölüm = bölünen/bölen

### <a name="example"></a>Örnek

```cpp
// valarray_op_equo.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<double> vaL ( 6 ), vaR ( 6 );
   valarray<double> vaNE ( 6 );
   for ( i = 0 ; i < 6 ; i += 2 )
      vaL [ i ] =  100;
   for ( i = 1 ; i < 6 ; i += 2 )
      vaL [ i ] =  -100;
   for ( i = 0 ; i < 6 ; i++ )
      vaR [ i ] =  2*i;

   cout << "The initial Left valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL / vaR );
   cout << "The element-by-element result of "
        << "the quotient is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 100 -100 100 -100 100 -100 ).
The initial Right valarray is: ( 0 2 4 6 8 10 ).
The element-by-element result of the quotient is the
valarray: ( inf -50 25 -16.6667 12.5 -10 ).
```

## <a name="operator"></a><a name="op_eq_eq"></a> işleç = =

Eşit olarak boyutlandırılmış iki valarışın öğesine karşılık gelen öğelerin eşit olup olmadığını veya bir valarray öğesinin tüm öğelerinin belirtilen değere eşit olup olmadığını sınar.

```cpp
template <class Type>
valarray<bool>
operator==(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator==(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator==(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Öğeleri eşitlik için sınanacak olan iki valarışın ilki.

*Right*\
Öğeleri eşitlik için test edilecek olan iki valarışın ikinci adı.

### <a name="return-value"></a>Dönüş Değeri

Boolean değerlerinin bir valarray, her biri:

- **`true`** karşılık gelen öğeler eşitse.

- **`false`** karşılık gelen öğeler eşit değilse.

### <a name="remarks"></a>Açıklamalar

İlk şablon işleci, öğelerinin her biri olan [ \<bool> valarray](../standard-library/valarray-bool-class.md)sınıfının bir nesnesini döndürür `I` `left[I] == right[I]` . İkinci şablon işleci öğesi içinde depolanır `I` `left[I] == right` . Üçüncü şablon işleci öğesi içinde depolanır `I` `left == right[I]` .

### <a name="example"></a>Örnek

```cpp
// valarray_op_eq.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaNE ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial Left valarray is: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaNE = ( vaL == vaR );
   cout << "The element-by-element result of "
        << "the equality comparison test is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the equality comparison test is the
valarray: ( 1 1 0 1 0 1 0 1 0 1 ).
```

## <a name="operator"></a><a name="op_xor"></a> işleç ^

`OR`İki eşit ölçekli valarışın karşılık gelen öğeler arasında bit düzeyinde dışlamalı ( **Xor**) veya bir valarray ile belirtilen öğe türü değeri arasında bir değer alır.

```cpp
template <class Type>
valarray<Type>
operator^(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator^(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator^(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
İlgili öğeleri, bir valarray öğesinin her öğesiyle bit düzeyinde birleştirilecek olan öğe türü bit düzeyinde **Xor** veya belirtilen bir değerle birleştirilecek olan iki valarışının ilki.

*Right*\
İlgili öğeleri, bir valarray öğesinin her öğesiyle bit düzeyinde birleştirilecek olan öğe türünün bit düzeyinde **Xor** veya belirtilen bir değeri ile birleştirilecek iki valarışın ikinci değeri.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri *sol* ve *sağ* bit düzeyinde **Xor** işleminin öğe temelinde birleşimi olan bir valarray.

### <a name="remarks"></a>Açıklamalar

Bit düzeyinde bir işlem,,,, **`char`** **`int`** **`float`** **`double`** **`long double`** **`void`** **`bool`** veya diğer daha karmaşık veri türlerinde değil, yalnızca bitleri ve veri türlerini ve türevlerini işlemek için kullanılabilir.

Bit düzeyinde dışlamalı `OR` ( **Xor**) aşağıdaki semantik anlamları vardır: bit *b* 1 ve *b* 2, *b* 1 **Xor** *b* 2, **`true`** bitlerin tam olarak biri true ise, **`false`** her iki bit de true ise veya her iki bit de doğruysa.

### <a name="example"></a>Örnek

```cpp
// valarray_op_xor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<int> vaLAA ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  1;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  i-1;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  i-1;

   cout << "The initial Left valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaLAA = ( vaL ^ vaR );
   cout << "The element-by-element result of "
        << "the bitwise XOR operator^ is the\n"
        << "valarray: ( ";
           for ( i = 0 ; i < 10 ; i++ )
         cout << vaLAA [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is:  ( 1 0 1 0 1 0 1 0 1 0 ).
The initial Right valarray is: ( 0 0 1 3 3 4 6 6 7 9 ).
The element-by-element result of the bitwise XOR operator^ is the
valarray: ( 1 0 0 3 2 4 7 6 6 9 ).
```

## <a name="operator124"></a><a name="op_or"></a> işleç&#124;

`OR`İki eşit ölçekli valarışın karşılık gelen öğeler arasında bit düzeyinde veya bir valarray ile belirtilen bir değer olan öğe türünü alır.

```cpp
template <class Type>
valarray<Type>
operator|(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<Type>
operator|(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<Type>
operator|(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
İlgili öğeleri, `OR` bir valarray öğesinin her öğesiyle bit düzeyinde birleştirilecek olan öğe türü bit düzeyinde veya belirtilen bir değerle birleştirilecek olan iki valarışın ilki.

*Right*\
İlgili öğeleri, `OR` bir valarray öğesinin her öğesiyle bit düzeyinde birleştirilecek bir öğe türü bit düzeyinde veya belirtilen değerle birleştirilecek olan iki valarışın ikinci değeri.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri `OR` *sol* ve *sağ* bit düzeyinde işlemin öğe temelinde birleşimi olan bir valarray.

### <a name="remarks"></a>Açıklamalar

Bit düzeyinde bir işlem yalnızca,, **`char`** **`int`** **`float`** **`double`** **longdouble**, **`void`** , **`bool`** veya diğer daha karmaşık veri türlerinde değil, BITS içindeki ve veri türlerindeki ve varyantları işlemek için kullanılabilir.

Bit düzeyinde veya mantıksal olarak aynı Truth tablosuna sahiptir `OR` , ancak tek tek bitlerin düzeyindeki veri türü için geçerli olur. Bit *b* 1 ve *b* 2, *b* 1 `OR` *b* 2, **`true`** bitlerin en az biri doğru veya **`false`** her iki bit de yanlış olduğunda. Mantıksal `OR` [işleç&#124;&#124;](../standard-library/valarray-operators.md#op_lor) , bir öğe düzeyinde uygulanır, sıfır olmayan değerlerin tümü olarak sayılıyor **`true`** ve sonuç Boolean değerlerinin bir valarray. Bit düzeyinde OR veya `operator|` aksine, bit düzeyinde işlemin sonucuna bağlı olarak 0 veya 1 ' den farklı değerler valarray olabilir.

### <a name="example"></a>Örnek

```cpp
// valarray_op_bitor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<int> vaLAA ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  1;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  i-1;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  i-1;

   cout << "The initial Left valarray is:  ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaLAA = ( vaL | vaR );
   cout << "The element-by-element result of "
        << "the bitwise OR operator| is the\n"
        << "valarray: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaLAA [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is:  ( 1 0 1 0 1 0 1 0 1 0 ).
The initial Right valarray is: ( 0 0 1 3 3 4 6 6 7 9 ).
The element-by-element result of the bitwise OR operator| is the
valarray: ( 1 0 1 3 3 4 7 6 7 9 ).
```

## <a name="operator124124"></a><a name="op_lor"></a> işleç&#124;&#124;

`OR`İki eşit ölçekli valarışın karşılık gelen öğeleri veya bir valarray ile valarray öğesi türünün belirtilen değeri arasında mantıksal değer edinir.

```cpp
template <class Type>
valarray<bool>
operator||(
    const valarray<Type>& left,
    const valarray<Type>& right);

template <class Type>
valarray<bool>
operator||(
    const valarray<Type>& left,
    const Type& right);

template <class Type>
valarray<bool>
operator||(
    const Type& left,
    const valarray<Type>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
İlgili öğeleri, `OR` bir valarray öğesinin her öğesiyle birleştirilecek olan öğe türünün mantıksal veya belirtilen değeri ile birleştirilecek olan iki valarışın ilki.

*Right*\
İlgili öğeleri `OR` bir valarray öğesinin her öğesiyle birleştirilecek olan öğe türünün mantıksal veya belirtilen değeriyle birleştirilecek olan iki valarışın ikinci değeri.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri tür olan **`bool`** ve *sol* ve *sağ* mantıksal veya işlemin öğe temelinde birleşimi olan bir valarray.

### <a name="remarks"></a>Açıklamalar

Mantıksal `OR` `operator||` bir öğe düzeyinde uygulanır, sıfır olmayan tüm değerleri olarak sayarak **`true`** Sonuç olarak Boolean değerlerinin bir valarray. &#124;bit düzeyinde işlem, bit düzeyinde `OR` işlemin sonucuna bağlı olarak 0 veya 1 ' den farklı değerler valarray ile sonuçlanabilir. [](../standard-library/valarray-operators.md#op_or)

### <a name="example"></a>Örnek

```cpp
// valarray_op_logor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   valarray<bool> vaLOR ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  0;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  0;

   cout << "The initial Left valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaLOR = ( vaL || vaR );
   cout << "The element-by-element result of "
        << "the logical OR operator|| is the\n"
        << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaLOR [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial Left valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).
The initial Right valarray is: ( 0 0 0 3 0 0 6 0 0 9 ).
The element-by-element result of the logical OR operator|| is the
valarray: ( 0 0 0 1 0 1 1 1 0 1 ).
```
