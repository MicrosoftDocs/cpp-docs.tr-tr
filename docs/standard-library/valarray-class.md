---
title: valarray Sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: abfac363388fc86a8b9c68df149bbe65fdd1d427
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482725"
---
# <a name="valarray-class"></a>valarray Sınıfı

Şablon sınıfı bir dizi öğe türü denetleyen bir nesneyi tanımlayan `Type` , bir dizi olarak depolanan, yüksek hızlı matematik işlemlerini gerçekleştirmek için tasarlanmış ve işlem performansına yönelik en iyi duruma getirilmiş.

## <a name="remarks"></a>Açıklamalar

Değerleri ve öğelerin sıralı bir dizi matematik kavramını gösterimini sırayla sıfırdan numaralı sınıftır. Sınıf yakın bir kapsayıcı gibi bazı destekler, ancak bazıları, bu birinci sınıf özellikleri sıra kapsayıcıları, gibi açıklanan [vektör](../standard-library/vector-class.md), destekler. Bu şablon sınıfının öğesinden iki önemli şekilde farklıdır:

- Karşılık gelen öğeleri arasında çok sayıda aritmetik işlemler tanımlar `valarray<Type>` aynı türde ve uzunluktaki, nesnelerin gibi *xarr* cos = ( *yarr*) + sin ( *zarr*).

