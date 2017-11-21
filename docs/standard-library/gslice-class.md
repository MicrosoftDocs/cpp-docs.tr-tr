---
title: "gslice sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- valarray/std::gslice
- valarray/std::gslice::size
- valarray/std::gslice::start
- valarray/std::gslice::stride
dev_langs: C++
helpviewer_keywords:
- std::gslice [C++]
- std::gslice [C++], size
- std::gslice [C++], start
- std::gslice [C++], stride
ms.assetid: f47cffd0-ea59-4b13-848b-7a5ce1d7e2a3
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6928fd3aa902b5ed0ab4e942950af76448e16e5e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="gslice-class"></a>gslice Sınıfı
Çok boyutlu bir valarray kümelerine tanımlamak için kullanılan valarray için yardımcı sınıfı. Bir dizinin tüm öğeleri çok boyutlu bir matris bir valarray kabul, dilim boyutlu bir diziye dışında bir vektör ayıklar.  
  
## <a name="remarks"></a>Açıklamalar  
 Türünde bir nesne niteleyen parametreleri sınıfı depolar [gslice_array](../standard-library/gslice-array-class.md). Sınıfın bir nesnesi için bağımsız değişken olarak bir nesne sınıfı gslice görüntülendiğinde, bir valarray alt dolaylı olarak oluşturulan [valarray](../standard-library/valarray-class.md#op_at)**\<türü >**. Üst valarray Seçili alt belirtin depolanan değerleri şunlardır:  
  
-   Bir başlangıç dizini.  
  
-   Sınıfının bir uzunluk vektör **valarray < size_t >**.  
  
-   STRIDE vektör sınıfının **valarray < size_t >**.  
  
 İki vektörü aynı uzunlukta olmalıdır.  
  
 Gslice tarafından tanımlanan kümesi sabit valarray kısmı ise, gslice yeni valarray olur. Gslice tarafından tanımlanan alt kümesini nonconstant valarray ayarlanırsa, gslice özgün valarray başvuru semantik vardır. Nonconstant valarrays için değerlendirme mekanizması süresi ve bellek kaydeder.  
  
 Valarrays işlemleri yalnızca gslices tarafından tanımlanan kaynak ve hedef alt kümelerini farklıdır ve tüm dizinleri geçerli sağlanır.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[gslice](#gslice)|Bir alt kümesini tanımlar bir `valarray` birden çok dilimleri oluşur `valarray` tüm belirtilen öğede başlatın.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[boyutu](#size)|İçinde bir genel dilimin öğeleri numaralarını belirtme dizi değerleri bulur bir `valarray`.|  
|[Başlat](#start)|Bir genel dilimin başlangıç dizinini bulur bir `valarray`.|  
|[STRIDE](#stride)|Bir genel dilimin öğeler arasındaki mesafeyi bulur bir `valarray`.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<valarray >  
  
 **Namespace:** std  
  
##  <a name="gslice"></a>gslice::gslice  
 Çok boyutlu bir valarray dilimleri tanımlamak için kullanılan valarray için yardımcı sınıfı.  
  
```  
gslice();

gslice(
    size_t _StartIndex,  
    const valarray<size_t>& _LenArray,  
    const valarray<size_t>& _IncArray);
```  
  
### <a name="parameters"></a>Parametreler  
 `_StartIndex`  
 Alt ilk öğe valarray dizini.  
  
 `_LenArray`  
 Her dilimi öğe sayısını belirten bir dizi.  
  
 `_IncArray`  
 STRIDE her dilimi belirten bir dizi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsayılan Oluşturucu başlangıç dizini için sıfır ve uzunluğu ve STRIDE vektörlerinin sıfır uzunluklu vektörleri depolar. İkinci oluşturucu depoları `_StartIndex` başlangıç dizini için `_LenArray` uzunluk dizisi için ve `_IncArray` STRIDE dizi.  
  
### <a name="remarks"></a>Açıklamalar  
 **gslice** aynı her başlangıcında öğesi belirtilen valarray, birden çok dilimleri oluşan bir valarray kümesini tanımlar. Birden çok dilim tanımlamak için diziler kullanın arasındaki tek fark yeteneğidir `gslice` ve [slice::slice](../standard-library/slice-class.md#slice). İlk dilim dizini ile ilk bir öğeye sahip `_StartIndex`, ilk öğesi tarafından belirtilen öğe sayısı `_LenArray`ve ilk öğesi tarafından verilen bir STRIDE `_IncArray`. Resme dilimler sonraki kümesini ilk dilim tarafından verilen ilk öğesine sahip. İkinci öğesini `_LenArray` öğe sayısını belirtir. STRIDE ikinci öğesi tarafından verilen `_IncArray`. Üçüncü boyut dilim ve iki boyutlu dizi öğeleri başlangıç öğesi olarak ele analogously devam edin  
  
### <a name="example"></a>Örnek  
  
```cpp  
// gslice_ctor.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> va ( 20 ), vaResult;  
   for ( i = 0 ; i < 20 ; i+=1 )   
      va [ i ] =  i;  
  
   cout << "The operand valarray va is:" << endl << "(";  
   for ( i = 0 ; i < 20 ; i++ )  
      cout << " " << va [ i ];  
   cout << " )" << endl;  
  
   valarray<size_t> Len ( 2 ), Stride ( 2 );  
   Len [0] = 4;  
   Len [1] = 4;  
   Stride [0] = 7;  
   Stride [1] = 4;  
  
   gslice vaGSlice ( 0, Len, Stride );  
   vaResult = va [ vaGSlice ];  
  
   cout << "The valarray for vaGSlice is vaResult:" << endl  
        << "va[vaGSlice] = (";  
  
   for ( i = 0 ; i < 8 ; i++ )  
      cout << " " << vaResult [ i ];  
   cout << ")" << endl;  
}  
```  
  
```Output  
The operand valarray va is:  
( 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 )  
The valarray for vaGSlice is vaResult:  
va[vaGSlice] = ( 0 4 8 12 7 11 15 19)  
```  
  
##  <a name="size"></a>gslice::size  
 Bir valarray genel bir dilimi öğeleri numaralarını belirtme dizi değerlerini bulur.  
  
```  
valarray<size_t> size() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her bir valarray, genel bir dilim dilimi öğe sayısını belirten bir valarray.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini dilimler saklı uzunluklarının döndürür.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// gslice_size.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
   size_t sizeVA;  
  
   valarray<int> va ( 20 ), vaResult;  
   for ( i = 0 ; i < 20 ; i+=1 )  
      va [ i ] =  i;  
  
   cout << "The operand valarray va is:\n ( ";  
      for ( i = 0 ; i < 20 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
  
   sizeVA = va.size ( );  
   cout << "The size of the valarray is: "  
        << sizeVA << "." << endl << endl;  
  
   valarray<size_t> Len ( 2 ), Stride ( 2 );  
   Len [0] = 4;  
   Len [1] = 4;  
   Stride [0] = 7;  
   Stride [1] = 4;  
  
   gslice vaGSlice ( 0, Len, Stride );  
   vaResult = va [ vaGSlice ];  
   const valarray <size_t> sizeGS = vaGSlice.size ( );  
  
   cout << "The valarray for vaGSlice is vaResult:"  
        << "\n va[vaGSlice] = ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaResult [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The size of vaResult is:"  
        << "\n vaGSlice.size ( ) = ( ";  
      for ( i = 0 ; i < 2 ; i++ )  
         cout << sizeGS[ i ] << " ";  
   cout << ")." << endl;  
}  
```  
  
```Output  
The operand valarray va is:  
 ( 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 ).  
The size of the valarray is: 20.  
  
The valarray for vaGSlice is vaResult:  
 va[vaGSlice] = ( 0 4 8 12 7 11 15 19 ).  
The size of vaResult is:  
 vaGSlice.size ( ) = ( 4 4 ).  
```  
  
##  <a name="start"></a>gslice::Start  
 Bir valarray genel bir dilimin başlangıç dizinini bulur.  
  
```  
size_t start() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir valarray genel bir dilimin başlangıç dizini.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// gslice_start.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> va ( 20 ), vaResult;  
   for (i = 0 ; i < 20 ; i+=1 )  
      va [ i ] =  i;  
  
   cout << "The operand valarray va is:\n ( ";  
      for ( i = 0 ; i < 20 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
  
   valarray<size_t> Len ( 2 ), Stride ( 2 );  
   Len [0] = 4;  
   Len [1] = 4;  
   Stride [0] = 7;  
   Stride [1] = 4;  
  
   gslice vaGSlice ( 0, Len, Stride );  
   vaResult = va [ vaGSlice ];  
   size_t vaGSstart = vaGSlice.start ( );  
  
   cout << "The valarray for vaGSlice is vaResult:"  
        << "\n va[vaGSlice] = ( ";  
      for (i = 0 ; i < 8 ; i++ )  
         cout << vaResult [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The index of the first element of vaResult is: "  
        << vaGSstart << "." << endl;  
}  
```  
  
```Output  
The operand valarray va is:  
 ( 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 ).  
The valarray for vaGSlice is vaResult:  
 va[vaGSlice] = ( 0 4 8 12 7 11 15 19 ).  
The index of the first element of vaResult is: 0.  
```  
  
##  <a name="stride"></a>gslice::stride  
 Bir valarray, genel bir dilim öğeler arasındaki mesafeyi bulur.  
  
```  
valarray<size_t> stride() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Her bir valarray, genel bir dilim dilimin öğeler arasındaki uzaklıkları belirtme valarray.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// gslice_stride.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> va ( 20 ), vaResult;  
   for (i = 0 ; i < 20 ; i+=1 )  
      va [ i ] =  i;  
  
   cout << "The operand valarray va is:\n ( ";  
      for (i = 0 ; i < 20 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
  
   valarray<size_t> Len ( 2 ), Stride ( 2 );  
   Len [0] = 4;  
   Len [1] = 4;  
   Stride [0] = 7;  
   Stride [1] = 4;  
  
   gslice vaGSlice ( 0, Len, Stride );  
   vaResult = va [ vaGSlice ];  
   const valarray <size_t> strideGS = vaGSlice.stride ( );  
  
   cout << "The valarray for vaGSlice is vaResult:"  
        << "\n va[vaGSlice] = ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaResult [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The strides of vaResult are:"  
        << "\n vaGSlice.stride ( ) = ( ";  
      for ( i = 0 ; i < 2 ; i++ )  
         cout << strideGS[ i ] << " ";  
   cout << ")." << endl;  
  
}  
```  
  
```Output  
The operand valarray va is:  
 ( 0 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 ).  
The valarray for vaGSlice is vaResult:  
 va[vaGSlice] = ( 0 4 8 12 7 11 15 19 ).  
The strides of vaResult are:  
 vaGSlice.stride ( ) = ( 7 4 ).  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)

