---
title: '&lt;valarray&gt; işleçleri'
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
ms.openlocfilehash: 231bad65e2af1ee2ab800890c83cc50e584a8c6a
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246104"
---
# <a name="ltvalarraygt-operators"></a>&lt;valarray&gt; işleçleri

## <a name="op_neq"></a> işleç! =

Eşit değil veya bir valarray tüm öğelerini eşit olup iki eşit boyutlu valarrays karşılık gelen öğeleri olup olmadığını test belirtilen bir değer.

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

*Sol*\
Eşitsizlik için test edilecek öğeleri olan iki valarrays ilk.

*sağ*\
Eşitsizlik için test edilecek öğeleri olan iki valarrays saniye.

### <a name="return-value"></a>Dönüş Değeri

Her biri bir valarray Boole değerleri:

- **doğru** karşılık gelen öğelerle eşit olduğunda.

- **false** karşılık gelen öğelerle eşit değilse.

### <a name="remarks"></a>Açıklamalar

Sınıfın bir nesnesi ilk şablon işlecini verir [valarray\<bool >](../standard-library/valarray-bool-class.md), her biri öğeleri `I` olduğu `left[I] != right[I]`.

İkinci şablon işlecini öğesinde depolar `I` `left[I] != right`.

Üçüncü şablon işlecini öğesinde depolar `I` `left != right[I]`.

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

## <a name="op_mod"></a> operator %

Karşılık gelen öğelerle iki eşit boyutlu valarrays veya bir valarray bir belirtilen değere bölünmesinden veya bir valarray tarafından belirtilen değere bölerek bölme kalanı alır.

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

*Sol*\
Bir değer veya hangi başka bir değer ile bölünen hizmet veren valarray ya da valarray bölünür sağlamaktır.

*sağ*\
Bir değer veya bölen olarak hizmet veren ve, başka bir değerle böler valarray veya valarray.

### <a name="return-value"></a>Dönüş Değeri

Aralığın öğe düzeyinde çarpımının kalanları öğeleri olan bir valarray, *sol* bölü *doğru*.

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

## <a name="op_amp"></a> İşleci&amp;

Bit düzeyinde alır **ve** bir valarray ve öğe türü belirtilen değeri veya iki eşit boyutlu valarrays karşılık gelen öğeleri arasında.

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

*Sol*\
İlgili öğeleri olan bit ile birleştirilecek iki valarrays ilk `AND` veya bir valarray her öğesinin bit düzeyinde birleştirilecek öğe türü belirtilen değeri.

*sağ*\
İki valarrays ilgili öğeleri olan bit ile birleştirilecek ikinci `AND` veya bir valarray her öğesinin bit düzeyinde birleştirilecek öğe türü belirtilen değeri.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri, bit düzeyinde AND işlemi aralığın öğe düzeyinde çarpımının birleşimi olan bir valarray, *sol* ve *doğru*.

### <a name="remarks"></a>Açıklamalar

Bit düzeyinde işlem yalnızca bit işlemek için kullanılabilir **char** ve **int** veri türleri ve çeşitleri değil **float**, **çift**, **longdouble**, **void**, **bool** veya diğer, daha karmaşık veri türleri.

