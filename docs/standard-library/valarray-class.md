---
title: valarray Sınıfı
ms.date: 03/27/2019
f1_keywords:
- valarray/std::valarray
- valarray/std::valarray::value_type
- valarray/std::valarray::apply
- valarray/std::valarray::cshift
- valarray/std::valarray::free
- valarray/std::valarray::max
- valarray/std::valarray::min
- valarray/std::valarray::resize
- valarray/std::valarray::shift
- valarray/std::valarray::size
- valarray/std::valarray::sum
- valarray/std::valarray::swap
helpviewer_keywords:
- std::valarray [C++]
- std::valarray [C++], value_type
- std::valarray [C++], apply
- std::valarray [C++], cshift
- std::valarray [C++], free
- std::valarray [C++], max
- std::valarray [C++], min
- std::valarray [C++], resize
- std::valarray [C++], shift
- std::valarray [C++], size
- std::valarray [C++], sum
- std::valarray [C++], swap
ms.assetid: 19b862f9-5d09-4003-8844-6ddd02c1a3a7
ms.openlocfilehash: f116758591461614acfa7c171bff2b1675f453e4
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78866264"
---
# <a name="valarray-class"></a>valarray Sınıfı

Sınıf şablonu, dizi olarak depolanan `Type` türünde öğelerin dizisini denetleyen, yüksek hızlı matematik işlemleri gerçekleştirmek için tasarlanan ve hesaplama performansı için iyileştirilmiş bir nesne tanımlar.

## <a name="remarks"></a>Açıklamalar

Sınıfı, sıralı bir değer kümesinin matematik kavramının bir gösterimidir ve öğeler sıfırdan sıralı olarak numaralandırılır. Sınıf, [vektör](../standard-library/vector-class.md), destek gibi birinci sınıf sıra kapsayıcılarının bazı özelliklerini desteklediğinden, yakın bir kapsayıcı olarak açıklanmaktadır. Sınıf şablonu vektöründen iki önemli şekilde farklılık gösterir:

- Bu, *xarr* = cos ( *yarr*) + sin ( *zarr*) gibi aynı türdeki ve uzunluktaki `valarray<Type>` nesnelerinin karşılık gelen öğeleri arasında çok sayıda aritmetik işlem tanımlar.

