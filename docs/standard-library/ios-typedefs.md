---
title: "&lt;iOS&gt; tür tanımları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- iosfwd/std::ios
- iosfwd/std::streamoff
- iosfwd/std::streampos
- iosfwd/std::streamsize
- iosfwd/std::wios
- iosfwd/std::wstreampos
ms.assetid: 0b962632-3439-44de-bf26-20c67a7f0ff3
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: 6c94f157a28c606db6e7523b9af18e972f870c46
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ltiosgt-typedefs"></a>&lt;iOS&gt; tür tanımları
||||  
|-|-|-|  
|[iOS](#ios)|[streamoff](#streamoff)|[streampos](#streampos)|  
|[streamsize](#streamsize)|[wios](#wios)|[wstreampos](#wstreampos)|  
  
##  <a name="ios">iOS</a>  
 Eski iostream kitaplığı ios sınıfından destekler.  
  
```  
typedef basic_ios<char, char_traits<char>> ios;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı için eş anlamlı türüdür [basic_ios](../standard-library/basic-ios-class.md), türündeki öğeler için özelleştirilmiş `char` varsayılan karakter nitelikler ile.  
  
##  <a name="streamoff"></a>  streamoff  
 İç işlemleri destekler.  
  
```  
#ifdef _WIN64  
    typedef __int64 streamoff;  
#else  
    typedef long streamoff;  
#endif  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Türü işlemleri konumlandırma çeşitli akışında katılan bir bayt uzaklığı depolayan bir nesneyi tanımlayan imzalı bir tamsayıdır. Kendi gösterimi en az 32 değeri BITS içeriyor. Bir akış içinde rastgele bayt konumunu göstermek için mutlaka yeterince büyük değil. Değer **streamoff(-1)** genellikle hatalı uzaklığı gösterir.  
  
##  <a name="streampos"></a>  streampos  
 Arabellek işaretçi veya dosya işaretçisini geçerli konumunu tutar.  
  
```  
typedef fpos<mbstate_t> streampos;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eşanlamlısı türüdür [fpos](../standard-library/fpos-class.md)< `mbstate_t`>.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// ios_streampos.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main( )   
{  
   using namespace std;  
  
   ofstream x( "iostream.txt" );  
   x << "testing";  
   streampos y = x.tellp( );  
   cout << y << endl;  
}  
```  
  
```Output  
7  
```  
  
##  <a name="streamsize"></a>  streamsize  
 Akış boyutunu gösterir.  
  
```  
#ifdef _WIN64  
    typedef __int64 streamsize;  
#else  
    typedef int streamsize;  
#endif  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çeşitli akış işlemleri söz konusu öğelerin sayısını depolayan bir nesneyi tanımlayan bir işaretli tamsayıyı türüdür. Kendi gösterimi en az 16 bit vardır. Bir akış içinde rastgele bayt konumunu göstermek için mutlaka yeterince büyük değil.  
  
### <a name="example"></a>Örnek  
  Derleme ve aşağıdaki programı çalıştırma Ara sonra ayarı etkisini görmek için dosya sınama.txt `streamsize`.  
  
```  
// ios_streamsize.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main( )   
{  
   using namespace std;  
   char a[16] = "any such text";  
   ofstream x( "test.txt" );  
   streamsize y = 6;  
   x.write( a, y );  
}  
```  
  
##  <a name="wios">wios</a>  
 Eski iostream kitaplığı wios sınıfından destekler.  
  
```  
typedef basic_ios<wchar_t, char_traits<wchar_t>> wios;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı için eş anlamlı türüdür [basic_ios](../standard-library/basic-ios-class.md), türündeki öğeler için özelleştirilmiş `wchar_t` varsayılan karakter nitelikler ile.  
  
##  <a name="wstreampos"></a>  wstreampos  
 Arabellek işaretçi veya dosya işaretçisini geçerli konumunu tutar.  
  
```  
typedef fpos<mbstate_t> wstreampos;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eşanlamlısı türüdür [fpos](../standard-library/fpos-class.md)< `mbstate_t`>.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// ios_wstreampos.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main( )   
{  
   using namespace std;  
   wofstream xw( "wiostream.txt" );  
   xw << L"testing";  
   wstreampos y = xw.tellp( );  
   cout << y << endl;  
}  
```  
  
```Output  
7  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<ios>](../standard-library/ios.md)

