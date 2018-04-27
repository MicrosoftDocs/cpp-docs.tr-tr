---
title: '&lt;valarray&gt; işleçleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: 8a53562c-90ab-4eb3-85d3-ada5259d90b0
caps.latest.revision: 8
manager: ghogen
helpviewer_keywords:
- std::operator!= (valarray), std::operator&amp; (valarray)
- std::operator&amp;&amp; (valarray)
- std::operator&gt; (valarray)
- std::operator&gt;&gt; (valarray)
- std::operator&gt;= (valarray)
- std::operator&lt; (valarray)
- std::operator&lt;&lt; (valarray)
- std::operator&lt;= (valarray), std::operator== (valarray)
ms.openlocfilehash: b22e60aa2794c98c298648fa5906004ec18f259a
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ltvalarraygt-operators"></a>&lt;valarray&gt; işleçleri

||||
|-|-|-|
|[operator!=](#op_neq)|[operator%](#op_mod)|[işleci&amp;](#op_amp)|
|[işleci&amp;&amp;](#op_amp_amp)|[işleci&gt;](#op_gt)|[işleci&gt;&gt;](#op_gt_gt)|
|[işleci&gt;=](#op_gt_eq)|[işleci&lt;](#op_lt)|[işleci&lt;&lt;](#op_lt_lt)|
|[işleci&lt;=](#op_lt_eq)|[işleç *](#op_star)|[operator +](#op_add)|
|[operator-](#operator-)|[operator /](#op_div)|[operator==](#op_eq_eq)|
|[operator ^](#op_xor)|[işleci|](#op_or)|[işleci||](#op_lor)|

## <a name="op_neq"></a>  operator! =

İki eşit boyutta valarrays karşılık gelen öğelerini eşit olmayan veya olup olmadığını bir valarray tüm öğeleri eşit olup olmadığını sınar belirtilen bir değeri.

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

`left` Eşitsizlik için sınanacak öğeleri olan iki valarrays ilk.

`right` Eşitsizlik için sınanacak öğeleri olan iki valarrays saniye.

### <a name="return-value"></a>Dönüş Değeri

Her biri bir valarray Boole değerleri:

- **doğru** karşılık gelen öğeleri eşit ise.

- **yanlış** karşılık gelen öğeleri eşit değilse.

### <a name="remarks"></a>Açıklamalar

İlk şablon işleci sınıfın bir nesnesi döndürür [valarray\<bool >](../standard-library/valarray-bool-class.md), her öğeleri `I` olan `left[I] != right[I]`.

İkinci şablon işleci öğesinde depolar `I` `left[I] != right`.

Üçüncü şablon işleci öğesinde depolar `I` `left != right[I]`.

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
        << "the not equal comparison test is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the not equal comparison test is the
 valarray: ( 0 0 1 0 1 0 1 0 1 0 ).
*\
```

## <a name="op_mod"></a>  operator %

İki eşit boyutta valarrays veya bir valarray bir belirtilen değere bölünmesinden veya valarray tarafından belirtilen değere bölerek öğelere karşılık gelir ayırma kalan alır.

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

`left` Bir değer veya hangi başka bir değer bölünen hizmet valarray veya valarray bölünür yüklemektir.

`right` Bir değer veya, bölen olarak hizmet verir ve başka bir değerle böler valarray veya valarray.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri olan element-wise kalanları valarray, `left` bölü `right`.

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
        << "division is the\n valarray: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaREM [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 53 -67 53 -67 53 -67 ).
The initial Right valarray is: ( 1 4 7 10 13 16 ).
The remainders from the element-by-element division is the
 valarray: ( 0 -3 4 -7 1 -3 ).
*\
```

## <a name="op_amp"></a>  işleci&amp;

Bit düzeyinde edinir **ve** veya bir valarray ile öğe türü belirtilen değeri arasında iki eşit boyutta valarrays öğelere karşılık gelir.

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

`left` İlgili öğeleri olan Bitsel ile birleştirilecek iki valarrays ilk **ve** veya belirtilen değer Bitsel bir valarray her öğenin birleştirilecek öğe türü.

`right` İlgili öğeleri olan Bitsel ile birleştirilecek iki valarrays ikinci **ve** veya belirtilen değer Bitsel bir valarray her öğenin birleştirilecek öğe türü.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri bit tabanlı AND işlemi element-wise birleşimi olan bir valarray, `left` ve `right`.

### <a name="remarks"></a>Açıklamalar

Bit tabanlı işlemi yalnızca bit cinsinden işlemek için kullanılabilir `char` ve `int` veri türleri ve çeşitleri değil **float**, **çift**, **longdouble**, `void`, `bool` veya diğer, daha karmaşık veri türleri.

Bit düzeyinde **ve** mantıksal aynı gerçekte tabloda sahip **ve** ancak tek tek bit düzeyinde veri türü için geçerlidir. [İşleci & &](../standard-library/valarray-operators.md#amp) geçerli bir öğe düzeyi, tüm sıfır olmayan değerler true ve sonuç sayım valarray Boolean değeri değil. Bit düzeyinde **ANDoperator &**, bunun aksine, değer 0 veya 1, bit düzeyinde işleminin sonucunu bağlı olarak başka bir valarray neden olabilir.

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
        << "the bitwise operator & is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaBWA [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is:  ( 0 2 0 4 0 6 0 8 0 10 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the bitwise operator & is the
 valarray: ( 0 0 0 0 0 4 0 0 0 8 ).
*\
```

## <a name="op_amp_amp"></a>  işleci&amp;&amp;

Mantıksal edinir **ve** bir valarray ve valarray's öğe türü belirtilen değeri veya iki eşit boyutta valarrays karşılık gelen öğeleri arasında.

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

`left` İlgili öğeleri olan mantıksal ile birleştirilecek iki valarrays ilk **ve** veya belirtilen değer bir valarray her öğenin birleştirilecek öğe türü.

`right` İlgili öğeleri olan mantıksal ile birleştirilecek iki valarrays ikinci **ve** veya belirtilen değer bir valarray her öğenin birleştirilecek öğe türü.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri türü bool ve mantıksal element-wise birleşimi valarray **ve** işlemi `left` ve `right`.

### <a name="remarks"></a>Açıklamalar

Mantıksal **ANDoperator & &** geçerli bir öğe düzeyi, tüm sıfır olmayan değerler true ve sonuç sayım valarray Boolean değeri değil. Bit düzeyinde sürümü **ve**, [işleci &,](../standard-library/valarray-operators.md#op_amp), bunun aksine, değer 0 veya 1, bit düzeyinde işleminin sonucunu bağlı olarak başka bir valarray neden olabilir.

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
        << "the logical AND operator&& is the\n valarray: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaLAA [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the logical AND operator&& is the
 valarray: ( 0 0 0 1 0 1 0 1 0 1 ).
*\
```

## <a name="op_gt"></a>  işleci&gt;

Bir valarray öğelerini daha büyük bir eşit boyutta valarray öğelerini veya bir valarray tüm öğeleri büyük ya da belirtilen değerden daha az olup olmadığını test eder.

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

`left` Her bir valarray öğesi ile Karşılaştırılacak ilk Karşılaştırılacak öğeleri olan iki valarrays veya belirtilen bir değeri.

`right` Karşılaştırılacak öğeleri olan iki valarrays ikinci veya belirtilen bir değeri her bir valarray öğesi ile Karşılaştırılacak.

### <a name="return-value"></a>Dönüş Değeri

Her biri bir valarray Boole değerleri:

- **doğru** varsa `left` öğesi veya değeri karşılık gelen daha büyük `right` öğesi veya değer.

- **yanlış** varsa `left` öğesi veya değeri karşılık gelen daha büyük değil `right` öğesi veya değer.

### <a name="remarks"></a>Açıklamalar

İki valarrays öğe sayısı eşit değilse, tanımlanmamış bir sonucudur.

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
        << "the greater than comparison test is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( -1 0 1 2 3 4 5 6 7 8 ).
The element-by-element result of the greater than comparison test is the
 valarray: ( 1 1 0 1 0 1 0 1 0 1 ).
*\
```

## <a name="op_gt_eq"></a>  işleci&gt;=

Bir valarray öğelerini değerinden büyük veya eşit boyutta bir valarray veya olup bir valarray tüm öğeleri daha büyük veya eşit veya daha az veya belirtilen değere eşit öğelerini eşit olup olmadığını sınar.

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

`left` Her bir valarray öğesi ile Karşılaştırılacak ilk Karşılaştırılacak öğeleri olan iki valarrays veya belirtilen bir değeri.

`right` Karşılaştırılacak öğeleri olan iki valarrays ikinci veya belirtilen bir değeri her bir valarray öğesi ile Karşılaştırılacak.

### <a name="return-value"></a>Dönüş Değeri

Her biri bir valarray Boole değerleri:

- **doğru** varsa `left` öğesi veya değeri sıfırdan büyük veya buna karşılık gelen eşit `right` öğesi veya değer.

- **yanlış** varsa `left` öğesi veya değer, ilgili değerinden `right` öğesi veya değer.

### <a name="remarks"></a>Açıklamalar

İki valarrays öğe sayısı eşit değilse, tanımlanmamış bir sonucudur.

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
        << "the greater than or equal test is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( -1 0 1 2 3 4 5 6 7 8 ).
The element-by-element result of the greater than or equal test is the
 valarray: ( 1 1 0 1 0 1 0 1 0 1 ).
*\
```

## <a name="op_gt_gt"></a>  işleci&gt;&gt;

Valarray belirtilen sayıda konumlar veya ikinci valarray tarafından belirtilen bir element-wise miktar, her bir öğe için BITS sağa kaydırır.

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

`left` Değerin gölgeye veya değişebilir öğeleri olan valarray.

`right` Sağa kaydırma veya valarray miktarını gösteren değer öğeleri sağa kaydırma element-wise miktarını belirtin.

### <a name="return-value"></a>Dönüş Değeri

Belirli bir miktarda öğeleri sağ gölgeye valarray.

### <a name="remarks"></a>Açıklamalar

İşaretli sayılara korunur kendi işaretlere sahip.

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
        << "the right shift is the\n valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 64 -64 64 -64 64 -64 64 -64 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the right shift is the
 valarray: ( 64 -32 16 -8 4 -2 1 -1 ).
*\
```

## <a name="op_lt"></a>  işleci&lt;

Bir valarray öğelerini eşit boyutta bir valarray veya bir valarray tüm öğeleri büyük ya da belirtilen değerden daha az olup öğelerini değerinden olup olmadığını sınar.

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

`left` Her bir valarray öğesi ile Karşılaştırılacak ilk Karşılaştırılacak öğeleri olan iki valarrays veya belirtilen bir değeri.

`right` Karşılaştırılacak öğeleri olan iki valarrays ikinci veya belirtilen bir değeri her bir valarray öğesi ile Karşılaştırılacak.

### <a name="return-value"></a>Dönüş Değeri

Her biri bir valarray Boole değerleri:

- **doğru** varsa `left` öğesi veya değer, ilgili değerinden `right` öğesi veya değer.

- **yanlış** varsa `left` öğesi veya değeri değil karşılık gelen daha küçük `right` öğesi veya değer.

### <a name="remarks"></a>Açıklamalar

Öğeleri iki valarrays sayısı eşit değilse, tanımlanmamış bir sonucudur.

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
        << "the less-than comparson test is the\n valarray: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the less-than comparson test is the
 valarray: ( 0 0 1 0 1 0 1 0 1 0 ).
*\
```

## <a name="op_lt_eq"></a>  işleci&lt;=

Bir valarray öğelerini küçük veya buna eşit boyutta bir valarray öğelerini eşit olup olmadığına veya bir valarray tüm öğeleri daha büyük veya eşit veya daha az veya belirtilen değere eşit olup olmadığını sınar.

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

`left` Her bir valarray öğesi ile Karşılaştırılacak ilk Karşılaştırılacak öğeleri olan iki valarrays veya belirtilen bir değeri.

`right` Karşılaştırılacak öğeleri olan iki valarrays ikinci veya belirtilen bir değeri her bir valarray öğesi ile Karşılaştırılacak.

### <a name="return-value"></a>Dönüş Değeri

Her biri bir valarray Boole değerleri:

- **doğru** varsa `left` öğesi değeri mi değerinden küçük veya eşit karşılık gelen `right` öğesi veya değer.

- **yanlış** varsa `left` öğesi veya değeri karşılık gelen daha büyük `right` öğesi veya değer.

### <a name="remarks"></a>Açıklamalar

Öğeleri iki valarrays sayısı eşit değilse, tanımlanmamış bir sonucudur.

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
        << "the less than or equal test is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( -1 0 1 2 3 4 5 6 7 8 ).
The element-by-element result of the less than or equal test is the
 valarray: ( 0 0 1 0 1 0 1 0 1 0 ).
*\
```

## <a name="op_lt_lt"></a>  işleci&lt;&lt;

Valarray belirtilen sayıda konumlar veya ikinci valarray tarafından belirtilen bir element-wise miktar, her bir öğe için BITS Sola kaydırır.

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

`left` Değerin gölgeye veya değişebilir öğeleri olan valarray.

`right` Sola kaydırma veya valarray miktarını gösteren değer öğeleri sola kaydırma element-wise miktarını belirtin.

### <a name="return-value"></a>Dönüş Değeri

Belirli bir miktarda sol öğeleri gölgeye bir valarray.

### <a name="remarks"></a>Açıklamalar

İşaretli sayılara korunur kendi işaretlere sahip.

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
        << "the left shift is the\n valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 1 -1 1 -1 1 -1 1 -1 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the left shift is the
 valarray: ( 1 -2 4 -8 16 -32 64 -128 ).
*\
```

## <a name="op_star"></a>  işleç *

İki eşit boyutta valarrays ya da, ilgili öğeler arasında element-wise ürün edinir valarray belirtilen değer arasında.

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

`left` Her bir valarray öğesi ile çarpılacağı ilk çarpılacağı öğeleri olan iki valarrays ya da belirtilen bir değeri.

`right` Öğeleri çarpılacağı olan iki valarrays ikinci veya belirtilen değer bir valarray her öğenin çarpılacağı.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri olan element-wise ürün valarray, `left` ve `right`.

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
        << "the multiplication is the\n valarray: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the multiplication is the
 valarray: ( 0 -1 4 -3 8 -5 12 -7 ).
*\
```

## <a name="op_add"></a>  operator +

İki eşit boyutta valarrays ya da, ilgili öğeler arasında element-wise toplam alacağı valarray belirtilen değer arasında.

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

`left` Her bir valarray öğesi ile eklenecek ilk eklenecek öğeleri olan iki valarrays veya belirtilen bir değeri.

`right` Eklenecek öğeleri olan iki valarrays ikinci veya belirtilen değer bir valarray her öğenin eklenecek.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri element-wise toplamı olan valarray, `left` ve `right`.

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
        << "the sum is the\n valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the sum is the
 valarray: ( 2 0 4 2 6 4 8 6 ).
*\
```

## <a name="operator-"></a>  operator-

Karşılık gelen öğeleri iki eşit boyutta valarrays veya, element-wise birbirinden edinir valarray belirtilen değer arasında.

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

`left` Bir değer veya içerdiği diğer değerleri veya valarrays fark oluşturan çıkarılır için olan minuend görevi gören valarray.

`right` Bir değer veya diğer değerleri veya fark oluşturan içinde valarrays çıkartma yapılacak için subtrahend görevi gören valarray.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri element-wise farkı olan bir valarray, `left` ve `right`.

### <a name="remarks"></a>Açıklamalar

Çıkarma tanımlamak için kullanılan aritmetik terminolojisi:

fark minuend - = subtrahend

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
        << "the difference is the\n valarray: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 10 0 10 0 10 0 10 0 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the difference is the
 valarray: ( 10 -1 8 -3 6 -5 4 -7 ).
*\
```

## <a name="op_div"></a>  operator /

İki eşit boyutta valarrays ya da, ilgili öğeler arasında element-wise sayının edinir valarray belirtilen değer arasında.

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

`left` Bir değer veya hangi başka bir değer bölünen hizmet valarray veya valarray sayının oluşturan bölünür yüklemektir.

`right` Bir değer veya valarray, bölen olarak hizmet verir ve başka bir değer veya sayının oluşturan içinde valarray böler.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri olan element-wise sayının valarray, `left` bölü `right`.

### <a name="remarks"></a>Açıklamalar

Bölme tanımlamak için kullanılan aritmetik terminolojisi:

sayının bölünen = / bölen

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
        << "the quotient is the\n valarray: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 100 -100 100 -100 100 -100 ).
The initial Right valarray is: ( 0 2 4 6 8 10 ).
The element-by-element result of the quotient is the
 valarray: ( inf -50 25 -16.6667 12.5 -10 ).
*\
```

## <a name="op_eq_eq"></a>  operator ==

İki eşit boyutta valarrays karşılık gelen öğelerini eşittir veya bir valarray tüm öğeleri olup olup testleri belirtilen değere eşit.

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

`left` Eşitlik için test edilecek öğeleri olan iki valarrays ilk.

`right` Eşitlik için test edilecek öğeleri olan iki valarrays saniye.

### <a name="return-value"></a>Dönüş Değeri

Her biri bir valarray Boole değerleri:

- **doğru** karşılık gelen öğeleri eşit olması durumunda.

- **yanlış** karşılık gelen öğeleri eşit değilse.

### <a name="remarks"></a>Açıklamalar

İlk şablon işleci sınıfın bir nesnesi döndürür [valarray\<bool >](../standard-library/valarray-bool-class.md), her öğeleri `I` olan `left[I] == right[I]`. İkinci şablon işleci öğesinde depolar `I` `left[I] == right`. Üçüncü şablon işleci öğesinde depolar `I` `left == right[I]`.

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
        << "the equality comparison test is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNE [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is: ( 0 1 -2 3 -4 5 -6 7 -8 9 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the equality comparison test is the
 valarray: ( 1 1 0 1 0 1 0 1 0 1 ).
*\
```

## <a name="op_xor"></a>  operator ^

Bit düzeyinde özel edinir `OR` ( **XOR**) veya bir valarray ile öğe türü belirtilen değeri arasında iki eşit boyutta valarrays öğelere karşılık gelir.

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

`left` İlgili öğeleri olan Bitsel ile birleştirilecek iki valarrays ilk **XOR** veya belirtilen değer Bitsel bir valarray her öğenin birleştirilecek öğe türü.

`right` İlgili öğeleri olan Bitsel ile birleştirilecek iki valarrays ikinci **XOR** veya belirtilen değer Bitsel bir valarray her öğenin birleştirilecek öğe türü.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri bitwise element-wise birleşimi olan bir valarray **XOR** işlemi `left` ve `right`.

### <a name="remarks"></a>Açıklamalar

Bit tabanlı işlemi yalnızca bit cinsinden işlemek için kullanılabilir `char` ve `int` veri türleri ve çeşitleri değil **float**, **çift**, `long double`, `void`, `bool` veya diğer, daha karmaşık veri türleri.

Bit düzeyinde özel `OR` ( **XOR**) aşağıdaki semantiğini vardır: BITS verilen *b*1 ve *b*2, *b*1  **XOR** *b*2 **true** BITS tam olarak birine true; ise **false** bitlerin her ikisi de false olduğunda veya bitlerin her ikisi de doğruysa.

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
        << "the bitwise XOR operator^ is the\n valarray: ( ";
           for ( i = 0 ; i < 10 ; i++ )
         cout << vaLAA [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is:  ( 1 0 1 0 1 0 1 0 1 0 ).
The initial Right valarray is: ( 0 0 1 3 3 4 6 6 7 9 ).
The element-by-element result of the bitwise XOR operator^ is the
 valarray: ( 1 0 0 3 2 4 7 6 6 9 ).
*\
```

## <a name="op_or"></a>  işleci&#124;

Bit düzeyinde edinir `OR` veya bir valarray ile öğe türü belirtilen değeri arasında iki eşit boyutta valarrays öğelere karşılık gelir.

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

`left` İlgili öğeleri olan Bitsel ile birleştirilecek iki valarrays ilk `OR` veya belirtilen değer Bitsel bir valarray her öğenin birleştirilecek öğe türü.

`right` İlgili öğeleri olan Bitsel ile birleştirilecek iki valarrays ikinci `OR` veya belirtilen değer Bitsel bir valarray her öğenin birleştirilecek öğe türü.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri bitwise element-wise birleşimi olan bir valarray `OR` işlemi `left` ve `right`.

### <a name="remarks"></a>Açıklamalar

Bit tabanlı işlemi yalnızca bit cinsinden işlemek için kullanılabilir `char` ve `int` veri türleri ve çeşitleri değil **float**, **çift**, **longdouble**, `void`, `bool` veya diğer, daha karmaşık veri türleri.

Bit düzeyinde OR mantıksal aynı gerçekte tabloda sahip `OR`, ancak tek tek bit düzeyinde veri türü için geçerlidir. BITS verilen *b*1 ve *b*2, *b*1 `OR` *b*2 **true** BITS en az biri olduğunda TRUE veya **false** bitlerin her ikisi de yanlışsa. Mantıksal `OR` [işleci&#124; &#124; ](../standard-library/valarray-operators.md#op_lor) olarak sıfır dışındaki tüm değerleri sayım bir öğe düzeyi geçerli **true**, ve sonucu bir valarray Boolean değeri. Bit düzeyinde OR `operator|`, bunun aksine, değer 0 veya 1, bit düzeyinde işleminin sonucunu bağlı olarak başka bir valarray neden olabilir.

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
        << "the bitwise OR operator| is the\n valarray: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaLAA [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is:  ( 1 0 1 0 1 0 1 0 1 0 ).
The initial Right valarray is: ( 0 0 1 3 3 4 6 6 7 9 ).
The element-by-element result of the bitwise OR operator| is the
 valarray: ( 1 0 1 3 3 4 7 6 7 9 ).
*\
```

## <a name="op_lor"></a>  işleci&#124;&#124;

Mantıksal edinir `OR` veya bir valarray ile valarray öğesi türünde belirtilen değer arasında iki eşit boyutta valarrays öğelere karşılık gelir.

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

`left` İlgili öğeleri olan mantıksal ile birleştirilecek iki valarrays ilk `OR` veya belirtilen değer bir valarray her öğenin birleştirilecek öğe türü.

`right` İlgili öğeleri olan mantıksal ile birleştirilecek iki valarrays ikinci `OR` veya belirtilen değer bir valarray her öğenin birleştirilecek öğe türü.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri türü olan bir valarray `bool` ve mantıksal OR çalışmasını element-wise birleşimi `left` ve `right`.

### <a name="remarks"></a>Açıklamalar

Mantıksal `OR` `operator||` olarak sıfır dışındaki tüm değerleri sayım bir öğe düzeyi geçerli **doğru**, ve sonucu bir valarray Boolean değeri. Bit düzeyinde sürümü `OR`, [işleci&#124; ](../standard-library/valarray-operators.md#op_or) aksine, değer 0 veya 1, bit düzeyinde işleminin sonucunu bağlı olarak başka bir valarray neden olabilir.

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
        << "the logical OR operator|| is the\n valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaLOR [ i ] << " ";
   cout << ")." << endl;
}
\* Output:
The initial Left valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).
The initial Right valarray is: ( 0 0 0 3 0 0 6 0 0 9 ).
The element-by-element result of the logical OR operator|| is the
 valarray: ( 0 0 0 1 0 1 1 1 0 1 ).
*\
```

## <a name="see-also"></a>Ayrıca bkz.

[\<valarray >](../standard-library/valarray.md)<br/>
