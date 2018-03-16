---
title: "valarray sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1325bcdbf00e217391ac7df4f583750b1fba4090
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2018
---
# <a name="valarray-class"></a>valarray Sınıfı
Şablon sınıfı türündeki öğeler bir dizi denetimleri bir nesneyi tanımlayan **türü** , bir dizi olarak depolanan, yüksek hızlı matematik işlemlerini gerçekleştirmek için tasarlanmış ve hesaplama performans için en iyi duruma getirilmiş.  
  
## <a name="remarks"></a>Açıklamalar  
 Değerleri ve öğeleri sıralı bir dizi matematiksel kavramı gösterimini sırayla sıfırdan numaralı sınıftır. Sınıf yakın bir kapsayıcı olarak bazı destekler, ancak tüm, bu birinci sınıf özellikleri sıra kapsayıcıları, gibi açıklanan [vektör](../standard-library/vector-class.md), destekler. Şablon sınıfı öğesinden iki önemli yollar bakımından farklılık gösterir:  
  
-   Karşılık gelen öğeleri arasında çok sayıda aritmetik işlemler tanımlar **valarray\<türü >** aynı türde ve uzunluk nesneleri gibi *xarr* cos = ( *yarr*) + sin ( *zarr*).  
  
-   Çeşitli alt simge için ilginç şekillerde tanımlayan bir **valarray\<türü >** aşırı yüklemesi tarafından nesne [işleci&#91;&#93;](#op_at).  
  
 Sınıfın bir nesnesi **türü**:  
  
-   Genel varsayılan oluşturucu, yıkıcı, kopya oluşturucu ve geleneksel davranışı atama işleci sahiptir.  
  
-   Aritmetik işleçler ve kayan nokta türleri için geleneksel davranışı ile tanımlanan gerektiği gibi matematik işlevleri tanımlar.  
  
 Özellikle, kopya oluşturma ve atama tarafından izlenen varsayılan yapım arasında hiçbir küçük farklılıklar olabilir. Sınıfındaki nesneler üzerinde işlemler hiçbiri **türü** özel durumlar oluşturma.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[valarray](#valarray)|Oluşturan bir `valarray` belirli bir boyuta veya belirli bir değerin veya başka bir kopya olarak öğelerle `valarray` veya başka bir alt `valarray`.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[value_type](#value_type)|Depolanan öğenin türünü temsil eden bir tür bir `valarray`.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[Uygula](#apply)|Belirtilen işlev her öğeye uygular bir `valarray`.|  
|[cshift](#cshift)|Tüm öğeleri cyclically kaydırır bir `valarray` konumlar belirtilen sayısı.|  
|[free](#free)|Tarafından kullanılan bellek boşaltır `valarray`.|  
|[max](#max)|En büyük öğeyi bulur bir `valarray`.|  
|[min](#min)|En küçük öğeyi bulur bir `valarray`.|  
|[resize](#resize)|Öğelerin sayısını değiştirir bir `valarray` ekleyerek veya kaldırarak gerektiği gibi öğeleri belirtilen bir sayı.|  
|[shift](#shift)|Tüm öğeleri kaydırır bir `valarray` konumlar belirtilen sayısı.|  
|[Boyutu](#size)|Öğe sayısı bulur bir `valarray`.|  
|[sum](#sum)|Tüm öğelerin toplamı, belirleyen bir `valarray` sıfır uzunluğunda.|  
|[Değiştirme](#swap)||  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleci!](#op_not)|Mantıksal edinir birli işleç `NOT` her bir öğe değerini bir `valarray`.|  
|[operator%=](#op_mod_eq)|Ya da belirtilen bir dizi öğelerini element-wise ayırma kalan edinir `valarray` veya öğesi türünde bir değer.|  
|[operator & =](#op_amp_eq)|Bit düzeyinde alır `AND` dizisindeki öğelerin ile ilgili öğeleri belirtilen bir ya da `valarray` veya öğesi türünde bir değer ile.|  
|[İşleç >> =](#op_gt_gt_eq)|Sağa kaydırmalar her öğe için BITS, bir `valarray` işlenen belirtilen sayıda konumlar veya saniyenin tarafından belirtilen bir element-wise miktar `valarray`.|  
|[işleç << =](#op_lt_lt_eq)|Sola kaydırır her öğe için BITS, bir `valarray` işlenen belirtilen sayıda konumlar veya saniyenin tarafından belirtilen bir element-wise miktar `valarray`.|  
|[operator*=](#op_star_eq)|Öğelerini belirtilen değerle çarpar `valarray` veya element-wise işlenen öğe türü değeri `valarray`.|  
|[operator+](#op_add)|Her bir öğe artı uygulandığı birli işleç bir `valarray`.|  
|[operator+=](#op_add_eq)|Belirtilen bir öğelerini ekler `valarray` veya element-wise işlenen öğe türü değeri `valarray`.|  
|[operator-](#operator-)|Her bir öğe eksi uygulandığı birli işleç bir `valarray`.|  
|[operator-=](#operator-_eq)|Belirtilen bir öğelerini çıkarır `valarray` veya element-wise işleneni öğe türü değeri `valarray`.|  
|[operator/=](#op_div_eq)|İşleneni böler `valarray` belirtilen öğelerini tarafından element-wise `valarray` veya öğesi türünde bir değer.|  
|[operator=](#op_eq)|Öğelerine atar bir `valarray` değerleri doğrudan veya başka bir parçası olarak belirtilen `valarray` ya da bir `slice_array`, `gslice_array`, `mask_array`, veya `indirect_array`.|  
|[işleci&#91;&#93;](#op_at)|Bir öğenin veya belirtilen dizin veya belirtilen bir alt değeri bir başvuru döndürür.|  
|[operator^=](#op_xor_eq)|Element-wise özel mantıksal or işleci alır ( `XOR`) belirtilen valarray veya öğesi türünde bir değer içeren bir dizi.|  
|[İşleç&#124;=](#op_or_eq)|Bit düzeyinde alır `OR` dizisindeki öğelerin ile ilgili öğeleri belirtilen bir ya da `valarray` veya öğesi türünde bir değer ile.|  
|[operator~](#op_dtor)|Bit düzeyinde edinir birli işleç `NOT` her bir öğe değerini bir `valarray`.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<valarray >  
  
 **Namespace:** std  
  
##  <a name="apply"></a>  valarray::apply  
 Belirtilen işlev, her bir valarray öğesine uygulanır.  
  
```  
valarray<Type> apply(Type _Func(Type)) const;

valarray<Type> apply(Type _Func(constType&)) const;
```  
  
### <a name="parameters"></a>Parametreler  
 *_Func(Type)*  
 İşlenen valarray her öğeye uygulanacak işlev nesnesi.  
  
 *_Func(const Type&)*  
 İşlenen valarray her öğeye uygulanacak const işlev nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeleri olan bir valarray `_Func` element-wise işlenen valarray öğelerine uygulanır.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini sınıfın bir nesnesi döndürür [valarray](../standard-library/valarray-class.md)**\<türü >**, uzunluğu [boyutu](#size), her öğeleri `I` olan**func**((  **\*bu**) [ `I`]).  
  
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
\* Output:   
The initial Right valarray is: ( 0 0 -2 3 0 -5 6 0 -8 9 )  
The element-by-element result of applying MyApplyFunc to vaR is the  
valarray: (  0 0 -4 6 0 -10 12 0 -16 18 )  
*\  
```  
  
##  <a name="cshift"></a>  valarray::cshift  
 Cyclically bir valarray tüm öğeler tarafından belirtilen konumlar sayısı kaydırır.  
  
```  
valarray<Type> cshift(int count) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `count`  
 Öğeleri İleri gölgeye üzeresiniz basamak sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hangi tüm öğeleri taşındı yeni bir valarray `count` cyclically işlenen valarray içinde konumlarına göre sol valarray önüne doğru konumlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Pozitif bir değer `count` öğeleri cyclically Sola kaydırır `count` yerleştirir.  
  
 Negatif değerini `count` cyclically sağ öğeleri kaydırır `count` yerleştirir.  
  
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
\* Output:   
The operand valarray va1 is: ( 0 1 2 3 4 5 6 7 8 9)  
The cyclically shifted valarray va1 is:  
va1.cshift (4) = ( 4 5 6 7 8 9 0 1 2 3)  
The operand valarray va2 is: ( 10 9 8 7 6 5 4 3 2 1)  
The cyclically shifted valarray va2 is:  
va2.shift (-4) = ( 4 3 2 1 10 9 8 7 6 5)  
*\  
```  
  
##  <a name="free"></a>  valarray::Free  
 Valarray tarafından kullanılan belleği serbest bırakır.  
  
```  
void free();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu standart olmayan işlevi, boş bir valarray atama için eşdeğerdir. Örneğin:  
  
```  
valarray<T> v;  
v = valarray<T>();

// equivalent to v.free()  
```  
  
##  <a name="max"></a>  valarray::Max  
 En büyük öğesi bir valarray bulur.  
  
```  
Type max() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 En yüksek değer işleneni valarray öğeleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi uygulayarak değerlerini karşılaştırır **işleci\<**  veya **işleci >** sınıfının öğeleri çiftleri arasındaki **türü**, hangi işleçlerini olmalıdır öğe için sağlanan **türü**.  
  
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
\* Output:   
The operand valarray is: ( 0 1 8 3 7 5 6 13 2 9 ).  
The largest element in the valarray is: 13.  
*\  
```  
  
##  <a name="min"></a>  valarray::Min  
 En küçük öğenin bir valarray bulur.  
  
```  
Type min() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlenen valarray öğeleri en küçük değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi uygulayarak değerlerini karşılaştırır **işleci\<**  veya **işleci >** sınıfının öğeleri çiftleri arasındaki **türü**, hangi işleçlerini olmalıdır öğe için sağlanan **türü**.  
  
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
\* Output:   
The operand valarray is: ( 0 2 3 -3 8 0 -6 14 -3 -9 ).  
The smallest element in the valarray is: -9.  
*\  
```  
  
##  <a name="op_not"></a>  valarray::operator!  
 Mantıksal edinir birli işleç **değil** bir valarray her bir öğesinde değerleri.  
  
```  
valarray<bool> operator!() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Valarray işlenen valarray öğesi değerlerini değilleme Boole değerleri.  
  
### <a name="remarks"></a>Açıklamalar  
 Mantıksal işlemi **değil** sıfırlardan olanları içine dönüştürür olanları olarak sıfır dışındaki tüm değerleri tahminini ve sıfır dönüştürür çünkü öğeleri üzerindeki geçersiz kılar. Boole değerleri, döndürülen valarray işlenen valarray aynı boyutta değil.  
  
 Ayrıca vardır bit **değil**[valarray::operator ~](#op_dtor) , üzerindeki geçersiz kılar ikili gösterimidir içinde tek tek bit düzeyinde `char` ve `int` bir valarray öğeleri.  
  
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
        << "the logical NOT operator! is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaNOT [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).  
The element-by-element result of the logical NOT operator! is the  
 valarray: ( 1 1 1 0 1 0 1 0 1 0 ).  
*\  
```  
  
##  <a name="op_mod_eq"></a>  valarray::operator%=  
 Dizi öğelerini element-wise belirtilen valarray veya öğesi türünde bir değer göre ayırma kalan alır.  
  
```  
valarray<Type>& operator%=(const valarray<Type>& right);

valarray<Type>& operator%=(const Type& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Valarray veya aynı olan element-wise, işlenen valarray bölmek için işlenen valarray bir öğe türü değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeleri olan işleneni valarray element-wise bölümünün kalan tutar valarray tarafından `right`  
  
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
        << "division is the\n valarray: ( ";  
      for ( i = 0 ; i < 6 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is: ( 53 -67 53 -67 53 -67 ).  
The initial  right valarray is: ( 1 4 7 10 13 16 ).  
The remainders from the element-by-element division is the  
 valarray: ( 0 -3 4 -7 1 -3 ).  
*\  
```  
  
##  <a name="and_eq"></a>  valarray::operator&amp;=  
 Bit düzeyinde edinir **ve** öğelerin bir dizi belirtilen valarray karşılık gelen öğeleri veya öğe türünde bir değer.  
  
```  
valarray<Type>& operator&=(const valarray<Type>& right);

valarray<Type>& operator&=(const Type& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Valarray veya bir öğe türü, birleştirilecek olan işleneni valarray özdeş, mantıksal olarak element-wise değerini **ve** işlenen valarray ile.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeleri element-wise olan valarray mantıksal **ve** tarafından işlenen valarray, `right`  
  
### <a name="remarks"></a>Açıklamalar  
 Bit tabanlı işlemi yalnızca bit cinsinden işlemek için kullanılabilir `char` ve `int` veri türleri ve çeşitleri değil **float**, **çift**, **longdouble**, `void`, `bool`, veya diğer, daha karmaşık veri türleri.  
  
 Bit düzeyinde AND mantıksal aynı gerçekte tabloda sahip **ve** ancak tek tek bit düzeyinde veri türü için geçerlidir. BITS verilen *b*1 ve *b*2, *b*1 **ve** *b*2 **true** her iki BITS true; **false** en az bir false ise.  
  
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
        << "the logical AND operator&= is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).  
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).  
The element-by-element result of the logical AND operator&= is the  
 valarray: ( 0 0 0 2 0 4 0 6 0 8 ).  
*\  
```  
  
##  <a name="op_gt_gt_eq"></a>  valarray::operator&gt;&gt;=  
 Valarray işleneninin belirtilen sayıda konumlar veya ikinci valarray tarafından belirtilen bir element-wise miktar her öğe için BITS sağa kaydırır.  
  
```  
valarray<Type>& operator>>=(const valarray<Type>& right);

valarray<Type>& operator>>=(const Type& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Sağa kaydırma veya valarray miktarını gösteren değer öğeleri sağa kaydırma element-wise miktarını belirtin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeleri olmuştur valarray sağ belirtilen tutarı gölgeye `right`.  
  
### <a name="remarks"></a>Açıklamalar  
 İşaretli sayılara korunur kendi işaretlere sahip.  
  
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
        << "the right shift is the\n valarray: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial operand valarray is: ( 64 -64 64 -64 64 -64 64 -64 ).  
The  right valarray is: ( 0 1 2 3 4 5 6 7 ).  
The element-by-element result of the right shift is the  
 valarray: ( 64 -32 16 -8 4 -2 1 -1 ).  
*\  
```  
  
##  <a name="op_lt_lt_eq"></a>  valarray::operator&lt;&lt;=  
 Valarray işleneninin belirtilen sayıda konumlar veya ikinci valarray tarafından belirtilen bir element-wise miktar her öğe için BITS Sola kaydırır.  
  
```  
valarray<Type>& operator<<=(const valarray<Type>& right);

valarray<Type>& operator<<=(const Type& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Sola kaydırma veya valarray miktarını gösteren değer öğeleri sola kaydırma element-wise miktarını belirtin.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen tutarı öğeleri gölgeye valarray sol `right`.  
  
### <a name="remarks"></a>Açıklamalar  
 İşaretli sayılara korunur kendi işaretlere sahip.  
  
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
        << "the left shift\n on the operand array is the valarray:\n ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial operand valarray is: ( 1 -1 1 -1 1 -1 1 -1 ).  
The  right valarray is: ( 0 1 2 3 4 5 6 7 ).  
The element-by-element result of the left shift  
 on the operand array is the valarray:  
 ( 1 -2 4 -8 16 -32 64 -128 ).  
*\  
```  
  
##  <a name="op_star_eq"></a>  valarray::operator*=  
 Belirtilen valarray öğelerini veya öğe türünde bir değer element-wise, bir işlenen valarray çarpar.  
  
```  
valarray<Type>& operator*=(const valarray<Type>& right);

valarray<Type>& operator*=(const Type& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Valarray veya aynı olan element-wise, işlenen valarray Çarp için işlenen valarray bir öğe türü değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeleri olan işleneni valarray element-wise çarpımını valarray ve `right`.  
  
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
        << "the multiplication is the\n valarray: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).  
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).  
The element-by-element result of the multiplication is the  
 valarray: ( 0 -1 4 -3 8 -5 12 -7 ).  
*\  
```  
  
##  <a name="op_add"></a>  valarray::operator+  
 Her bir öğesinde bir valarray artı uygulandığı birli işleç.  
  
```  
valarray<Type> operator+() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeleri işleneni dizi birimleridir valarray.  
  
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
        << "the operator+ is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaPLUS [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is:  ( 0 0 -2 2 -4 4 -6 6 -8 8 ).  
The element-by-element result of the operator+ is the  
 valarray: ( 0 0 -2 2 -4 4 -6 6 -8 8 ).  
*\  
```  
  
##  <a name="op_add_eq"></a>  valarray::operator+=  
 Belirtilen valarray öğelerini veya öğe türünde bir değer element-wise, bir işlenen valarray ekler.  
  
```  
valarray<Type>& operator+=(const valarray<Type>& right);

valarray<Type>& operator+=(const Type& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Valarray veya o, element-wise, işlenen valarray eklenecek işleneni valarray özdeş bir öğe türü değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeleri işleneni valarray element-wise toplamı olan valarray ve `right`.  
  
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
        << "the sum is the\n valarray: ( ";  
      for (i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).  
The initial  right valarray is: ( 0 1 2 3 4 5 6 7 ).  
The element-by-element result of the sum is the  
 valarray: ( 2 0 4 2 6 4 8 6 ).  
*\  
```  
  
##  <a name="valarray__operator-"></a>  valarray::operator-  
 Her bir öğesinde bir valarray eksi uygulandığı birli işleç.  
  
```  
valarray<Type> operator-() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeleri işleneni dizi birimleridir valarray.  
  
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
        << "the operator+ is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaMINUS [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is:  ( 0 0 -2 2 -4 4 -6 6 -8 8 ).  
The element-by-element result of the operator+ is the  
 valarray: ( 0 0 2 -2 4 -4 6 -6 8 -8 ).  
*\  
```  
  
##  <a name="valarray__operator-_eq"></a>  valarray::operator-=  
 Belirtilen valarray öğelerini veya öğe türünde bir değer element-wise, işlenen valarray çıkarır.  
  
```  
valarray<Type>& operator-=(const valarray<Type>& right);

valarray<Type>& operator-=(const Type& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Valarray veya o, element-wise, işleneni valarray çıkarılır için işlenen valarray özdeş bir öğe türü değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeleri olan işleneni valarray element-wise fark valarray ve `right`.  
  
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
        << "the difference is the\n valarray: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is: ( 10 0 10 0 10 0 10 0 ).  
The initial  right valarray is: ( 0 1 2 3 4 5 6 7 ).  
The element-by-element result of the difference is the  
 valarray: ( 10 -1 8 -3 6 -5 4 -7 ).  
*\  
```  
  
##  <a name="op_div_eq"></a>  valarray::operator/=  
 İşlenen valarray element-wise belirtilen valarray öğelerini veya öğe türünde bir değer tarafından böler.  
  
```  
valarray<Type>& operator/=(const valarray<Type>& right);

valarray<Type>& operator/=(const Type& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Valarray veya o, element-wise, işlenen valarray bölünür için işlenen valarray özdeş bir öğe türü değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeleri olan işleneni valarray element-wise sayının valarray bölünmüş tarafından `right`.  
  
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
        << "the quotient is the\n valarray: ( ";  
      for (i = 0 ; i < 6 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is: ( 100 -100 100 -100 100 -100 ).  
The initial Right valarray is: ( 0 2 4 6 8 10 ).  
The element-by-element result of the quotient is the  
 valarray: ( 1.#INF -50 25 -16.6667 12.5 -10 ).  
*\  
```  
  
##  <a name="op_eq"></a>  valarray::operator=  
 Öğeleri değerleri doğrudan veya başka bir valarray veya slice_array, gslice_array, mask_array veya indirect_array parçası olarak belirtilen bir valarray atar.  
  
```  
valarray<Type>& operator=(const valarray<Type>& right);

valarray<Type>& operator=(valarray<Type>&& right);

valarray<Type>& operator=(const Type& val);

valarray<Type>& operator=(const slice_array<Type>& _Slicearray);

valarray<Type>& operator=(const gslice_array<Type>& _Gslicearray);

valarray<Type>& operator=(const mask_array<Type>& _Maskarray);

valarray<Type>& operator=(const indirect_array<Type>& _Indarray);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 İşlenen valarray kopyalanacak valarray.  
  
 `val`  
 İşlenen valarray öğelerine atanacak değer.  
  
 `_Slicearray`  
 İşlenen valarray kopyalanacak slice_array.  
  
 `_Gslicearray`  
 İşlenen valarray kopyalanacak gslice_array.  
  
 `_Maskarray`  
 İşlenen valarray kopyalanacak mask_array.  
  
 `_Indarray`  
 İşlenen valarray kopyalanacak indirect_array.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk üye işleci denetlediği sırasının bir kopyasını ile denetlenen dizisi değiştirir `right`.  
  
 İkinci üye işleci ile ilk, ancak aynı olan bir [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
 Üçüncü üye işleci denetimli dizisinin her öğe bir kopyası ile değiştirir. `val`.  
  
 Bu öğeleri yalnızca oluşturulan kendi değişkenleriyle seçili denetimli dizisinin kalan üye işleçleri Değiştir [işleci&#91;&#93;](#op_at).  
  
 İlk denetlenen sıradaki üye değiştirme denetlenen sıradaki üyenin değerini bağlıdır, tanımlanmamış bir sonucudur.  
  
### <a name="remarks"></a>Açıklamalar  
 Denetimli sırası uzunluğu değişirse, genellikle tanımlanmamış bir sonucudur. Bu uygulama, ancak yalnızca herhangi bir işaretçileri veya denetlenen sıradaki öğelere başvurular geçersiz kılmak için etkisidir.  
  
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
\* Output:   
The operand valarray va is: 0 1 2 3 4 5 6 7 8 9  
The operand valarray vaR is: 10 9 8 7 6 5 4 3 2 1  
The reassigned valarray va is: 10 9 8 7 6 5 4 3 2 1  
The reassigned valarray va is: 10 10 10 10 10 10 10 10 10 10  
*\  
```  
  
##  <a name="op_at"></a>  valarray::operator[]  
 Bir öğenin veya belirtilen dizin veya belirtilen bir alt değeri bir başvuru döndürür.  
  
```  
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
 `_Off`  
 Bir değer atanması öğenin dizini.  
  
 `_Slicearray`  
 Seçilecek veya yeni bir valarray için döndürülen bir alt belirten bir valarray, slice_array.  
  
 `_Gslicearray`  
 Seçilecek veya yeni bir valarray için döndürülen bir alt belirten bir valarray, gslice_array.  
  
 *_Boolarray*  
 Seçilecek veya yeni bir valarray için döndürülen bir alt belirten bir valarray, bool_array.  
  
 `_Indarray`  
 Seçilecek veya yeni bir valarray için döndürülen bir alt belirten bir valarray, bir indirect_array.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir öğenin veya belirtilen dizin veya belirtilen bir alt değeri referansı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu denetlediği kümelerini öğelerin sıralarının seçmek için çeşitli yollar sağlamak için üye işleci aşırı *\****bu**. Beş üye işleçleri ilk grubunu iş çeşitli aşırı birlikte [işleç =](#op_eq) (ve diğer atama işleçleri) (denetimli dizisini dilimleme) seçmeli değiştirme işlemine izin vermek için. Seçilen öğeleri mevcut olması gerekir.  
  
 Kullanarak derlendiğinde [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) valarray sınırları dışındaki bir öğe erişmeye 1 veya 2 olarak tanımlanan, bir çalışma zamanı hatası oluşur.  Bkz: [işaretli yineleyiciler](../standard-library/checked-iterators.md) daha fazla bilgi için.  
  
### <a name="example"></a>Örnek  
  Örnekler için bkz: [slice::slice](../standard-library/slice-class.md#slice) ve [gslice::gslice](../standard-library/gslice-class.md#gslice) bir örnek için nasıl bildirme ve işlecini kullanın.  
  
##  <a name="op_xor_eq"></a>  valarray::operator^=  
 Element-wise özel mantıksal or işleci alır ( **XOR**) belirtilen valarray veya öğesi türünde bir değer içeren bir dizi.  
  
```  
valarray<Type>& operator|=(const valarray<Type>& right);

valarray<Type>& operator|=(const Type& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Valarray veya bir öğe türü, birleştirilecek olan işleneni valarray özdeş, mantıksal özel tarafından element-wise değerini **XOR** işlenen valarray ile.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeleri olan mantıksal element-wise, özel bir valarray **XOR** işlenen valarray, ve `right`.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel mantıksal veya denir **XOR**, aşağıdaki semantiğini vardır: öğeleri verilen *e*1 ve *e*2, *e*1  **XOR** *e*2 **true** öğelerden tam olarak birine true; ise **false** hem öğeleri false ise veya her iki öğeleri doğru olduğunda.  
  
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
        << "the bitwise XOR operator^= is the\n valarray: ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial operand valarray is:  ( 1 0 1 0 1 0 1 0 1 0 ).  
The  right valarray is: ( 0 0 1 3 3 4 6 6 7 9 ).  
The element-by-element result of the bitwise XOR operator^= is the  
 valarray: ( 1 0 0 3 2 4 7 6 6 9 ).  
*\  
```  
  
##  <a name="op_or_eq"></a>  valarray::operator&#124;=  
 Bit düzeyinde edinir `OR` öğelerin bir dizi belirtilen valarray karşılık gelen öğeleri veya öğe türünde bir değer.  
  
```  
valarray<Type>& operator|=(const valarray<Type>& right);

valarray<Type>& operator|=(const Type& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Valarray veya bir öğe türü, birleştirilecek olan işleneni valarray özdeş, bitwise tarafından element-wise değerini `OR` işlenen valarray ile.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Element-wise Bitsel olan öğeleri olan bir valarray `OR` tarafından işlenen valarray, `right`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bit tabanlı işlemi yalnızca bit cinsinden işlemek için kullanılabilir `char` ve `int` veri türleri ve çeşitleri değil **float**, **çift**, **longdouble**, `void`, `bool`, veya diğer, daha karmaşık veri türleri.  
  
 Bit düzeyinde `OR` mantıksal aynı gerçekte tabloda sahip `OR` ancak tek tek bit düzeyinde veri türü için geçerlidir. BITS verilen *b*1 ve *b*2, *b*1 `OR` *b*2 **true** BITS en az biri olduğunda TRUE; **false** bitlerin her ikisi de yanlışsa.  
  
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
  
   cout << "The initial operand valarray is:\n ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The  right valarray is:\n ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaL |= vaR;  
   cout << "The element-by-element result of "  
        << "the logical OR\n operator|= is the valarray:\n ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial operand valarray is:  
 ( 1 0 1 0 1 0 1 0 1 0 ).  
The  right valarray is:  
 ( 0 0 1 3 3 4 6 6 7 9 ).  
The element-by-element result of the logical OR  
 operator|= is the valarray:  
 ( 1 0 1 3 3 4 7 6 7 9 ).  
*\  
```  
  
##  <a name="op_dtor"></a>  valarray::operator ~  
 Bit düzeyinde edinir birli işleç **değil** bir valarray her bir öğesinde değerleri.  
  
```  
valarray<Type> operator~() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bit düzeyinde Boole değerleri valarray **değil** işlenen valarray öğesi değerlerinin.  
  
### <a name="remarks"></a>Açıklamalar  
 Bit tabanlı işlemi yalnızca bit cinsinden işlemek için kullanılabilir `char` ve `int` veri türleri ve çeşitleri değil **float**, **çift**, **longdouble**, `void`, `bool` veya diğer, daha karmaşık veri türleri.  
  
 Bit düzeyinde **değil** mantıksal aynı gerçekte tabloda sahip **değil** ancak tek tek bit düzeyinde veri türü için geçerlidir. Bit verilen *b*, ~ *b* true ise *b* false ve false ise *b* doğrudur. Mantıksal **değil**[işleci!](#op_not) sıfır dışındaki tüm değerleri olarak sayım bir öğe düzeyi geçerli **doğru**, ve sonucu bir valarray Boolean değeri. Bit düzeyinde **NOToperator ~**, bunun aksine, değer 0 veya 1, bit düzeyinde işleminin sonucunu bağlı olarak başka bir valarray neden olabilir.  
  
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
        << "the bitwise NOT operator~ is the\n valarray: ( ";  
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
        << "the bitwise NOT operator~ is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaNOT2 [ i ] << " ";  
   cout << ")." << endl;  
  
   // The negative numbers are represented using  
   // the two's complement approach, so adding one  
   // to the flipped bits returns the negative elements  
   vaNOT2 = vaNOT2 + 1;  
   cout << "The element-by-element result of "  
        << "adding one\n is the negative of the "  
        << "original elements the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaNOT2 [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray <unsigned short int> is:  ( 0 5 2 15 4 25 6 35 8 45 ).  
The element-by-element result of the bitwise NOT operator~ is the  
 valarray: ( 65535 65530 65533 65520 65531 65510 65529 65500 65527 65490 ).  
  
The initial valarray <int> is:  ( 0 -2 2 -6 4 -10 6 -14 8 -18 ).  
The element-by-element result of the bitwise NOT operator~ is the  
 valarray: ( -1 1 -3 5 -5 9 -7 13 -9 17 ).  
The element-by-element result of adding one  
 is the negative of the original elements the  
 valarray: ( 0 2 -2 6 -4 10 -6 14 -8 18 ).  
*\  
```  
  
##  <a name="resize"></a>  valarray::resize  
 Bir valarray öğe sayısı için belirli sayıda değiştirir.  
  
```  
void resize(
    size_t _Newsize);

void resize(
    size_t _Newsize,   
    const Type val);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Newsize`  
 Yeniden boyutlandırılan valarray öğe sayısı.  
  
 `val`  
 Yeniden boyutlandırılan valarray öğelerine verilecek değer.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk üye işlevi kendi varsayılan oluşturucu öğeleriyle başlatır.  
  
 Herhangi bir işaretçileri veya denetlenen sıradaki öğelere başvurular geçersiz kılınır.  
  
### <a name="example"></a>Örnek  
  Aşağıdaki örnek valarray::resize üye fonksiyonu kullanımını göstermektedir.  
  
```  
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
\* Output:   
The valarray contains ( 0 1 2 3 4 5 6 7 8 9 ).  
The number of elements in the valarray is: 10.  
  
The valarray contains ( 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 ).  
The number of elements in the resized valarray is: 15.  
*\  
```  
  
##  <a name="shift"></a>  valarray::Shift  
 Bir valarray tüm öğeler tarafından belirtilen bir basamak sayısını kaydırır.  
  
```  
valarray<Type> shift(int count) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `count`  
 Öğeleri İleri gölgeye üzeresiniz basamak sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hangi tüm öğeleri taşındı yeni bir valarray `count` konumlar işleneni valarray içinde konumlarına göre sol valarray önüne bulunun.  
  
### <a name="remarks"></a>Açıklamalar  
 Pozitif bir değer `count` öğeleri Sola kaydırır `count` , sıfır dolguyla yerleştirir.  
  
 Negatif değerini `count` öğeleri sağa kaydırır `count` , sıfır dolguyla yerleştirir.  
  
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
\* Output:   
The operand valarray va1(10) is: ( 0 1 2 3 4 5 6 7 8 9 ).  
The shifted valarray va1 is: va1.shift (4) = ( 4 5 6 7 8 9 0 0 0 0 ).  
The operand valarray va2(10) is: ( 10 9 8 7 6 5 4 3 2 1 ).  
The shifted valarray va2 is: va2.shift (-4) = ( 0 0 0 0 10 9 8 7 6 5 ).  
*\  
```  
  
##  <a name="size"></a>  valarray::size  
 Valarray öğe sayısını bulur.  
  
```  
size_t size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlenen valarray öğe sayısı.  
  
### <a name="example"></a>Örnek  
  Aşağıdaki örnek valarray::size üye fonksiyonu kullanımını göstermektedir.  
  
```  
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
    cout << "After initializing two more elements,\n "  
         << "the operand valarray va2(12) is now: ( ";  
        for (i = 0; i < 12; i++)  
            cout << va2[i] << " ";  
    cout << ")." << endl;  
    cout << "The number of elements in the valarray va2 is still: "  
         << size2  << "." << endl;  
}  
\* Output:   
The operand valarray va1(10) is: ( 0 1 2 3 4 5 6 7 8 9 ).  
The number of elements in the valarray va1 is: va1.size = 10.  
  
The operand valarray va2(12) is: ( 0 1 2 3 4 5 6 7 8 9 ).  
The number of elements in the valarray va2 is: va2.size = 12.  
  
After initializing two more elements,  
 the operand valarray va2(12) is now: ( 0 1 2 3 4 5 6 7 8 9 10 11 ).  
The number of elements in the valarray va2 is still: 12.  
*\  
```  
  
##  <a name="sum"></a>  valarray::Sum  
 Valarray sıfır dışında uzunlukta tüm öğelerin toplamı belirler.  
  
```  
Type sum() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlenen valarray öğelerini toplamı.  
  
### <a name="remarks"></a>Açıklamalar  
 Uzunluk birden büyük ise, üye fonksiyonu değerleri toplama uygulayarak ekler `operator+=` sınıfının öğeleri çiftleri arasındaki **türü**, hangi işleci sonuç olarak, sağlanması için türündeki öğeler  **Türü**.  
  
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
\* Output:   
The operand valarray va (10) is: ( 0 1 2 3 4 5 6 7 8 9 ).  
The sum of elements in the valarray is: 45.  
*\  
```  
  
##  <a name="swap"></a>  valarray::Swap  
 İki öğelerini alış verişleri `valarray`s.  
  
```  
void swap(valarray& right);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`right`|A `valarray` öğeleri takas için sağlama.|  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini denetimli sıraları arasında değiştirir `*this` ve `right`. Bunu Sabit sürede yapar, hiçbir özel durum oluşturur ve hiçbir başvuruları, işaretçileri veya iki denetimli sıraları öğelerinde tanımladığınız yineleyiciler geçersiz kılar.  
  
##  <a name="valarray"></a>  valarray::valarray  
 Belirli bir boyuta veya belirli bir değerin veya başka bir valarray bir kopyasını veya başka bir valarray alt öğeleri olan bir valarray oluşturur.  
  
```  
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
 `Count`  
 Valarray olmasını öğe sayısı.  
  
 `Val`  
 Valarray öğeleri başlatılırken kullanılacak değer.  
  
 `Ptr`  
 Valarray öğeleri başlatmak için kullanılan değerleri işaretçi.  
  
 `Right`  
 Varolan bir valarray yeni valarray başlatılamadı.  
  
 `SliceArray`  
 Yapılandırılan valarray öğelerini başlatılırken kullanılacak öğesi değerleri olan slice_array.  
  
 `GsliceArray`  
 Yapılandırılan valarray öğelerini başlatılırken kullanılacak öğesi değerleri olan gslice_array.  
  
 `MaskArray`  
 Yapılandırılan valarray öğelerini başlatılırken kullanılacak öğesi değerleri olan mask_array.  
  
 `IndArray`  
 Yapılandırılan valarray öğelerini başlatılırken kullanılacak öğesi değerleri olan indirect_array.  
  
 `IList`  
 Kopyalanacak öğe içeren initializer_list.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk (varsayılan) Oluşturucu, boş bir dizi nesneyi başlatır. Sonraki üç oluşturucular her bir dizi nesneyi başlatmak `Count` aşağıdaki gibi öğeleri:  
  
-   İçin açık `valarray(size_t Count)`, her öğesinin varsayılan kurucu ile başlatıldı.  
  
-   İçin `valarray(const Type& Val, Count)`, her öğe ile başlatılmış `Val`.  
  
-   İçin `valarray(const Type* Ptr, Count)`, konumunda öğe `I` ile başlatılmış `Ptr`[ `I`].  
  
 Bir valarray nesnesine her kalan Oluşturucu başlatır\<türü > değişkeninde belirtilen alt tarafından belirlenen nesne.  
  
 Son Oluşturucusu sonraki son olarak, ancak ile aynıdır bir [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
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
  
    cout << "The new valarray initialized from the slice is vaSlice ="  
        << "\nva[slice( 2, 4, 3)] = (";  
    for (int i = 0; i < 3; i++) {  
        cout << " " << vaSlice[i];  
    }  
    cout << " )" << endl;  
  
    valarray<int> va2{{ 1, 2, 3, 4 }};  
    for (auto& v : va2){  
        cout << v << " ";  
    }  
    cout << endl;  
}  
  
```  
  
```Output  
The operand valarray va is:( 0 2 2 2 2 2 2 2 2 2 )The new valarray initialized from the slice is vaSlice =va[slice( 2, 4, 3)] = ( 0 0 0 )1 2 3 4  
```  
  
##  <a name="value_type"></a>  valarray::value_type  
 Valarray içinde depolanan öğenin türünü temsil eden tür.  
  
```  
typedef Type value_type;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür **türü**.  
  
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
\* Output:   
The initial operand valarray is:  ( 0 -1 2 -1 4 -1 6 -1 8 -1 ).  
The decalared value_type Right is: 10  
The resulting valarray is:  ( 0 -10 20 -10 40 -10 60 -10 80 -10 ).  
*\  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)