- Bu, aşırı yükleme [işlecine&#91;](#op_at)göre bir `valarray<Type>` nesnesini altyana eklemek için çeşitli ilginç yollar tanımlar.

`Type`sınıfının bir nesnesi:

- , Geleneksel davranışla ortak bir varsayılan oluşturucuya, yıkıcı, kopya oluşturucusuna ve atama işlecine sahiptir.

- Geleneksel davranışla birlikte kayan nokta türleri için tanımlanan, gerektiğinde aritmetik işleçleri ve matematik işlevlerini tanımlar.

Özellikle, kopyalama oluşturma ve varsayılan oluşturma arasında ve ardından atama ile hiçbir hafif fark olamaz. `Type` sınıfının nesnelerinde hiçbir işlem özel durum oluşturabilir.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[valarray](#valarray)|Belirli bir boyutun veya belirli bir değerin öğeleriyle ya da başka bir `valarray`başka bir `valarray` ya da alt kümesinin bir kopyası olarak `valarray` oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[value_type](#value_type)|`valarray`depolanan öğe türünü temsil eden bir tür.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[uygulayabilirsiniz](#apply)|`valarray`her öğesine belirtilen bir işlevi uygular.|
|[cshift](#cshift)|Periyodik `valarray` tüm öğeleri belirtilen sayıda konum ile kaydırır.|
|[free](#free)|`valarray`tarafından kullanılan belleği serbest bırakır.|
|[Biçimlendir](#max)|`valarray`en büyük öğeyi bulur.|
|[Min](#min)|`valarray`en küçük öğeyi bulur.|
|[yeniden boyutlandırma](#resize)|Bir `valarray` öğe sayısını belirtilen sayı olarak değiştirir, gerekli olarak öğeleri ekler veya kaldırır.|
|[karakter](#shift)|`valarray` tüm öğeleri belirtilen sayıda konum ile kaydırır.|
|[boyutla](#size)|Bir `valarray`öğe sayısını bulur.|
|[toplamlarını](#sum)|Sıfır olmayan uzunluktaki `valarray` tüm öğelerin toplamını belirler.|
|[Kur](#swap)||

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işlecinde!](#op_not)|Bir `valarray`her öğenin mantıksal `NOT` değerlerini elde eden birli işleç.|
|[işleç% =](#op_mod_eq)|Bir dizi öğesinin öğelerinin, belirtilen bir `valarray` veya öğe türünün bir değeri ile bölünmesinin kalan kısmını alır.|
|[işleç & =](#op_and_eq)|Bir dizideki öğelerin bit düzeyinde `AND`, belirtilen bir `valarray` karşılık gelen öğelerle ya da öğe türünün bir değeriyle edinir.|
|[işleç > > =](#op_gt_gt_eq)|`valarray` işleneninin her bir öğesi için bitleri, belirtilen sayıda konum veya ikinci bir `valarray`belirtilen öğe temelinde bir miktar ile sağa kaydırır.|
|[işleç < < =](#op_lt_lt_eq)|Sol-`valarray` işleneninin her bir öğesi için bitleri, belirtilen sayıda konum veya ikinci bir `valarray`belirtilen öğe temelinde bir miktar ile kaydırır.|
|[işleç * =](#op_star_eq)|Belirtilen bir `valarray` öğelerini veya öğe türü, öğe temelinde değerini bir işlenenden çarpar `valarray`.|
|[işleç +](#op_add)|Bir `valarray`içindeki her öğeye Plus uygulayan birli işleç.|
|[işleç + =](#op_add_eq)|Belirtilen bir `valarray` öğelerini veya öğe türü, öğe temelinde bir değeri bir işlenenin `valarray`ekler.|
|[işlecinde](#operator-)|Bir `valarray`içindeki her öğeye eksi işareti uygulayan birli işleç.|
|[işleç-=](#operator-_eq)|Belirtilen bir `valarray` öğelerini veya öğe türü, öğe temelinde bir değeri bir işlenenden çıkartır `valarray`.|
|[işleç/=](#op_div_eq)|Bir işleneni, belirtilen bir `valarray` öğeleri veya öğe türü için öğe temelinde `valarray` böler.|
|[işleç =](#op_eq)|Değerleri doğrudan veya diğer bir `valarray` parçası olarak ya da bir `slice_array`, `gslice_array`, `mask_array`veya `indirect_array`olarak belirtilen bir `valarray` öğeleri atar.|
|[işlecinde&#91;&#93;](#op_at)|Belirtilen dizindeki veya belirtilen bir alt kümedeki bir öğeye veya değerine bir başvuru döndürür.|
|[işleç ^ =](#op_xor_eq)|Belirtilen bir valarray veya öğe türünde bir değere sahip bir dizinin öğe temelinde özel mantıksal veya işlecini (`XOR`) alır.|
|[işleç&#124;=](#op_or_eq)|Bir dizideki öğelerin bit düzeyinde `OR`, belirtilen bir `valarray` karşılık gelen öğelerle ya da öğe türünün bir değeriyle edinir.|
|[işleç ~](#op_dtor)|Bir `valarray`her öğenin bit düzeyinde `NOT` değerlerini elde eden birli işleç.|

## <a name="apply"></a>uygulayabilirsiniz

Bir valarray öğesinin her öğesine belirtilen bir işlev uygular.

```cpp
valarray<Type> apply(Type _Func(Type)) const;

valarray<Type> apply(Type _Func(constType&)) const;
```

### <a name="parameters"></a>Parametreler

*_Func (tür)* \
Valarray işleneninin her öğesine uygulanacak işlev nesnesi.

*_Func (const Type &)* \
Const için işlev nesnesi, valarray işleneninin her öğesine uygulanır.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri valarray işleneninin öğelerine öğe temelinde uygulanmış olan bir valarray `_Func`.

### <a name="remarks"></a>Açıklamalar

Üye [işlevi,](#size) [valarray](../standard-library/valarray-class.md) **\<türünde >** sınıfının, her biri `_Func((*this)[I])`*olan öğelerinden oluşan* bir nesne döndürür.

### <a name="example"></a>Örnek

```cpp
// valarray_apply.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

using namespace std;

int __cdecl MyApplyFunc( int n )
{
   return n*2;
}

int main( int argc, char* argv[] )
{
   valarray<int> vaR(10), vaApplied(10);
   int i;

   for ( i = 0; i < 10; i += 3 )
      vaR[i] = i;

   for ( i = 1; i < 10; i += 3 )
      vaR[i] = 0;

   for ( i = 2; i < 10; i += 3 )
      vaR[i] = -i;

   cout << "The initial Right valarray is: (";
   for   ( i=0; i < 10; ++i )
      cout << " " << vaR[i];
   cout << " )" << endl;

   vaApplied = vaR.apply( MyApplyFunc );

   cout << "The element-by-element result of "
       << "applying MyApplyFunc to vaR is the\nvalarray: ( ";
   for ( i = 0; i < 10; ++i )
      cout << " " << vaApplied[i];
   cout << " )" << endl;
}
```

```Output
The initial Right valarray is: ( 0 0 -2 3 0 -5 6 0 -8 9 )
The element-by-element result of applying MyApplyFunc to vaR is the
valarray: (  0 0 -4 6 0 -10 12 0 -16 18 )
```

## <a name="cshift"></a>cshift

Periyodik, bir valarray içindeki tüm öğeleri belirtilen sayıda konum ile kaydırır.

```cpp
valarray<Type> cshift(int count) const;
```

### <a name="parameters"></a>Parametreler

*sayı*\
Öğelerin ileri kaydırılacağı konum sayısı.

### <a name="return-value"></a>Dönüş Değeri

Tüm öğelerin, valarray önüne doğru bir şekilde taşındığı, valarray 'in, işlenen valarray içindeki konumlarına göre periyodik *konumlarını taşıyan yeni* bir.

### <a name="remarks"></a>Açıklamalar

*Count* pozitif değeri öğeleri periyodik Left *Count* konumlarına geçirir.

*Count* değerinin negatif bir değeri, öğeleri periyodik doğru *sayı* konumlarına geçirir.

### <a name="example"></a>Örnek

```cpp
// valarray_cshift.cpp
// compile with: /EHsc

#include <valarray>
#include <iostream>

int main()
{
    using namespace std;
    int i;

    valarray<int> va1(10), va2(10);
    for (i = 0; i < 10; i+=1)
        va1[i] = i;
    for (i = 0; i < 10; i+=1)
        va2[i] = 10 - i;

    cout << "The operand valarray va1 is: (";
    for (i = 0; i < 10; i++)
        cout << " " << va1[i];
    cout << ")" << endl;

    // A positive parameter shifts elements right
    va1 = va1.cshift(4);
    cout << "The cyclically shifted valarray va1 is:\nva1.cshift (4) = (";
    for (i = 0; i < 10; i++)
        cout << " " << va1[i];
    cout << ")" << endl;

    cout << "The operand valarray va2 is: (";
    for (i = 0; i < 10; i++)
        cout << " " << va2[i];
    cout << ")" << endl;

    // A negative parameter shifts elements left
    va2 = va2.cshift(-4);
    cout << "The cyclically shifted valarray va2 is:\nva2.shift (-4) = (";
    for (i = 0; i < 10; i++)
        cout << " " << va2[i];
    cout << ")" << endl;
}
```

```Output
The operand valarray va1 is: ( 0 1 2 3 4 5 6 7 8 9)
The cyclically shifted valarray va1 is:
va1.cshift (4) = ( 4 5 6 7 8 9 0 1 2 3)
The operand valarray va2 is: ( 10 9 8 7 6 5 4 3 2 1)
The cyclically shifted valarray va2 is:
va2.shift (-4) = ( 4 3 2 1 10 9 8 7 6 5)
```

## <a name="free"></a>Süz

Valarray tarafından kullanılan belleği serbest bırakır.

```cpp
void free();
```

### <a name="remarks"></a>Açıklamalar

Bu standart olmayan işlev boş bir valarray atama ile eşdeğerdir. Örnek:

```cpp
valarray<T> v;
v = valarray<T>();

// equivalent to v.free()
```

## <a name="max"></a>Biçimlendir

Bir valarray içinde en büyük öğeyi bulur.

```cpp
Type max() const;
```

### <a name="return-value"></a>Dönüş Değeri

Valarray işleneninde öğelerin en büyük değeri.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, sınıf `Type`öğe çiftleri arasında **işleç\<** veya **işleç >** uygulayarak, öğe `Type`için hangi işleçlerin sağlanması gerektiğini, değerleri karşılaştırır.

### <a name="example"></a>Örnek

```cpp
// valarray_max.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i, MaxValue;

   valarray<int> vaR ( 10 );
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  2*i - 1;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  10 - i;

   cout << "The operand valarray is: ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   MaxValue = vaR.max (  );
   cout << "The largest element in the valarray is: "
        << MaxValue  << "." << endl;
}
```

```Output
The operand valarray is: ( 0 1 8 3 7 5 6 13 2 9 ).
The largest element in the valarray is: 13.
```

## <a name="min"></a>Min

Bir valarray içindeki en küçük öğeyi bulur.

```cpp
Type min() const;
```

### <a name="return-value"></a>Dönüş Değeri

Valarray işleneninde öğelerin en küçük değeri.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, sınıf `Type`öğe çiftleri arasında **işleç\<** veya **işleç >** uygulayarak, öğe `Type`için hangi işleçlerin sağlanması gerektiğini, değerleri karşılaştırır.

### <a name="example"></a>Örnek

```cpp
// valarray_min.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i, MinValue;

   valarray<int> vaR ( 10 );
   for ( i = 0 ; i < 10 ; i += 3 )
      vaR [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 3 )
      vaR [ i ] =  2*i;
   for ( i = 2 ; i < 10 ; i += 3 )
      vaR [ i ] =  5 - i;

   cout << "The operand valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   MinValue = vaR.min ( );
   cout << "The smallest element in the valarray is: "
        << MinValue  << "." << endl;
}
/* Output:
The operand valarray is: ( 0 2 3 -3 8 0 -6 14 -3 -9 ).
The smallest element in the valarray is: -9.
*/
```

## <a name="op_not"></a>işlecinde!

Bir valarray içindeki her öğenin mantıksal **Not** değerlerini elde eden birli işleç.

```cpp
valarray<bool> operator!() const;
```

### <a name="return-value"></a>Dönüş Değeri

Valarray işleneninin öğe değerlerini olumsuzlama olan Boolean değerlerinin valarray.

### <a name="remarks"></a>Açıklamalar

Mantıksal işlem, tüm sıfırları bir değere dönüştürdüğünden ve sıfır dışında tüm değerleri sıfır olarak dönüştürerek **öğeleri geçersiz hale** getirir. Boole değerlerinin döndürülen valarray, valarray işleneni ile aynı boyutudır.

Ayrıca, bir valarray 'ın **karakter** ve **tamsayı** öğelerinin ikili gösteriminde tek tek bitlerin düzeyinde geçersiz hale gelen bit düzeyinde **olmayan**[valarray:: operator ~](#op_dtor) .

### <a name="example"></a>Örnek

```cpp
// valarray_op_lognot.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 );
   valarray<bool> vaNOT ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;

   cout << "The initial valarray is:  ( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   vaNOT = !vaL;
   cout << "The element-by-element result of "
        << "the logical NOT operator! is the"
        << endl << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaNOT [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).
The element-by-element result of the logical NOT operator! is the
valarray: ( 1 1 1 0 1 0 1 0 1 0 ).
```

## <a name="op_mod_eq"></a>işleç% =

Bir dizi öğesinin öğelerini belirtilen bir valarray veya öğe türünün bir değeri ile bölmenin geri kalanını edinir.

```cpp
valarray<Type>& operator%=(const valarray<Type>& right);

valarray<Type>& operator%=(const Type& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Bir öğe türünün valarray veya değeri, öğe odaklı, öğe temelinde, valarray işleneni olan valarray ile özdeş.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri, işlenenin öğe temelinde valarray *sağ* tarafında kalan bir valarray

### <a name="example"></a>Örnek

```cpp
// valarray_class_op_rem.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 6 ), vaR ( 6 );
   for ( i = 0 ; i < 6 ; i += 2 )
      vaL [ i ] =  53;
   for ( i = 1 ; i < 6 ; i += 2 )
      vaL [ i ] =  -67;
   for ( i = 0 ; i < 6 ; i++ )
      vaR [ i ] =  3*i+1;

   cout << "The initial valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial  right valarray is: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL %= vaR;
   cout << "The remainders from the element-by-element "
        << "division is the"
        << endl << "valarray: ( ";
      for ( i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial valarray is: ( 53 -67 53 -67 53 -67 ).
The initial  right valarray is: ( 1 4 7 10 13 16 ).
The remainders from the element-by-element division is the
valarray: ( 0 -3 4 -7 1 -3 ).
```

## <a name="op_and_eq"></a>işleç&amp;=

Bir dizideki bit düzeyinde **ve** öğelerin, belirtilen bir valarray karşılık gelen öğelerle ya da öğe türü değeri ile elde ettiği öğeleri alır.

```cpp
valarray<Type>& operator&=(const valarray<Type>& right);

valarray<Type>& operator&=(const Type& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Bir öğe türünün valarray veya değeri, öğe temelinde, valarray işleneni ile mantıksal `AND` birleştirilecek olan işlenenden özdeş.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri, işlenenin öğe temelinde mantıksal `AND` olan bir valarray- *sağ*

### <a name="remarks"></a>Açıklamalar

Bit düzeyinde bir işlem, **float**, **Double**, **longdouble**, **void**, **bool**veya diğer, daha karmaşık veri türlerinde değil yalnızca **char** ve **int** veri türleri ve varyantlarını işlemek için kullanılabilir.

Bit düzeyinde ve mantıksal `AND` aynı Truth tablosuna sahiptir, ancak tek tek bitlerin düzeyindeki veri türü için geçerli olur. Her iki *bit de*doğru olursa, b 1 ve *b*2, *b*1 `AND` *b*2 değeri de **geçerlidir** ; en az bir false olduğunda **false** .

### <a name="example"></a>Örnek

```cpp
// valarray_class_op_bitand.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;
   for ( i = 0 ; i < 10 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL &= vaR;
   cout << "The element-by-element result of "
        << "the logical AND operator&= is the"
        << endl << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the logical AND operator&= is the
valarray: ( 0 0 0 2 0 4 0 6 0 8 ).
```

## <a name="op_gt_gt_eq"></a>işleç&gt;&gt;=

Bir valarray işleneninin her öğesi için bitleri, belirtilen sayıda konum veya bir ikinci valarray tarafından belirtilen öğe temelinde bir miktar ile sağa kaydırır.

```cpp
valarray<Type>& operator>>=(const valarray<Type>& right);

valarray<Type>& operator>>=(const Type& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Öğesi, sağ SHIFT veya valarray öğelerinin öğe temelinde sağ SHIFT miktarını belirten değer.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri sağ tarafta belirtilen miktarı sağa kaydırılan bir *valarray.*

### <a name="remarks"></a>Açıklamalar

İmzalı sayıların işaretleri korunur.

### <a name="example"></a>Örnek

```cpp
// valarray_class_op_rs.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  64;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -64;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial operand valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The  right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL >>= vaR;
   cout << "The element-by-element result of "
        << "the right shift is the"
        << endl << "valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial operand valarray is: ( 64 -64 64 -64 64 -64 64 -64 ).
The  right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the right shift is the
valarray: ( 64 -32 16 -8 4 -2 1 -1 ).
```

## <a name="op_lt_lt_eq"></a>işleç&lt;&lt;=

Sol-bir valarray işleneninin her öğesi için bitleri, belirtilen sayıda konum veya bir ikinci valarray tarafından belirtilen öğe temelinde bir miktar ile kaydırır.

```cpp
valarray<Type>& operator<<=(const valarray<Type>& right);

valarray<Type>& operator<<=(const Type& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Öğeleri, sol SHIFT veya valarray öğelerinin öğe temelinde sol SHIFT miktarını belirten değer.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri *sağ tarafta*belirtilen miktarı sola kaydırılan bir valarray.

### <a name="remarks"></a>Açıklamalar

İmzalı sayıların işaretleri korunur.

### <a name="example"></a>Örnek

```cpp
// valarray_class_op_ls.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  1;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial operand valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The  right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL <<= vaR;
   cout << "The element-by-element result of "
        << "the left shift"
        << endl << "on the operand array is the valarray:"
        << endl << "( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial operand valarray is: ( 1 -1 1 -1 1 -1 1 -1 ).
The  right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the left shift
on the operand array is the valarray:
( 1 -2 4 -8 16 -32 64 -128 ).
```

## <a name="op_star_eq"></a>işleç * =

Belirtilen bir valarray öğelerini veya öğe türü bir değeri olan öğe türünü bir işlenen valarray ile çarpar.

```cpp
valarray<Type>& operator*=(const valarray<Type>& right);

valarray<Type>& operator*=(const Type& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Öğe türünün valarray veya değeri, öğe temelinde, öğe odaklı, valarray işleneni olan valarray ile özdeş.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri valarray ve *Right*işleneninin öğe odaklı ürünü olan bir valarray.

### <a name="example"></a>Örnek

```cpp
// valarray_op_emult.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  2;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL *= vaR;
   cout << "The element-by-element result of "
        << "the multiplication is the"
        << endl << "valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
/* Output:
The initial valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the multiplication is the
valarray: ( 0 -1 4 -3 8 -5 12 -7 ).
*/
```

## <a name="op_add"></a>işleç +

Bir valarray içindeki her öğeye Plus uygulayan birli işleç.

```cpp
valarray<Type> operator+() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğeleri ve işlenen dizisi olan bir valarray.

### <a name="example"></a>Örnek

```cpp
// valarray_op_eplus.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 );
   valarray<int> vaPLUS ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;

   cout << "The initial valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   vaPLUS = +vaL;
   cout << "The element-by-element result of "
        << "the operator+ is the"
        << endl << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaPLUS [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial valarray is:  ( 0 0 -2 2 -4 4 -6 6 -8 8 ).
The element-by-element result of the operator+ is the
valarray: ( 0 0 -2 2 -4 4 -6 6 -8 8 ).
```

## <a name="op_add_eq"></a>işleç + =

Belirtilen bir valarray öğelerini ya da öğe türü, öğe temelinde bir değeri valarray bir işlenene ekler.

```cpp
valarray<Type>& operator+=(const valarray<Type>& right);

valarray<Type>& operator+=(const Type& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Öğe türünün valarray veya değeri, öğe temelinde, öğe odaklı valarray işlenenden özdeş olan valarray.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri valarray ve *Right*işleneninin öğe temelinde toplamı olan bir valarray.

### <a name="example"></a>Örnek

```cpp
// valarray_op_eadd.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  2;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  -1;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial valarray is: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial  right valarray is: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL += vaR;
   cout << "The element-by-element result of "
        << "the sum is the"
        << endl << "valarray: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).
The initial  right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the sum is the
valarray: ( 2 0 4 2 6 4 8 6 ).
```

## <a name="operator-"></a>işlecinde

Bir valarray içindeki her öğeye eksi işareti uygulayan birli işleç.

```cpp
valarray<Type> operator-() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğeleri işlenen dizisinin dışında olan bir valarray.

### <a name="example"></a>Örnek

```cpp
// valarray_op_eminus.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 );
   valarray<int> vaMINUS ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      vaL [ i ] =  -i;
   for ( i = 1 ; i < 10 ; i += 2 )
      vaL [ i ] =  i-1;

   cout << "The initial valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   vaMINUS = -vaL;
   cout << "The element-by-element result of "
        << "the operator+ is the"
        << endl << "valarray: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaMINUS [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial valarray is:  ( 0 0 -2 2 -4 4 -6 6 -8 8 ).
The element-by-element result of the operator+ is the
valarray: ( 0 0 2 -2 4 -4 6 -6 8 -8 ).
```

## <a name="operator-_eq"></a>işleç-=

Belirtilen bir valarray öğelerini ya da öğe türü bir değeri olan öğe türünü bir işlenenden çıkartır valarray.

```cpp
valarray<Type>& operator-=(const valarray<Type>& right);

valarray<Type>& operator-=(const Type& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Bir öğe türünün valarray veya değeri, öğe temelinde çıkarılacak valarray işleneniyle aynı bir öğe türü için valarray.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri valarray ve *Right*işleneninin öğe temelinde farkı olan bir valarray.

### <a name="example"></a>Örnek

```cpp
// valarray_op_esub.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 8 ), vaR ( 8 );
   for ( i = 0 ; i < 8 ; i += 2 )
      vaL [ i ] =  10;
   for ( i = 1 ; i < 8 ; i += 2 )
      vaL [ i ] =  0;
   for ( i = 0 ; i < 8 ; i++ )
      vaR [ i ] =  i;

   cout << "The initial valarray is: ( ";
      for (i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial  right valarray is: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL -= vaR;
   cout << "The element-by-element result of "
        << "the difference is the"
        << endl << "valarray: ( ";
      for ( i = 0 ; i < 8 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial valarray is: ( 10 0 10 0 10 0 10 0 ).
The initial  right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the difference is the
valarray: ( 10 -1 8 -3 6 -5 4 -7 ).
```

## <a name="op_div_eq"></a>işleç/=

Bir işleneni, belirtilen bir valarray öğelerinin veya öğe türünün bir değerinin valarray öğe temelinde böler.

```cpp
valarray<Type>& operator/=(const valarray<Type>& right);

valarray<Type>& operator/=(const Type& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Öğe türünün valarray veya değeri, öğe temelinde, valarray işleneni içine bölünecek şekilde valarray.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri, valarray işlenenin öğe temelinde bölümü olan ve *sağ*tarafından bölünmüş bir.

### <a name="example"></a>Örnek

```cpp
// valarray_op_ediv.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<double> vaL ( 6 ), vaR ( 6 );
   for ( i = 0 ; i < 6 ; i += 2 )
      vaL [ i ] =  100;
   for ( i = 1 ; i < 6 ; i += 2 )
      vaL [ i ] =  -100;
   for ( i = 0 ; i < 6 ; i++ )
      vaR [ i ] =  2*i;

   cout << "The initial valarray is: ( ";
      for (i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The initial Right valarray is: ( ";
      for (i = 0 ; i < 6 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL /= vaR;
   cout << "The element-by-element result of "
        << "the quotient is the"
        << endl << "valarray: ( ";
      for (i = 0 ; i < 6 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial valarray is: ( 100 -100 100 -100 100 -100 ).
The initial Right valarray is: ( 0 2 4 6 8 10 ).
The element-by-element result of the quotient is the
valarray: ( inf -50 25 -16.6667 12.5 -10 ).
```

## <a name="op_eq"></a>işleç =

Değerleri doğrudan veya başka bir valarray parçası olarak ya da bir slice_array, gslice_array, mask_array veya indirect_array tarafından belirtilen bir valarray öğesine atar.

```cpp
valarray<Type>& operator=(const valarray<Type>& right);

valarray<Type>& operator=(valarray<Type>&& right);

valarray<Type>& operator=(const Type& val);

valarray<Type>& operator=(const slice_array<Type>& _Slicearray);

valarray<Type>& operator=(const gslice_array<Type>& _Gslicearray);

valarray<Type>& operator=(const mask_array<Type>& _Maskarray);

valarray<Type>& operator=(const indirect_array<Type>& _Indarray);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Valarray işleneni kopyalamak için valarray.

*val*\
Valarray işleneninin öğelerine atanacak değer.

*_Slicearray*\
Valarray işlenene kopyalanacak slice_array.

*_Gslicearray*\
Valarray işlenene kopyalanacak gslice_array.

*_Maskarray*\
Valarray işlenene kopyalanacak mask_array.

*_Indarray*\
Valarray işlenene kopyalanacak indirect_array.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işleci denetimli diziyi, *sağdan*denetlenen sıranın bir kopyasıyla değiştirir.

İkinci üye işleci ilki ile aynıdır, ancak [rvalue başvuru bildirimci: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

Üçüncü üye işleci, denetlenen sıranın her bir öğesini bir *Val*kopyasıyla değiştirir.

Kalan üye işleçleri, yalnızca [işleci&#91;](#op_at)tarafından oluşturulan, bağımsız değişkenlerine göre seçilen denetimli dizinin bu öğelerinin yerini alır.

Değiştirme denetimli dizideki bir üyenin değeri, ilk denetlenen dizideki bir üyeye bağımlıysa, sonuç tanımsızdır.

### <a name="remarks"></a>Açıklamalar

Denetlenen dizinin uzunluğu değişirse, sonuç genellikle tanımsız olur. Ancak bu uygulamada, efekt yalnızca denetimli dizideki öğelere yönelik işaretçileri veya başvuruları geçersiz kılmak için kullanılır.

### <a name="example"></a>Örnek

```cpp
// valarray_op_assign.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 10 ), vaR ( 10 );
   for ( i = 0 ; i < 10 ; i += 1 )
      va [ i ] = i;
   for ( i = 0 ; i < 10 ; i+=1 )
      vaR [ i ] = 10 -  i;

   cout << "The operand valarray va is:";
   for ( i = 0 ; i < 10 ; i++ )
      cout << " " << va [ i ];
   cout << endl;

   cout << "The operand valarray vaR is:";
      for ( i = 0 ; i < 10 ; i++ )
         cout << " " << vaR [ i ];
   cout << endl;

   // Assigning vaR to va with the first member functon
   va = vaR;
   cout << "The reassigned valarray va is:";
   for ( i = 0 ; i < 10 ; i++ )
      cout << " " << va [ i ];
   cout << endl;

   // Assigning elements of value 10 to va
   // with the second member functon
   va = 10;
   cout << "The reassigned valarray va is:";
      for ( i = 0 ; i < 10 ; i++ )
         cout << " " << va [ i ];
   cout << endl;
}
```

```Output
The operand valarray va is: 0 1 2 3 4 5 6 7 8 9
The operand valarray vaR is: 10 9 8 7 6 5 4 3 2 1
The reassigned valarray va is: 10 9 8 7 6 5 4 3 2 1
The reassigned valarray va is: 10 10 10 10 10 10 10 10 10 10

```

## <a name="op_at"></a>operator []

Belirtilen dizindeki veya belirtilen bir alt kümedeki bir öğeye veya değerine bir başvuru döndürür.

```cpp
Type& operator[](size_t _Off);

slice_array<Type> operator[](slice _Slicearray);

gslice_array<Type> operator[](const gslice& _Gslicearray);

mask_array<Type> operator[](const valarray<bool>& _Boolarray);

indirect_array<Type> operator[](const valarray<size_t>& _Indarray);

Type operator[](size_t _Off) const;

valarray<Type> operator[](slice _Slice) const;

valarray<Type> operator[](const gslice& _Gslicearray) const;

valarray<Type> operator[](const valarray<bool>& _Boolarray) const;

valarray<Type> operator[](const valarray<size_t>& _Indarray) const;
```

### <a name="parameters"></a>Parametreler

*_Off*\
Bir değere atanacak öğenin dizini.

*_Slicearray*\
Seçilecek veya yeni bir valarray döndürülecek bir alt kümeyi belirten bir valarray slice_array.

*_Gslicearray*\
Seçilecek veya yeni bir valarray döndürülecek bir alt kümeyi belirten bir valarray gslice_array.

*_Boolarray*\
Seçilecek veya yeni bir valarray döndürülecek bir alt kümeyi belirten bir valarray bool_array.

*_Indarray*\
Seçilecek veya yeni bir valarray döndürülecek bir alt kümeyi belirten bir valarray indirect_array.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dizinde veya belirtilen bir alt kümede bulunan bir öğeye veya değerine başvuru.

### <a name="remarks"></a>Açıklamalar

Üye işleci, <strong>\*</strong>tarafından denetlenen öğeler arasından öğe dizileri seçmek için çeşitli yollar sağlamak üzere aşırı yüklenmiştir. İlk beş üye işleci grubu, denetlenen sıranın seçmeli değiştirme (dilimleme) için farklı [işleç =](#op_eq) (ve diğer atama işleçleri) ile birlikte çalışır. Seçilen öğeler var olmalıdır.

1 veya 2 olarak tanımlanan [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) kullanılarak derlendiğinde, valarray sınırları dışında bir öğeye erişmeyi denerseniz bir çalışma zamanı hatası oluşur.  Daha fazla bilgi için bkz. [Checked Iterators](../standard-library/checked-iterators.md) .

### <a name="example"></a>Örnek

İşlecinin nasıl bildirileledilinin ve kullanılacağı bir örnek için [Slice:: Slice](../standard-library/slice-class.md#slice) ve [gslice:: gslice](../standard-library/gslice-class.md#gslice) örneklerine bakın.

## <a name="op_xor_eq"></a>işleç ^ =

Belirtilen bir valarray veya öğe türünde bir değere sahip olan bir dizinin öğe temelinde özel mantıksal veya işlecini ( **Xor**) alır.

```cpp
valarray<Type>& operator|=(const valarray<Type>& right);

valarray<Type>& operator|=(const Type& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Öğe türünün valarray veya değeri, öğe temelinde, valarray işleneni ile dışlamalı mantıksal **Xor** tarafından birleştirilecek olan valarray.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri, öğe odaklı, valarray ve *Right*işleneninin dışlamalı mantıksal **Xor** olan bir valarray.

### <a name="remarks"></a>Açıklamalar

Tek başına mantıksal or, **Xor**olarak adlandırılır, aşağıdaki anlamlara sahiptir *: 1 ve*2. öğeler verildiğinde, *e*1 **Xor** *e* *2,* tam olarak bir öğe doğru ise **doğrudur** ; Her iki öğe de yanlışsa veya her iki öğe de doğruysa **false** .

### <a name="example"></a>Örnek

```cpp
// valarray_op_exor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
    using namespace std;
    int i;

    valarray<int> vaL ( 10 ), vaR ( 10 );
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

    cout << "The initial operand valarray is:  ( ";
        for (i = 0 ; i < 10 ; i++ )
            cout << vaL [ i ] << " ";
    cout << ")." << endl;

    cout << "The  right valarray is: ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << vaR [ i ] << " ";
    cout << ")." << endl;

    vaL ^= vaR;
    cout << "The element-by-element result of "
        << "the bitwise XOR operator^= is the"
        << endl << "valarray: ( ";
        for (i = 0 ; i < 10 ; i++ )
            cout << vaL [ i ] << " ";
    cout << ")." << endl;
}
```

```Output
The initial operand valarray is:  ( 1 0 1 0 1 0 1 0 1 0 ).
The  right valarray is: ( 0 0 1 3 3 4 6 6 7 9 ).
The element-by-element result of the bitwise XOR operator^= is the
valarray: ( 1 0 0 3 2 4 7 6 6 9 ).
```

## <a name="op_or_eq"></a>işleç&#124;=

Bir dizideki öğelerin bit düzeyinde `OR`, belirtilen valarray karşılık gelen öğelerle veya öğe türü değeri ile edinir.

```cpp
valarray<Type>& operator|=(const valarray<Type>& right);

valarray<Type>& operator|=(const Type& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Bir öğe türünün valarray veya değeri, öğe temelinde, valarray işleneni ile bit düzeyinde `OR` olarak birleştirilmek için kullanılan işlenenden özdeş.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri, valarray işlenenin öğe temelinde bit düzeyinde *`OR`.*

### <a name="remarks"></a>Açıklamalar

Bit düzeyinde bir işlem, **float**, **Double**, **longdouble**, **void**, **bool**veya diğer, daha karmaşık veri türlerinde değil yalnızca **char** ve **int** veri türleri ve varyantlarını işlemek için kullanılabilir.

Bit düzeyinde `OR`, mantıksal `OR` aynı Truth tablosuna sahiptir ancak tek tek bitlerin düzeyindeki veri türü için geçerli olur. Bitlerin en az biri doğru ise *b 1 ve* *b*2, *b*1 `OR` *b*2, **doğru** olur; Her iki bit de false olduğunda **false** .

### <a name="example"></a>Örnek

```cpp
// valarray_class_op_bitor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> vaL ( 10 ), vaR ( 10 );
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

   cout << "The initial operand valarray is:"
        << endl << "( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;

   cout << "The  right valarray is:"
        << endl << "( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << vaR [ i ] << " ";
   cout << ")." << endl;

   vaL |= vaR;
   cout << "The element-by-element result of "
        << "the logical OR"
        << endl << "operator|= is the valarray:"
        << endl << "( ";
      for (i = 0 ; i < 10 ; i++ )
         cout << vaL [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The initial operand valarray is:
( 1 0 1 0 1 0 1 0 1 0 ).
The  right valarray is:
( 0 0 1 3 3 4 6 6 7 9 ).
The element-by-element result of the logical OR
operator|= is the valarray:
( 1 0 1 3 3 4 7 6 7 9 ).
```

## <a name="op_dtor"></a>işleç ~

Bir valarray içindeki her öğenin bit düzeyinde `NOT` değerlerini elde eden birli işleç.

```cpp
valarray<Type> operator~() const;
```

### <a name="return-value"></a>Dönüş Değeri

Valarray işlenenin öğe değerlerinin bit düzeyinde `NOT` olan Boolean değerlerinin valarray.

### <a name="remarks"></a>Açıklamalar

Bit düzeyinde bir işlem, **float**, **Double**, **longdouble**, **void**, **bool** veya diğer, daha karmaşık veri türlerinde değil yalnızca **char** ve **int** veri türleri ve varyantlarını işlemek için kullanılabilir.

Bit düzeyinde `NOT`, mantıksal `NOT` aynı Truth tablosuna sahiptir ancak tek tek bitlerin düzeyindeki veri türü için geçerli olur. Verilen bit *b*, ~ *b* , *b* yanlış ise true, *b* ise false şeklindedir. Mantıksal **Not**[işleci!](#op_not) öğe düzeyinde uygulanır, sıfır olmayan tüm değerler **doğru**olarak belirlenir ve sonuç Boolean değerlerinin bir valarray. Bit düzeyinde `NOToperator~`, buna karşılık olarak, bit düzeyinde işlemin sonucuna bağlı olarak 0 veya 1 ' den farklı değerlerin valarray oluşmasına neden olabilir.

### <a name="example"></a>Örnek

```cpp
// valarray_op_bitnot.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
    using namespace std;
    int i;

    valarray<unsigned short int> vaL1 ( 10 );
    valarray<unsigned short int> vaNOT1 ( 10 );
    for ( i = 0 ; i < 10 ; i += 2 )
        vaL1 [ i ] =  i;
    for ( i = 1 ; i < 10 ; i += 2 )
        vaL1 [ i ] =  5*i;

    cout << "The initial valarray <unsigned short int> is:  ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << vaL1 [ i ] << " ";
    cout << ")." << endl;

    vaNOT1 = ~vaL1;
    cout << "The element-by-element result of "
        << "the bitwise NOT operator~ is the"
        << endl << "valarray: ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << vaNOT1 [ i ] << " ";
    cout << ")." << endl << endl;

    valarray<int> vaL2 ( 10 );
    valarray<int> vaNOT2 ( 10 );
    for ( i = 0 ; i < 10 ; i += 2 )
        vaL2 [ i ] =  i;
    for ( i = 1 ; i < 10 ; i += 2 )
        vaL2 [ i ] =  -2 * i;

    cout << "The initial valarray <int> is:  ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << vaL2 [ i ] << " ";
    cout << ")." << endl;

    vaNOT2 = ~vaL2;
    cout << "The element-by-element result of "
        << "the bitwise NOT operator~ is the"
        << endl << "valarray: ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << vaNOT2 [ i ] << " ";
    cout << ")." << endl;

    // The negative numbers are represented using
    // the two's complement approach, so adding one
    // to the flipped bits returns the negative elements
    vaNOT2 = vaNOT2 + 1;
    cout << "The element-by-element result of "
        << "adding one"
        << endl << "is the negative of the "
        << "original elements the"
        << endl << "valarray: ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << vaNOT2 [ i ] << " ";
    cout << ")." << endl;
}
```

```Output
The initial valarray <unsigned short int> is:  ( 0 5 2 15 4 25 6 35 8 45 ).
The element-by-element result of the bitwise NOT operator~ is the
valarray: ( 65535 65530 65533 65520 65531 65510 65529 65500 65527 65490 ).

The initial valarray <int> is:  ( 0 -2 2 -6 4 -10 6 -14 8 -18 ).
The element-by-element result of the bitwise NOT operator~ is the
valarray: ( -1 1 -3 5 -5 9 -7 13 -9 17 ).
The element-by-element result of adding one
is the negative of the original elements the
valarray: ( 0 2 -2 6 -4 10 -6 14 -8 18 ).
```

## <a name="resize"></a>yeniden boyutlandırma

Bir valarray içindeki öğe sayısını belirtilen sayı olarak değiştirir.

```cpp
void resize(
    size_t _Newsize);

void resize(
    size_t _Newsize,
    const Type val);
```

### <a name="parameters"></a>Parametreler

*_Newsize*\
Yeniden boyutlandırılmış valarray öğe sayısı.

*val*\
Yeniden boyutlandırılmış valarray öğelerine verilecek değer.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi öğeleri varsayılan oluşturucularıyla başlatır.

Denetlenen dizideki öğelere yönelik işaretçiler veya başvurular geçersiz kılınır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, valarray:: Resize üye işlevinin kullanımını gösterir.

```cpp
// valarray_resize.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main()
{
    using namespace std;
    int i;
    size_t size1, sizeNew;

    valarray<int> va1(10);
    for (i = 0; i < 10; i+=1)
        va1[i] = i;

    cout << "The valarray contains ( ";
        for (i = 0; i < 10; i++)
            cout << va1[i] << " ";
    cout << ")." << endl;

    size1 = va1.size();
    cout << "The number of elements in the valarray is: "
         << size1  << "." <<endl << endl;

    va1.resize(15, 10);

    cout << "The valarray contains ( ";
        for (i = 0; i < 15; i++)
            cout << va1[i] << " ";
    cout << ")." << endl;
    sizeNew = va1.size();
    cout << "The number of elements in the resized valarray is: "
         << sizeNew  << "." <<endl << endl;
}
```

```Output
The valarray contains ( 0 1 2 3 4 5 6 7 8 9 ).
The number of elements in the valarray is: 10.

The valarray contains ( 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 ).
The number of elements in the resized valarray is: 15.
```

## <a name="shift"></a>karakter

Bir valarray içindeki tüm öğeleri belirtilen sayıda yere kaydırır.

```cpp
valarray<Type> shift(int count) const;
```

### <a name="parameters"></a>Parametreler

*sayı*\
Öğelerin ileri kaydırılacağı konum sayısı.

### <a name="return-value"></a>Dönüş Değeri

Tüm öğelerin taşınmış olduğu yeni bir valarray, valarray işleneninde yer *aldığı konumlarda olduğu* gibi, valarray önüne doğru.

### <a name="remarks"></a>Açıklamalar

*Count* pozitif değeri öğeleri sol *sayısı* , sıfır dolgulu olarak kaydırır.

Negatif *sayı* değeri öğeleri doğru *sayı* konumlarına, sıfır dolgulu bir şekilde kaydırır.

### <a name="example"></a>Örnek

```cpp
// valarray_shift.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va1 ( 10 ), va2 ( 10 );
   for ( i = 0 ; i < 10 ; i += 1 )
      va1 [ i ] =  i;
   for ( i = 0 ; i < 10 ; i += 1 )
      va2 [ i ] = 10 -  i;

   cout << "The operand valarray va1(10) is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va1 [ i ] << " ";
   cout << ")." << endl;

   // A positive parameter shifts elements left
   va1 = va1.shift ( 4 );
   cout << "The shifted valarray va1 is: va1.shift (4) = ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va1 [ i ] << " ";
   cout << ")." << endl;

   cout << "The operand valarray va2(10) is: ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va2 [ i ] << " ";
   cout << ")." << endl;

   // A negative parameter shifts elements right
   va2 = va2.shift ( - 4 );
   cout << "The shifted valarray va2 is: va2.shift (-4) = ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va2 [ i ] << " ";
   cout << ")." << endl;
}
```

```Output
The operand valarray va1(10) is: ( 0 1 2 3 4 5 6 7 8 9 ).
The shifted valarray va1 is: va1.shift (4) = ( 4 5 6 7 8 9 0 0 0 0 ).
The operand valarray va2(10) is: ( 10 9 8 7 6 5 4 3 2 1 ).
The shifted valarray va2 is: va2.shift (-4) = ( 0 0 0 0 10 9 8 7 6 5 ).
```

## <a name="size"></a>boyutla

Bir valarray içindeki öğe sayısını bulur.

```cpp
size_t size() const;
```

### <a name="return-value"></a>Dönüş Değeri

Valarray işleneninde öğe sayısı.

### <a name="example"></a>Örnek

Aşağıdaki örnek, valarray:: size üye işlevinin kullanımını gösterir.

```cpp
// valarray_size.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main()
{
    using namespace std;
    int i;
    size_t size1, size2;

    valarray<int> va1(10), va2(12);
    for (i = 0; i < 10; i += 1)
        va1[i] =  i;
    for (i = 0; i < 10; i += 1)
        va2[i] =  i;

    cout << "The operand valarray va1(10) is: ( ";
        for (i = 0; i < 10; i++)
            cout << va1[i] << " ";
    cout << ")." << endl;

    size1 = va1.size();
    cout << "The number of elements in the valarray va1 is: va1.size = "
         << size1  << "." <<endl << endl;

    cout << "The operand valarray va2(12) is: ( ";
        for (i = 0; i < 10; i++)
            cout << va2[i] << " ";
    cout << ")." << endl;

    size2 = va2.size();
    cout << "The number of elements in the valarray va2 is: va2.size = "
         << size2  << "." << endl << endl;

    // Initializing two more elements to va2
    va2[10] = 10;
    va2[11] = 11;
    cout << "After initializing two more elements,\n"
         << "the operand valarray va2(12) is now: ( ";
        for (i = 0; i < 12; i++)
            cout << va2[i] << " ";
    cout << ")." << endl;
    cout << "The number of elements in the valarray va2 is still: "
         << size2  << "." << endl;
}
```

```Output
The operand valarray va1(10) is: ( 0 1 2 3 4 5 6 7 8 9 ).
The number of elements in the valarray va1 is: va1.size = 10.

The operand valarray va2(12) is: ( 0 1 2 3 4 5 6 7 8 9 ).
The number of elements in the valarray va2 is: va2.size = 12.

After initializing two more elements,
the operand valarray va2(12) is now: ( 0 1 2 3 4 5 6 7 8 9 10 11 ).
The number of elements in the valarray va2 is still: 12.
```

## <a name="sum"></a>toplamlarını

Valarray sıfır olmayan uzunlukta tüm öğelerin toplamını belirler.

```cpp
Type sum() const;
```

### <a name="return-value"></a>Dönüş Değeri

Valarray işleneni öğelerinin toplamı.

### <a name="remarks"></a>Açıklamalar

Uzunluk birden büyükse, üye işlevi, sınıf `Type`öğe çiftleri arasında `operator+=`, bu nedenle `Type`türü öğeler için sağlanması gereken bir işleç) uygulayarak değerleri toplamına ekler.

### <a name="example"></a>Örnek

```cpp
// valarray_sum.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
    using namespace std;
    int i;
    int sumva = 0;

    valarray<int> va ( 10 );
    for ( i = 0 ; i < 10 ; i+=1 )
        va [ i ] =  i;

    cout << "The operand valarray va (10) is: ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << va [ i ] << " ";
    cout << ")." << endl;

    sumva = va.sum ( );
    cout << "The sum of elements in the valarray is: "
        << sumva  << "." <<endl;
}
```

```Output
The operand valarray va (10) is: ( 0 1 2 3 4 5 6 7 8 9 ).
The sum of elements in the valarray is: 45.
```

## <a name="swap"></a>Kur

İki `valarray`öğelerini değiş tokuş eder.

```cpp
void swap(valarray& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Takas edilecek öğeleri sağlayan bir `valarray`.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, `*this` ve *sağ*arasındaki denetlenen dizileri değiştirir. Bu, sabit bir zamanda özel durum oluşturmaz ve iki denetimli sırada öğeleri belirten hiçbir başvuru, işaretçi veya yineleyiciyi geçersiz kılar.

## <a name="valarray"></a>valarray

Belirli bir boyutun bir valarray veya belirli bir değerin öğeleriyle ya da başka bir valarray ya da başka bir valarray alt kümesinin kopyası olarak oluşturur.

```cpp
valarray();

explicit valarray(
    size_t Count);

valarray(
    const Type& Val,
    size_t Count);

valarray(
    const Type* Ptr,
    size_t Count);

valarray(
    const valarray<Type>& Right);

valarray(
    const slice_array<Type>& SliceArray);

valarray(
    const gslice_array<Type>& GsliceArray);

valarray(
    const mask_array<Type>& MaskArray);

valarray(
    const indirect_array<Type>& IndArray);

valarray(
    valarray<Type>&& Right);

valarray(
    initializer_list<Type> IList);
```

### <a name="parameters"></a>Parametreler

*Sayı*\
Valarray içinde olacak öğe sayısı.

*Val*\
Valarray içindeki öğeleri başlatırken kullanılacak değer.

*Ptr*\
Valarray içindeki öğeleri başlatmak için kullanılacak değerlere yönelik işaretçi.

*Sağ*\
Yeni valarray 'yi başlatmak için mevcut bir valarray.

\ *bölümü*
Öğe değerleri, oluşturulmakta olan valarray öğelerini başlatırken kullanılacak olan bir slice_array.

*Gdilimleyicearray*\
Öğe değerleri, oluşturulmakta olan valarray öğelerini başlatırken kullanılacak olan bir gslice_array.

*Maskarray*\
Öğe değerleri, oluşturulmakta olan valarray öğelerini başlatırken kullanılacak olan bir mask_array.

*Indarray*\
Öğe değerleri, oluşturulmakta olan valarray öğelerini başlatırken kullanılacak olan bir indirect_array.

*Ilist*\
Kopyalanacak öğeleri içeren initializer_list.

### <a name="remarks"></a>Açıklamalar

İlk (varsayılan) Oluşturucu nesnesini boş bir diziye başlatır. Sonraki üç Oluşturucu her biri nesneyi aşağıdaki gibi bir *Count* öğeleri dizisine başlatır:

- Açık `valarray(size_t Count)`için her öğe varsayılan Oluşturucu ile başlatılır.

- `valarray(const Type& Val, Count)`için her öğe *Val*ile başlatılır.

- `valarray(const Type* Ptr, Count)`için `I` konumundaki öğe `Ptr`[`I`] ile başlatılır.

Kalan her Oluşturucu nesneyi bağımsız değişkende belirtilen alt küme tarafından belirlenen bir valarray\<türü > nesnesine başlatır.

Son Oluşturucu son ' a bir sonraki ile aynıdır, ancak [rvalue başvuru bildirimci: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

### <a name="example"></a>Örnek

```cpp
// valarray_ctor.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main()
{
    using namespace std;
    int i;

    // The second member function
    valarray<int> va(10);
    for (auto i : va){
        va[i] = 2 * (i + 1);
    }

    cout << "The operand valarray va is:\n(";
    for (auto i : va) {
        cout << " " << va[i];
    }
    cout << " )" << endl;

    slice Slice(2, 4, 3);

    // The fifth member function
    valarray<int> vaSlice = va[Slice];

    cout << "The new valarray initialized from the slice is vaSlice =\n"
        << "va[slice( 2, 4, 3)] = (";
    for (int i = 0; i < 3; i++) {
        cout << " " << vaSlice[i];
    }
    cout << " )" << endl;

    valarray<int> va2{{ 1, 2, 3, 4 }};
    for (auto& v : va2) {
        cout << v << " ";
    }
    cout << endl;
}
```

```Output
The operand valarray va is:
( 0 2 2 2 2 2 2 2 2 2 )
The new valarray initialized from the slice is vaSlice =
va[slice( 2, 4, 3)] = ( 0 0 0 )
1 2 3 4
```

## <a name="value_type"></a>value_type

Bir valarray içinde depolanan öğe türünü temsil eden bir tür.

```cpp
typedef Type value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, `Type`şablon parametresi için bir eş anlamlı.

### <a name="example"></a>Örnek

```cpp
// valarray_value_type.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
    using namespace std;
    int i;
    valarray<int> va ( 10 );
    for ( i = 0 ; i < 10 ; i += 2 )
        va [ i ] =  i;
    for ( i = 1 ; i < 10 ; i += 2 )
        va [ i ] =  -1;

    cout << "The initial operand valarray is:  ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << va [ i ] << " ";
    cout << ")." << endl;

    // value_type declaration and initialization:
    valarray<int>::value_type Right = 10;

    cout << "The decalared value_type Right is: "
            << Right << endl;
    va *= Right;
    cout << "The resulting valarray is:  ( ";
        for ( i = 0 ; i < 10 ; i++ )
            cout << va [ i ] << " ";
    cout << ")." << endl;
}
```

```Output
The initial operand valarray is:  ( 0 -1 2 -1 4 -1 6 -1 8 -1 ).
The decalared value_type Right is: 10
The resulting valarray is:  ( 0 -10 20 -10 40 -10 60 -10 80 -10 ).
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