- Çeşitli alt simge için ilginç şekillerde tanımlayan bir `valarray<Type>` aşırı yükleme tarafından nesnesi [işleci&#91;&#93;](#op_at).

Sınıfın bir nesnesi `Type`:

- Genel varsayılan oluşturucu, yıkıcı, kopya oluşturucu ve geleneksel davranış atama işleci vardır.

- Aritmetik işleçler ve kayan nokta türleriyle geleneksel davranışı için tanımlanan gerektiği gibi matematik işlevleri tanımlar.

Özellikle, kopya oluşturma ve atama tarafından izlenen varsayılan yapı arasında hiçbir farklar olabilir. Sınıfındaki nesneler üzerinde işlemler hiçbiri `Type` özel durumlar oluşturabilir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[valarray](#valarray)|Oluşturur bir `valarray` öğeleri belirli bir değer veya başka bir kopya olarak veya belirli bir boyut `valarray` veya başka bir alt `valarray`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[value_type](#value_type)|İçinde depolanan öğenin türünü temsil eden bir tür bir `valarray`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Uygula](#apply)|Her öğeye belirtilen işlev geçerli bir `valarray`.|
|[cshift](#cshift)|Tüm öğeleri periyodik olarak kaydırır bir `valarray` belirli sayıdaki uzaklığına göre.|
|[free](#free)|Tarafından kullanılan belleği serbest bırakma `valarray`.|
|[en fazla](#max)|En büyük öğeyi bulur bir `valarray`.|
|[Min](#min)|En küçük öğeyi bulur bir `valarray`.|
|[yeniden boyutlandırma](#resize)|İçindeki öğelerin sayısını değiştirir bir `valarray` ekleyerek veya kaldırarak öğeler belirtilen bir sayı.|
|[Kaydırma](#shift)|Tüm öğeleri kaydırır bir `valarray` belirli sayıdaki uzaklığına göre.|
|[Boyutu](#size)|İçindeki öğelerin sayısını bulur bir `valarray`.|
|[TOPLA](#sum)|İçindeki tüm öğelerin toplamını belirleyen bir `valarray` sıfır uzunlukta.|
|[değiştirme](#swap)||

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleci!](#op_not)|Mantıksal alan birli işleç `NOT` her öğe değerlerini bir `valarray`.|
|[operator%=](#op_mod_eq)|Bir dizinin öğeleri element-wise bölme kalanı tarafından belirtilen alır `valarray` veya öğe türü değeri.|
|[işleç & =](#op_amp_eq)|Bit düzeyinde alır `AND` bir dizideki öğelerin karşılık gelen öğelerle belirtilen bir ya da `valarray` veya öğe türü değeri.|
|[İşleç >> =](#op_gt_gt_eq)|Sağ-kaydırmalar her öğe için BITS, bir `valarray` işlenen belirtilen sayıda konumları veya ikincisine belirtilen aralığın öğe düzeyinde çarpımının bir miktar `valarray`.|
|[işleç << =](#op_lt_lt_eq)|Sol-kaydırmalar her öğe için BITS, bir `valarray` işlenen belirtilen sayıda konumları veya ikincisine belirtilen aralığın öğe düzeyinde çarpımının bir miktar `valarray`.|
|[operator*=](#op_star_eq)|Öğelerinin belirtilen değerle çarpar `valarray` veya işleneni aralığın öğe düzeyinde çarpımının, öğe türü değeri `valarray`.|
|[operator +](#op_add)|Birli işleç artı her öğe için geçerli bir `valarray`.|
|[operator+=](#op_add_eq)|Belirli bir öğe ekler `valarray` veya işleneni aralığın öğe düzeyinde çarpımının, öğe türü değeri `valarray`.|
|[operator-](#operator-)|İçindeki her öğeyi bir eksi uygulayan birli işleç bir `valarray`.|
|[-= işleci](#operator-_eq)|Belirli bir öğe çıkarır `valarray` veya bir işlenen aralığın öğe düzeyinde çarpımının, öğe türü değeri `valarray`.|
|[/ = işleci](#op_div_eq)|Bir işlenen böler `valarray` tarafından belirtilen öğeleri aralığın öğe düzeyinde çarpımının `valarray` veya öğe türünde bir değer.|
|[operator=](#op_eq)|Öğesine atar bir `valarray` değerleri doğrudan ya da başka bir parçası olarak belirtilen `valarray` ya da bir `slice_array`, `gslice_array`, `mask_array`, veya `indirect_array`.|
|[işleci&#91;&#93;](#op_at)|Bir öğenin veya belirtilen dizin veya belirtilen alt değeri için bir başvuru döndürür.|
|[operator^=](#op_xor_eq)|Aralığın öğe düzeyinde çarpımının özel mantıksal or işleci alır ( `XOR`) belirtilen valarray ya da öğe türünün bir değeri ile bir dizi.|
|[İşleç&#124;=](#op_or_eq)|Bit düzeyinde alır `OR` bir dizideki öğelerin karşılık gelen öğelerle belirtilen bir ya da `valarray` veya öğe türü değeri.|
|[işleç ~](#op_dtor)|Bit düzeyinde alır bir birli işleç `NOT` her öğe değerlerini bir `valarray`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<valarray >

**Namespace:** std

## <a name="apply"></a>  valarray::apply

Belirtilen işlev bir valarray her öğeye uygulanır.

```cpp
valarray<Type> apply(Type _Func(Type)) const;

valarray<Type> apply(Type _Func(constType&)) const;
```

### <a name="parameters"></a>Parametreler

*_Func(Type)*<br/>
İşlenen valarray her öğesine uygulanacak işlev nesnesi.

*_Func(const Type&)*<br/>
Const işlenen valarray her öğeye uygulanacak işlev nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri olan bir valarray `_Func` element-wise işlenen valarray öğelerine uygulanır.

### <a name="remarks"></a>Açıklamalar

Üye işlevi sınıfın bir nesnesi döndürür [valarray](../standard-library/valarray-class.md)**\<türü >**, uzunluğu [boyutu](#size), her biri öğeleri *miyim*olduğu `_Func((*this)[I])`.

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
/* Output:
The initial Right valarray is: ( 0 0 -2 3 0 -5 6 0 -8 9 )
The element-by-element result of applying MyApplyFunc to vaR is the
valarray: (  0 0 -4 6 0 -10 12 0 -16 18 )
*/
```

## <a name="cshift"></a>  valarray::cshift

Periyodik bir valarray tüm öğeleri belirli sayıdaki uzaklığına göre geçirir.

```cpp
valarray<Type> cshift(int count) const;
```

### <a name="parameters"></a>Parametreler

*Sayısı*<br/>
İleri kaydırılmasına öğeleridir basamak sayısı.

### <a name="return-value"></a>Dönüş Değeri

İçindeki tüm öğeleri taşındı yeni bir valarray *sayısı* periyodik olarak işlenen valarray konumlarını göre sola valarray önüne doğru konumları.

### <a name="remarks"></a>Açıklamalar

Pozitif değerini *sayısı* öğeleri periyodik olarak sol kaydırır *sayısı* yerleştirir.

Bir negatif bir değer *sayısı* öğeleri periyodik olarak doğru kayar *sayısı* yerleştirir.

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
/* Output:
The operand valarray va1 is: ( 0 1 2 3 4 5 6 7 8 9)
The cyclically shifted valarray va1 is:
va1.cshift (4) = ( 4 5 6 7 8 9 0 1 2 3)
The operand valarray va2 is: ( 10 9 8 7 6 5 4 3 2 1)
The cyclically shifted valarray va2 is:
va2.shift (-4) = ( 4 3 2 1 10 9 8 7 6 5)
*/
```

## <a name="free"></a>  valarray::Free

Valarray tarafından kullanılan belleği serbest bırakır.

```cpp
void free();
```

### <a name="remarks"></a>Açıklamalar

Bu standart olmayan bir işlev boş bir valarray atama için eşdeğerdir. Örneğin:

```cpp
valarray<T> v;
v = valarray<T>();

// equivalent to v.free()
```

## <a name="max"></a>  valarray::Max

En büyük öğe içinde bir valarray bulur.

```cpp
Type max() const;
```

### <a name="return-value"></a>Dönüş Değeri

İşlenen valarray öğelerin maksimum değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi uygulayarak değerlerini karşılaştırır **işleci\<**  veya **işleci >** sınıfına ait öğelerin çiftleri arasındaki `Type`, öğe için hangi işleçleri sağlanmalıdır `Type`.

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
/* Output:
The operand valarray is: ( 0 1 8 3 7 5 6 13 2 9 ).
The largest element in the valarray is: 13.
*/
```

## <a name="min"></a>  valarray::Min

En küçük öğe içinde bir valarray bulur.

```cpp
Type min() const;
```

### <a name="return-value"></a>Dönüş Değeri

İşlenen valarray öğeleri minimum değer.

### <a name="remarks"></a>Açıklamalar

Üye işlevi uygulayarak değerlerini karşılaştırır **işleci\<**  veya **işleci >** sınıfına ait öğelerin çiftleri arasındaki `Type`, öğe için hangi işleçleri sağlanmalıdır `Type`.

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

## <a name="op_not"></a>  valarray::operator!

Mantıksal alan birli işleç **değil** her öğenin bir valarray değerleri.

```cpp
valarray<bool> operator!() const;
```

### <a name="return-value"></a>Dönüş Değeri

Valarray olumsuzlama işlenen valarray öğe değerlerini Boolean değerleri.

### <a name="remarks"></a>Açıklamalar

Mantıksal işleyişini **değil** çünkü bu sıfırlardan olanları içine dönüştürür ve tüm sıfır olmayan değerler olanları olarak değerlendirir ve bunları sıfır dönüştürür öğelerin belirtimini olumsuz duruma getirir. İşlenen valarray aynı boyutta döndürülen valarray Boolean değeri değil.

Ayrıca mevcuttur bit düzeyinde **değil**[valarray::operator ~](#op_dtor) ikili gösterimini içinde tek tek bit düzeyinde verilerek **char** ve **int**  bir valarray öğeleri.

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
/* Output:
The initial valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).
The element-by-element result of the logical NOT operator! is the
valarray: ( 1 1 1 0 1 0 1 0 1 0 ).
*/
```

## <a name="op_mod_eq"></a>  valarray::operator%=

Bir dizinin öğeleri belirtilen valarray veya öğe türü değeri element-wise bölme kalanı alır.

```cpp
valarray<Type>& operator%=(const valarray<Type>& right);

valarray<Type>& operator%=(const Type& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Valarray veya değeri aynı olan element-wise, işlenen valarray bölmek için işlenen valarray bir öğe türü.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri bölmeden aralığın öğe düzeyinde çarpımının işlenen valarray biri olan bir valarray tarafından *sağ*

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
/* Output:
The initial valarray is: ( 53 -67 53 -67 53 -67 ).
The initial  right valarray is: ( 1 4 7 10 13 16 ).
The remainders from the element-by-element division is the
valarray: ( 0 -3 4 -7 1 -3 ).
*/
```

## <a name="and_eq"></a>  valarray::operator&amp;=

Bit düzeyinde alır **ve** bir dizideki öğelerin belirtilen valarray karşılık gelen öğelerle veya öğe türü değeri.

```cpp
valarray<Type>& operator&=(const valarray<Type>& right);

valarray<Type>& operator&=(const Type& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Valarray veya bir öğe türünün, birleştirilecek olan işlenen valarray aynı, aralığın öğe düzeyinde çarpımının, mantıksal olarak değer `AND` işlenen valarray ile.

### <a name="return-value"></a>Dönüş Değeri

Aralığın öğe düzeyinde çarpımının öğeleri olan bir valarray mantıksal `AND` tarafından işlenen valarray, *sağ*

### <a name="remarks"></a>Açıklamalar

Bit düzeyinde işlem yalnızca bit işlemek için kullanılabilir **char** ve **int** veri türleri ve çeşitleri değil **float**, **çift**, **longdouble**, **void**, **bool**, ya da diğer, daha karmaşık veri türleri.

Bit düzeyinde AND mantıksal olarak aynı doğru tablosu sahip `AND` ancak tek bit düzeyinde veri türü için geçerlidir. BITS verilen *b*1 ve *b*2 *b*1 `AND` *b*2 **true** bitlerin her ikisi de doğruysa; **false** en az biri yanlış olması durumunda.

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
/* Output:
The initial valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).
The element-by-element result of the logical AND operator&= is the
valarray: ( 0 0 0 2 0 4 0 6 0 8 ).
*/
```

## <a name="op_gt_gt_eq"></a>  valarray::operator&gt;&gt;=

Valarray işlenenin belirtilen sayıda konumları veya ikinci bir valarray tarafından belirtilen aralığın öğe düzeyinde çarpımının bir miktar her öğe için BITS sağa kaydırır.

```cpp
valarray<Type>& operator>>=(const valarray<Type>& right);

valarray<Type>& operator>>=(const Type& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Sağa kaydırma veya valarray belirten değeri öğeleri sağa kaydırma aralığın öğe düzeyinde çarpımının miktarını belirtin.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri yapılmış bir valarray belirtilen miktarı sağa kaydırılacak *doğru*.

### <a name="remarks"></a>Açıklamalar

İşaretli sayılara korunur, imzalar vardır.

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
/* Output:
The initial operand valarray is: ( 64 -64 64 -64 64 -64 64 -64 ).
The  right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the right shift is the
valarray: ( 64 -32 16 -8 4 -2 1 -1 ).
*/
```

## <a name="op_lt_lt_eq"></a>  valarray::operator&lt;&lt;=

Valarray işlenenin belirtilen sayıda konumları veya ikinci bir valarray tarafından belirtilen aralığın öğe düzeyinde çarpımının bir miktar her öğe için BITS Sola kaydırır.

```cpp
valarray<Type>& operator<<=(const valarray<Type>& right);

valarray<Type>& operator<<=(const Type& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Sola kaydırma veya valarray belirten bir değeri, öğeleri sola kaydırma aralığın öğe düzeyinde çarpımının miktarını belirtin.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen miktarı öğeleri kaydırılacak bir valarray sol *doğru*.

### <a name="remarks"></a>Açıklamalar

İşaretli sayılara korunur, imzalar vardır.

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
/* Output:
The initial operand valarray is: ( 1 -1 1 -1 1 -1 1 -1 ).
The  right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the left shift
on the operand array is the valarray:
( 1 -2 4 -8 16 -32 64 -128 ).
*/
```

## <a name="op_star_eq"></a>  valarray::operator * =

Belirtilen valarray öğelerini veya öğe türünde bir değer için bir işlenen valarray element-wise, çarpar.

```cpp
valarray<Type>& operator*=(const valarray<Type>& right);

valarray<Type>& operator*=(const Type& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Valarray veya değeri aynı olan element-wise, işlenen valarray çarpmak için işlenen valarray bir öğe türü.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri işlenen valarray aralığın öğe düzeyinde çarpımının ürünü olan bir valarray ve *doğru*.

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

## <a name="op_add"></a>  valarray::operator +

Birli işleç artı bir valarray her öğe için geçerlidir.

```cpp
valarray<Type> operator+() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu işlenen dizinin öğeleri olan bir valarray.

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
/* Output:
The initial valarray is:  ( 0 0 -2 2 -4 4 -6 6 -8 8 ).
The element-by-element result of the operator+ is the
valarray: ( 0 0 -2 2 -4 4 -6 6 -8 8 ).
*/
```

## <a name="op_add_eq"></a>  valarray::operator +=

Element-wise, belirtilen valarray öğelerini veya öğe türünde bir değer için bir işlenen valarray ekler.

```cpp
valarray<Type>& operator+=(const valarray<Type>& right);

valarray<Type>& operator+=(const Type& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Valarray veya bir öğe türü, element-wise, için işlenen valarray eklenmesi için işlenen valarray, aynı değeri.

### <a name="return-value"></a>Dönüş Değeri

İşlenen valarray aralığın öğe düzeyinde çarpımının toplamını öğeleri olan bir valarray ve *doğru*.

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
/* Output:
The initial valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).
The initial  right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the sum is the
valarray: ( 2 0 4 2 6 4 8 6 ).
*/
```

## <a name="valarray__operator-"></a>  valarray::operator-

Birli işleç eksi bir valarray her öğe için geçerlidir.

```cpp
valarray<Type> operator-() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir valarray öğeleri işlenen dizinin olanlardır.

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
/* Output:
The initial valarray is:  ( 0 0 -2 2 -4 4 -6 6 -8 8 ).
The element-by-element result of the operator+ is the
valarray: ( 0 0 2 -2 4 -4 6 -6 8 -8 ).
*/
```

## <a name="valarray__operator-_eq"></a>  valarray::operator-=

Belirtilen valarray öğelerini veya öğe türünde bir değer element-wise, bir işlenen valarray çıkarır.

```cpp
valarray<Type>& operator-=(const valarray<Type>& right);

valarray<Type>& operator-=(const Type& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Valarray veya bir öğe türü, element-wise, işlenen valarray çıkarılır için işlenen valarray, aynı değeri.

### <a name="return-value"></a>Dönüş Değeri

İşlenen valarray aralığın öğe düzeyinde çarpımının fark öğeleri olan bir valarray ve *doğru*.

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
/* Output:
The initial valarray is: ( 10 0 10 0 10 0 10 0 ).
The initial  right valarray is: ( 0 1 2 3 4 5 6 7 ).
The element-by-element result of the difference is the
valarray: ( 10 -1 8 -3 6 -5 4 -7 ).
*/
```

## <a name="op_div_eq"></a>  valarray::operator / =

Bir işlenen valarray element-wise belirtilen valarray öğelerini veya öğe türü değeri böler.

```cpp
valarray<Type>& operator/=(const valarray<Type>& right);

valarray<Type>& operator/=(const Type& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Valarray veya bir öğe türü, yani, element-wise, işlenen valarray bölünür işlenen valarray aynı değeri.

### <a name="return-value"></a>Dönüş Değeri

İşlenen valarray aralığın öğe düzeyinde çarpımının kalanını öğeleri olan bir valarray bölünmüş tarafından *doğru*.

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
/* Output:
The initial valarray is: ( 100 -100 100 -100 100 -100 ).
The initial Right valarray is: ( 0 2 4 6 8 10 ).
The element-by-element result of the quotient is the
valarray: ( inf -50 25 -16.6667 12.5 -10 ).
*/
```

## <a name="op_eq"></a>  valarray::operator =

Öğe değerlerini doğrudan ya da diğer bazı valarray veya slice_array, gslice_array, mask_array veya indirect_array parçası olarak belirtilen bir valarray atar.

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

*sağ*<br/>
İşlenen valarray kopyalanacak valarray.

*VAL*<br/>
İşlenen valarray öğelerine atanacak değer.

*_Slicearray*<br/>
İşlenen valarray kopyalanacak slice_array.

*_Gslicearray*<br/>
İşlenen valarray kopyalanacak gslice_array.

*_Maskarray*<br/>
İşlenen valarray kopyalanacak mask_array.

*_Indarray*<br/>
İşlenen valarray kopyalanacak indirect_array.

### <a name="return-value"></a>Dönüş Değeri

Denetlenen dizideki ilk üye işleci tarafından denetlenen dizinin bir kopyasını değiştirir *doğru*.

İkinci üye işleci ile ilk olarak, ancak aynı olan bir [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

Üçüncü üye işleci değerinin denetlenen dizideki her öğe bir kopyasıyla değiştirir. *val*.

Bu öğeleri yalnızca oluşturulan kendi bağımsız seçili denetlenen dizinin kalan üye işleçleri değiştirin [işleci&#91;&#93;](#op_at).

Değiştirme denetlenen dizideki bir üyenin değeri ilk denetlenen dizideki bir üyede bağlıysa sonuç tanımsızdır.

### <a name="remarks"></a>Açıklamalar

Denetlenen dizinin uzunluğu değişirse, sonuç genellikle tanımsızdır. Bu uygulama, ancak yalnızca herhangi bir işaretçiler veya başvurular denetlenen dizideki öğelerin geçersiz kılmak için etkisidir.

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
/* Output:
The operand valarray va is: 0 1 2 3 4 5 6 7 8 9
The operand valarray vaR is: 10 9 8 7 6 5 4 3 2 1
The reassigned valarray va is: 10 9 8 7 6 5 4 3 2 1
The reassigned valarray va is: 10 10 10 10 10 10 10 10 10 10
*/
```

## <a name="op_at"></a>  valarray::operator]

Bir öğenin veya belirtilen dizin veya belirtilen alt değeri için bir başvuru döndürür.

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

*_Off*<br/>
Bir değerin atanacağı öğe dizini.

*_Slicearray*<br/>
Bir slice_array Seçilecek veya yeni bir valarray için döndürülen bir alt kümesini belirten bir valarray biri.

*_Gslicearray*<br/>
Bir gslice_array Seçilecek veya yeni bir valarray için döndürülen bir alt kümesini belirten bir valarray biri.

*_Boolarray*<br/>
Bir bool_array Seçilecek veya yeni bir valarray için döndürülen bir alt kümesini belirten bir valarray biri.

*_Indarray*<br/>
Bir indirect_array Seçilecek veya yeni bir valarray için döndürülen bir alt kümesini belirten bir valarray biri.

### <a name="return-value"></a>Dönüş Değeri

Bir öğe veya değerini belirtilen dizin veya belirtilen bir alt kümesine başvuru.

### <a name="remarks"></a>Açıklamalar

Üye işleci bu tarafından denetlenen arasından öğelerin sıralarının seçmek için çeşitli yollar sağlamak için aşırı yüklenmiş  <strong>\*bu</strong>. İlk beş üye işleçleri grubunu iş çeşitli aşırı yüklemeleri ile birlikte [işleç =](#op_eq) (ve diğer atama işleçleri) (denetlenen bir dizi dilimleme) seçmeli değiştirme işlemine izin vermek için. Seçilen öğeleri mevcut olması gerekir.

Kullanılarak derlendiğinde [_ıterator_debug_level](../standard-library/iterator-debug-level.md) valarray sınırları dışında bir öğeye erişmeyi denerseniz, 1 veya 2 ' tanımlanan, bir çalışma zamanı hatası oluşur.  Bkz: [Checked Iterators](../standard-library/checked-iterators.md) daha fazla bilgi için.

### <a name="example"></a>Örnek

Örnekler için bkz: [slice::slice](../standard-library/slice-class.md#slice) ve [gslice::gslice](../standard-library/gslice-class.md#gslice) bildirme ve kullanma işleci ilişkin bir örnek için.

## <a name="op_xor_eq"></a>  valarray::operator^=

Aralığın öğe düzeyinde çarpımının özel mantıksal or işleci alır ( **XOR**) belirtilen valarray ya da öğe türünün bir değeri ile bir dizi.

```cpp
valarray<Type>& operator|=(const valarray<Type>& right);

valarray<Type>& operator|=(const Type& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Valarray veya bir öğe türü, birleştirilecek olan işlenen valarray aynı, aralığın öğe düzeyinde çarpımının, mantıksal özel tarafından değerini **XOR** işlenen valarray ile.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri olan mantıksal aralığın öğe düzeyinde çarpımının, özel bir valarray **XOR** işlenen valarray, ve *doğru*.

### <a name="remarks"></a>Açıklamalar

Mantıksal veya, olarak adlandırılan özel **XOR**, semantiği aşağıdaki: öğe belirtildiğinde *e*1 ve *e*2 *e*1  **XOR** *e*2 **true** öğelerden tam olarak birine true; değilse **false** iki öğeyi yanlışsa veya her iki öğeleri true ise.

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
/* Output:
The initial operand valarray is:  ( 1 0 1 0 1 0 1 0 1 0 ).
The  right valarray is: ( 0 0 1 3 3 4 6 6 7 9 ).
The element-by-element result of the bitwise XOR operator^= is the
valarray: ( 1 0 0 3 2 4 7 6 6 9 ).
*/
```

## <a name="op_or_eq"></a>  valarray::operator&#124;=

Bit düzeyinde alır `OR` bir dizideki öğelerin belirtilen valarray karşılık gelen öğelerle veya öğe türü değeri.

```cpp
valarray<Type>& operator|=(const valarray<Type>& right);

valarray<Type>& operator|=(const Type& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Valarray veya bir öğe türü, birleştirilecek olan işlenen valarray aynı, aralığın öğe düzeyinde çarpımının, bit düzeyinde tarafından değerini `OR` işlenen valarray ile.

### <a name="return-value"></a>Dönüş Değeri

Aralığın öğe düzeyinde çarpımının bit düzeyinde olan öğeleri olan bir valarray `OR` tarafından işlenen valarray, *doğru*.

### <a name="remarks"></a>Açıklamalar

Bit düzeyinde işlem yalnızca bit işlemek için kullanılabilir **char** ve **int** veri türleri ve çeşitleri değil **float**, **çift**, **longdouble**, **void**, **bool**, ya da diğer, daha karmaşık veri türleri.

Bit düzeyinde `OR` mantıksal olarak aynı gerçekte tablo `OR` ancak tek bit düzeyinde veri türü için geçerlidir. BITS verilen *b*1 ve *b*2 *b*1 `OR` *b*2 **true** en az bir bit ise TRUE; **false** bitlerin her ikisi de false ise.

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
/* Output:
The initial operand valarray is:
( 1 0 1 0 1 0 1 0 1 0 ).
The  right valarray is:
( 0 0 1 3 3 4 6 6 7 9 ).
The element-by-element result of the logical OR
operator|= is the valarray:
( 1 0 1 3 3 4 7 6 7 9 ).
*/
```

## <a name="op_dtor"></a>  valarray::operator ~

Bit düzeyinde alır bir birli işleç `NOT` her öğenin bir valarray değerleri.

```cpp
valarray<Type> operator~() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bit düzeyinde Boole değerleri valarray `NOT` işlenen valarray öğe değerlerini.

### <a name="remarks"></a>Açıklamalar

Bit düzeyinde işlem yalnızca bit işlemek için kullanılabilir **char** ve **int** veri türleri ve çeşitleri değil **float**, **çift**, **longdouble**, **void**, **bool** veya diğer, daha karmaşık veri türleri.

Bit düzeyinde `NOT` mantıksal olarak aynı gerçekte tablo `NOT` ancak tek bit düzeyinde veri türü için geçerlidir. Bit verilen *b*, ~ *b* true, *b* yanlış olduğunda, bayrak yoksa yanlış *b* geçerlidir. Mantıksal **değil**[işleci!](#op_not) Tüm sıfır olmayan değerler olarak sayım bir öğe düzeyi geçerli **true**, ve sonucu bir valarray Boolean değeri. Bit düzeyinde `NOToperator~`, aksine, değerleri 0 veya 1, bit düzeyinde işlemin sonucunu bağlı olarak başka bir valarray neden olabilir.

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

/* Output:
The initial valarray <unsigned short int> is:  ( 0 5 2 15 4 25 6 35 8 45 ).
The element-by-element result of the bitwise NOT operator~ is the
valarray: ( 65535 65530 65533 65520 65531 65510 65529 65500 65527 65490 ).

The initial valarray <int> is:  ( 0 -2 2 -6 4 -10 6 -14 8 -18 ).
The element-by-element result of the bitwise NOT operator~ is the
valarray: ( -1 1 -3 5 -5 9 -7 13 -9 17 ).
The element-by-element result of adding one
is the negative of the original elements the
valarray: ( 0 2 -2 6 -4 10 -6 14 -8 18 ).
*/
```

## <a name="resize"></a>  valarray::Resize

Belirtilen bir sayıya bir valarray içindeki öğelerin sayısını değiştirir.

```cpp
void resize(
    size_t _Newsize);

void resize(
    size_t _Newsize,
    const Type val);
```

### <a name="parameters"></a>Parametreler

*_Newsize*<br/>
Yeniden boyutlandırılan valarray içindeki öğe sayısı.

*VAL*<br/>
Yeniden boyutlandırılan valarray öğelerine verilecek değer.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi öğeleri kendi varsayılan oluşturucu ile başlatır.

Herhangi bir işaretçiler veya başvurular denetlenen dizideki öğelerin geçersiz kılınır.

### <a name="example"></a>Örnek

Aşağıdaki örnek, valarray::resize üye işlevinin kullanımını gösterir.

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

## <a name="shift"></a>  valarray::Shift

Tüm öğeleri bir valarray basamak tarafından belirtilen sayıda kaydırır.

```cpp
valarray<Type> shift(int count) const;
```

### <a name="parameters"></a>Parametreler

*Sayısı*<br/>
İleri kaydırılmasına öğeleridir basamak sayısı.

### <a name="return-value"></a>Dönüş Değeri

İçindeki tüm öğeleri taşındı yeni bir valarray *sayısı* sol işlenen valarray konumlarını göre valarray önüne doğru konumları.

### <a name="remarks"></a>Açıklamalar

Pozitif değerini *sayısı* öğeleri Sola kaydırır *sayısı* , sıfır dolgulu yerleştirir.

Bir negatif bir değer *sayısı* öğeleri sağa kaydırır *sayısı* , sıfır dolgulu yerleştirir.

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
/* Output:
The operand valarray va1(10) is: ( 0 1 2 3 4 5 6 7 8 9 ).
The shifted valarray va1 is: va1.shift (4) = ( 4 5 6 7 8 9 0 0 0 0 ).
The operand valarray va2(10) is: ( 10 9 8 7 6 5 4 3 2 1 ).
The shifted valarray va2 is: va2.shift (-4) = ( 0 0 0 0 10 9 8 7 6 5 ).
*/
```

## <a name="size"></a>  valarray::size

Bir valarray öğelerin sayısını bulur.

```cpp
size_t size() const;
```

### <a name="return-value"></a>Dönüş Değeri

İşlenen valarray içindeki öğe sayısı.

### <a name="example"></a>Örnek

Aşağıdaki örnek, valarray::size üye işlevinin kullanımını gösterir.

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

## <a name="sum"></a>  valarray::Sum

Sıfır dışında uzunlukta bir valarray içindeki tüm öğelerin toplamını belirler.

```cpp
Type sum() const;
```

### <a name="return-value"></a>Dönüş Değeri

İşlenen valarray öğelerin toplamı.

### <a name="remarks"></a>Açıklamalar

Uzunluğu birden fazla ise, üye işlev değerleri toplama uygulayarak ekler `operator+=` sınıfına ait öğelerin çiftleri arasındaki `Type`, hangi işleci, sonuç olarak, sağlanmalı türü öğeler için `Type`.

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
/* Output:
The operand valarray va (10) is: ( 0 1 2 3 4 5 6 7 8 9 ).
The sum of elements in the valarray is: 45.
*/
```

## <a name="swap"></a>  valarray::Swap

İki öğeleri birbiriyle değiştirir `valarray`s.

```cpp
void swap(valarray& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*sağ*|A `valarray` değiştirilecek öğeleri sağlayan.|

### <a name="remarks"></a>Açıklamalar

Denetlenen diziyi üye işlevi değiştirir `*this` ve *doğru*. Bunu Sabit sürede yapar, hiçbir özel durum oluşturur ve hiçbir başvurular, işaretçiler veya iki denetlenen dizinin öğelerini belirlemek yineleyicileri geçersiz kılar.

## <a name="valarray"></a>  valarray::valarray

Belirli bir boyut veya belirli bir değer veya bir kopyasını başka bir valarray veya başka bir valarray alt öğeleri ile bir valarray oluşturur.

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

*Sayısı*<br/>
Valarray içinde olacak şekilde öğe sayısı.

*VAL*<br/>
Valarray öğeleri başlatılırken kullanılacak değer.

*PTR*<br/>
Valarray öğeleri başlatmak için kullanılacak değerler için işaretçi.

*sağ*<br/>
Mevcut bir valarray yeni valarray başlatılamadı.

*SliceArray*<br/>
Valarray yapılandırılmakta öğeleri başlatılırken kullanılacak öğe değerleri olan bir slice_array.

*GsliceArray*<br/>
Valarray yapılandırılmakta öğeleri başlatılırken kullanılacak öğe değerleri olan bir gslice_array.

*MaskArray*<br/>
Valarray yapılandırılmakta öğeleri başlatılırken kullanılacak öğe değerleri olan bir mask_array.

*IndArray*<br/>
Valarray yapılandırılmakta öğeleri başlatılırken kullanılacak öğe değerleri olan bir indirect_array.

*IList*<br/>
Kopyalanacak öğe içeren initializer_list.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu (varsayılan), boş bir dizi nesneyi başlatır. Sonraki üç oluşturucuları her nesnenin bir dizi başlatma *sayısı* aşağıdaki gibi öğeleri:

- İçin açık `valarray(size_t Count)`, her öğe varsayılan oluşturucu ile başlatılır.

- İçin `valarray(const Type& Val, Count)`, her öğe ile başlatılır *Val*.

- İçin `valarray(const Type* Ptr, Count)`, konumunda öğeyi `I` ile başlatılmış `Ptr`[ `I`].

Geri kalan her Oluşturucusu bir valarray nesneyi başlatır\<türü > bağımsız değişkeni olarak belirtilen alt tarafından belirlenen bir nesne.

Son Oluşturucu sonraki son olarak, ancak ile aynıdır bir [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

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

## <a name="value_type"></a>  valarray::value_type

Bir valarray içinde depolanan öğenin türünü temsil eden tür.

```cpp
typedef Type value_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `Type`.

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
/* Output:
The initial operand valarray is:  ( 0 -1 2 -1 4 -1 6 -1 8 -1 ).
The decalared value_type Right is: 10
The resulting valarray is:  ( 0 -10 20 -10 40 -10 60 -10 80 -10 ).
*/
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