Bit düzeyinde `AND` mantıksal olarak aynı gerçekte tablo `AND` ancak tek bit düzeyinde veri türü için geçerlidir. [İşleci & &](#op_amp_amp) geçerli bir öğe düzeyi, tüm sıfır olmayan değerler true ve sonuç sayım olduğu bir valarray Boolean değeri. Bit düzeyinde `AND` [işleci &](#op_amp), aksine, değerleri 0 veya 1, bit düzeyinde işlemin sonucunu bağlı olarak başka bir valarray neden olabilir.

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

## <a name="op_amp_amp"></a> İşleci&amp;&amp;

Mantıksal alır **ve** bir valarray ve valarray'nın öğe türünün belirtilen bir değeri veya iki eşit boyutlu valarrays karşılık gelen öğeleri arasında.

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

*Sol*\
İlgili öğeleri olan mantıksal ile birleştirilecek iki valarrays ilk `AND` veya bir valarray her bir öğe ile birleştirilecek öğe türü belirtilen değeri.

*sağ*\
İki valarrays ilgili öğeleri olan mantıksal ile birleştirilecek ikinci `AND` veya bir valarray her bir öğe ile birleştirilecek öğe türü belirtilen değeri.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri türü bool ve mantıksal aralığın öğe düzeyinde çarpımının birleşimi bir valarray `AND` işleyişini *sol* ve *doğru*.

### <a name="remarks"></a>Açıklamalar

Mantıksal `ANDoperator&&` geçerli bir öğe düzeyi, tüm sıfır olmayan değerler true ve sonuç sayım olduğu bir valarray Boolean değeri. Bit düzeyinde sürümünü `AND`, [işleci &,](#op_amp), aksine, değerleri 0 veya 1, bit düzeyinde işlemin sonucunu bağlı olarak başka bir valarray neden olabilir.

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

## <a name="op_gt"></a> İşleci&gt;

Bir valarray öğelerden daha büyük bir eşit boyutlu valarray öğelerini veya bir valarray tüm öğelerini büyük ya da belirtilen değerden daha az olup olmadığını sınar.

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

*Sol*\
Her bir valarray öğe ile Karşılaştırılacak ilk Karşılaştırılacak öğeleri olan iki valarrays ya da belirtilen bir değer.

*sağ*\
Karşılaştırılacak öğeleri olan iki valarrays ikinci veya belirtilen değer bir valarray her bir öğe ile Karşılaştırılacak.

### <a name="return-value"></a>Dönüş Değeri

Her biri bir valarray Boole değerleri:

- **doğru** varsa *sol* öğe veya değer ilgili daha fazla *doğru* öğe veya değer.

- **false** varsa *sol* öğe veya değer karşılık gelen değerinden büyük değil *doğru* öğe veya değer.

### <a name="remarks"></a>Açıklamalar

İki valarrays içindeki öğelerin sayısını eşit değilse sonuç tanımsızdır.

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

## <a name="op_gt_eq"></a> İşleci&gt;=

Bir valarray öğelerini değerinden büyük veya eşit boyutlu bir valarray veya bir valarray tüm öğelerini büyük veya eşit veya daha az olup belirtilen bir değere eşit öğelerinin eşit olup olmadığını test eder.

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

*Sol*\
Her bir valarray öğe ile Karşılaştırılacak ilk Karşılaştırılacak öğeleri olan iki valarrays ya da belirtilen bir değer.

*sağ*\
Karşılaştırılacak öğeleri olan iki valarrays ikinci veya belirtilen değer bir valarray her bir öğe ile Karşılaştırılacak.

### <a name="return-value"></a>Dönüş Değeri

Her biri bir valarray Boole değerleri:

- **doğru** varsa *sol* büyüktür veya eşittir karşılık gelen öğe veya değer *doğru* öğe veya değer.

- **false** varsa *sol* öğe veya değer azdır karşılık gelen *doğru* öğe veya değer.

### <a name="remarks"></a>Açıklamalar

İki valarrays içindeki öğelerin sayısını eşit değilse sonuç tanımsızdır.

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

## <a name="op_gt_gt"></a> İşleci&gt;&gt;

Sağa kaydırmalar her öğeyi belirtilen sayıda konumları veya ikinci bir valarray tarafından belirtilen aralığın öğe düzeyinde çarpımının bir miktara göre bir valarray parçaları.

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

*Sol*\
Kaydırılmasına değer veya kaydırılmasına öğeleri olan valarray.

*sağ*\
Sağa kaydırma veya valarray belirten değeri öğeleri sağa kaydırma aralığın öğe düzeyinde çarpımının miktarını belirtin.

### <a name="return-value"></a>Dönüş Değeri

Belirli bir miktarda öğeleri sağa kaydırılacak bir valarray.

### <a name="remarks"></a>Açıklamalar

İşaretli sayılara korunur, imzalar vardır.

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

## <a name="op_lt"></a> İşleci&lt;

Bir valarray öğelerinin eşit boyutlu bir valarray veya bir valarray tüm öğelerini büyük ya da belirtilen değerden daha az olup öğelerini küçük olup olmadığını test eder.

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

*Sol*\
Her bir valarray öğe ile Karşılaştırılacak ilk Karşılaştırılacak öğeleri olan iki valarrays ya da belirtilen bir değer.

*sağ*\
Karşılaştırılacak öğeleri olan iki valarrays ikinci veya belirtilen değer bir valarray her bir öğe ile Karşılaştırılacak.

### <a name="return-value"></a>Dönüş Değeri

Her biri bir valarray Boole değerleri:

- **doğru** varsa *sol* öğe veya değer azdır karşılık gelen *doğru* öğe veya değer.

- **false** varsa *sol* öğesi veya değeri değil ilgili daha az *doğru* öğe veya değer.

### <a name="remarks"></a>Açıklamalar

Öğeleri iki valarrays sayısına eşit değil ise sonuç tanımsızdır.

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

## <a name="op_lt_eq"></a> İşleci&lt;=

Bir valarray öğelerini ya da eşit boyutlu bir valarray öğelerinin eşit olup olmadığını veya bir valarray tüm öğelerini büyük veya eşit veya daha az veya belirtilen değere eşit olup olmadığını test eder.

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

*Sol*\
Her bir valarray öğe ile Karşılaştırılacak ilk Karşılaştırılacak öğeleri olan iki valarrays ya da belirtilen bir değer.

*sağ*\
Karşılaştırılacak öğeleri olan iki valarrays ikinci veya belirtilen değer bir valarray her bir öğe ile Karşılaştırılacak.

### <a name="return-value"></a>Dönüş Değeri

Her biri bir valarray Boole değerleri:

- **doğru** varsa *sol* öğe veya değer olan küçük veya eşit karşılık gelen *doğru* öğe veya değer.

- **false** varsa *sol* öğe veya değer ilgili daha fazla *doğru* öğe veya değer.

### <a name="remarks"></a>Açıklamalar

Öğeleri iki valarrays sayısına eşit değil ise sonuç tanımsızdır.

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

## <a name="op_lt_lt"></a> İşleci&lt;&lt;

Sola bir valarray belirtilen sayıda konumları veya ikinci bir valarray tarafından belirtilen aralığın öğe düzeyinde çarpımının bir miktar, her öğe için bit kaydırır.

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

*Sol*\
Kaydırılmasına değer veya kaydırılmasına öğeleri olan valarray.

*sağ*\
Sola kaydırma veya valarray belirten bir değeri, öğeleri sola kaydırma aralığın öğe düzeyinde çarpımının miktarını belirtin.

### <a name="return-value"></a>Dönüş Değeri

Belirli bir miktarda sola kaydırılacak öğeleri bir valarray.

### <a name="remarks"></a>Açıklamalar

İşaretli sayılara korunur, imzalar vardır.

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

## <a name="op_star"></a> operator *

Aralığın öğe düzeyinde çarpımının ürün arasındaki, iki eşit boyutlu valarrays ve karşılık gelen öğeleri alır bir valarray belirtilen değer arasında.

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

*Sol*\
Her bir valarray öğe ile çarpılmasına ilk çarpılmasına öğeleri olan iki valarrays ya da belirtilen bir değer.

*sağ*\
Öğeleri çarpılmasına olan iki valarrays ikinci veya belirtilen değer bir valarray her bir öğe ile çarpılmasına.

### <a name="return-value"></a>Dönüş Değeri

Aralığın öğe düzeyinde çarpımının ürün öğeleri olan bir valarray, *sol* ve *doğru*.

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

## <a name="op_add"></a> operator +

İki eşit boyutlu valarrays veya, ilgili öğeler arasındaki aralığın öğe düzeyinde çarpımının toplamını alır bir valarray belirtilen değer arasında.

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

*Sol*\
Bir valarray her öğesinin eklenmesi ilk eklenecek öğeleri olan iki valarrays ya da belirtilen bir değer.

*sağ*\
Eklenecek öğeleri olan iki valarrays ikinci veya belirtilen değer bir valarray her öğeyle eklenecek.

### <a name="return-value"></a>Dönüş Değeri

Aralığın öğe düzeyinde çarpımının toplamını öğeleri olan bir valarray, *sol* ve *doğru*.

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

## <a name="operator-"></a> operator-

İki eşit boyutlu valarrays veya, karşılık gelen öğeleri arasındaki aralığın öğe düzeyinde çarpımının fark alır bir valarray belirtilen değer arasında.

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

*Sol*\
Bir değer veya içerdiği diğer değerleri veya valarrays fark oluşturan içinde çıkarılan için olan Eksilen görevi gören valarray.

*sağ*\
Bir değer veya diğer değerleri veya fark oluşturan içinde valarrays çıkarmanın yapılacağı olan çıkarılan görevi gören valarray.

### <a name="return-value"></a>Dönüş Değeri

Aralığın öğe düzeyinde çarpımının fark öğeleri olan bir valarray, *sol* ve *doğru*.

### <a name="remarks"></a>Açıklamalar

Çıkarma tanımlamak için kullanılan aritmetik terimler:

fark - Eksilen = çıkarılan

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

## <a name="op_div"></a> operator /

Aralığın öğe düzeyinde çarpımının bölümü arasındaki, iki eşit boyutlu valarrays ve karşılık gelen öğeleri alır bir valarray belirtilen değer arasında.

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

*Sol*\
Bir değer veya hangi başka bir değer ile bölünen hizmet veren valarray ya da valarray sayının oluşturan içinde bölünür sağlamaktır.

*sağ*\
Bir değer veya valarray bölen olarak hizmet veren ve başka bir değer veya bölümü oluşturan içinde valarray böler.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri aralığın öğe düzeyinde çarpımının bölümü olan bir valarray, *sol* bölü *doğru*.

### <a name="remarks"></a>Açıklamalar

Bir bölme tanımlamak için kullanılan aritmetik terimler:

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

## <a name="op_eq_eq"></a> işleç ==

İki eşit boyutlu valarrays karşılık gelen öğeleri eşit veya bir valarray tüm öğelerini olup olup olmadığını test belirtilen değere eşit.

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

*Sol*\
Eşitlik için test edilecek öğeleri olan iki valarrays ilk.

*sağ*\
Eşitlik için test edilecek öğeleri olan iki valarrays saniye.

### <a name="return-value"></a>Dönüş Değeri

Her biri bir valarray Boole değerleri:

- **doğru** karşılık gelen öğe eşitse.

- **false** karşılık gelen öğelerle eşit değilse.

### <a name="remarks"></a>Açıklamalar

Sınıfın bir nesnesi ilk şablon işlecini verir [valarray\<bool >](../standard-library/valarray-bool-class.md), her biri öğeleri `I` olduğu `left[I] == right[I]`. İkinci şablon işlecini öğesinde depolar `I` `left[I] == right`. Üçüncü şablon işlecini öğesinde depolar `I` `left == right[I]`.

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

## <a name="op_xor"></a> operator ^

Bit düzeyinde özel alır `OR` ( **XOR**) veya bir valarray ve öğe türü belirtilen değeri karşılık gelen iki eşit boyutlu valarrays öğelerin arasında.

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

*Sol*\
İlgili öğeleri olan bit ile birleştirilecek iki valarrays ilk **XOR** veya bir valarray her öğesinin bit düzeyinde birleştirilecek öğe türü belirtilen değeri.

*sağ*\
İki valarrays ilgili öğeleri olan bit ile birleştirilecek ikinci **XOR** veya bir valarray her öğesinin bit düzeyinde birleştirilecek öğe türü belirtilen değeri.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri bit aralığın öğe düzeyinde çarpımının birleşimi olan bir valarray **XOR** işleyişini *sol* ve *doğru*.

### <a name="remarks"></a>Açıklamalar

Bit düzeyinde işlem yalnızca bit işlemek için kullanılabilir **char** ve **int** veri türleri ve çeşitleri değil **float**, **çift**, **uzun çift**, **void**, **bool** veya diğer, daha karmaşık veri türleri.

Bit düzeyinde özel `OR` ( **XOR**) aşağıdaki semantiği vardır: BITS verilen *b*1 ve *b*2 *b*1 **XOR** *b*2 **true** varsa BITS tam olarak biri doğruysa; **false** bitlerin her ikisi de false olduğunda veya bitlerin her ikisi de doğruysa.

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

## <a name="op_or"></a> işleci&#124;

Bit düzeyinde alır `OR` bir valarray ve öğe türü belirtilen değeri veya iki eşit boyutlu valarrays karşılık gelen öğeleri arasında.

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

*Sol*\
İlgili öğeleri olan bit ile birleştirilecek iki valarrays ilk `OR` veya bir valarray her öğesinin bit düzeyinde birleştirilecek öğe türü belirtilen değeri.

*sağ*\
İki valarrays ilgili öğeleri olan bit ile birleştirilecek ikinci `OR` veya bir valarray her öğesinin bit düzeyinde birleştirilecek öğe türü belirtilen değeri.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri bit aralığın öğe düzeyinde çarpımının birleşimi olan bir valarray `OR` işleyişini *sol* ve *doğru*.

### <a name="remarks"></a>Açıklamalar

Bit düzeyinde işlem yalnızca bit işlemek için kullanılabilir **char** ve **int** veri türleri ve çeşitleri değil **float**, **çift**, **longdouble**, **void**, **bool** veya diğer, daha karmaşık veri türleri.

Bit düzeyinde OR mantıksal olarak aynı doğru tablosu sahip `OR`, ancak tek bit düzeyinde veri türü için geçerlidir. BITS verilen *b*1 ve *b*2 *b*1 `OR` *b*2 **true** en az bir bit ise TRUE veya **false** bitlerin her ikisi de false ise. Mantıksal `OR` [işleci&#124; &#124; ](../standard-library/valarray-operators.md#op_lor) olarak sıfır dışındaki tüm değerleri sayma bir öğe düzeyi geçerli **true**, ve sonucu bir valarray Boolean değeri. Bit düzeyinde OR `operator|`, aksine, değerleri 0 veya 1, bit düzeyinde işlemin sonucunu bağlı olarak başka bir valarray neden olabilir.

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

## <a name="op_lor"></a> işleci&#124;&#124;

Mantıksal alır `OR` bir valarray ve valarray öğe türü belirtilen değeri veya iki eşit boyutlu valarrays karşılık gelen öğeleri arasında.

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

*Sol*\
İlgili öğeleri olan mantıksal ile birleştirilecek iki valarrays ilk `OR` veya bir valarray her bir öğe ile birleştirilecek öğe türü belirtilen değeri.

*sağ*\
İki valarrays ilgili öğeleri olan mantıksal ile birleştirilecek ikinci `OR` veya bir valarray her bir öğe ile birleştirilecek öğe türü belirtilen değeri.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri türü olan bir valarray **bool** ve mantıksal OR işleyişini aralığın öğe düzeyinde çarpımının birleşimi *sol* ve *doğru*.

### <a name="remarks"></a>Açıklamalar

Mantıksal `OR` `operator||` olarak sıfır dışındaki tüm değerleri sayma bir öğe düzeyi geçerli **true**, ve sonucu bir valarray Boolean değeri. Bit düzeyinde sürümünü `OR`, [işleci&#124; ](../standard-library/valarray-operators.md#op_or) aksine, değerleri 0 veya 1, bit düzeyinde işlemin sonucunu bağlı olarak başka bir valarray neden olabilir.

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
