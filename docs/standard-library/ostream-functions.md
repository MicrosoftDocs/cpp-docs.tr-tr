---
title: "&lt;ostream&gt; işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ostream/std::swap
- ostream/std::endl
- ostream/std::ends
- ostream/std::flush
ms.assetid: d6e56cc0-c8df-4dbe-be10-98e14c35ed3a
caps.latest.revision: "15"
manager: ghogen
helpviewer_keywords:
- std::swap [C++]
- std::endl [C++]
- std::ends [C++]
- std::flush [C++]
ms.openlocfilehash: 252a178f1ce71c30bdd830811cbce59b22acc791
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltostreamgt-functions"></a>&lt;ostream&gt; işlevleri
||||  
|-|-|-|  
|[değiştirme](#swap)|[endl](#endl)|[sona erer](#ends)|  
|[Temizleme](#flush)|  
  
##  <a name="endl"></a>endl  
 Bir satır sonlandırır ve arabelleği temizler.  
  
```  
template class<Elem, Tr> basic_ostream<Elem, Tr>& endl(basic_ostream<Elem, Tr>& Ostr);
```  
  
### <a name="parameters"></a>Parametreler  
 `Elem`  
 Öğe türü.  
  
 `Ostr`  
 Türünde bir nesne `basic_ostream`.  
  
 `Tr`  
 Karakter nitelikler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Türünde bir nesne `basic_ostream`.  
  
### <a name="remarks"></a>Açıklamalar  
 Manipulator çağrıları `Ostr` **.** [put](../standard-library/basic-ostream-class.md#put)( `Ostr` **.** [widen](../standard-library/basic-ios-class.md#widen)( **'\n'**)) ve ardından çağırır `Ostr` **.** [flush](../standard-library/basic-ostream-class.md#flush). Döndürdüğü `Ostr`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// ostream_endl.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   cout << "testing" << endl;  
}  
```  
  
```Output  
testing  
```  
  
##  <a name="ends"></a>sona erer  
 Bir dize sonlandırır.  
  
```  
template class<Elem, Tr> basic_ostream<Elem, Tr>& ends(basic_ostream<Elem, Tr>& Ostr);
```  
  
### <a name="parameters"></a>Parametreler  
 `Elem`  
 Öğe türü.  
  
 `Ostr`  
 Türünde bir nesne `basic_ostream`.  
  
 `Tr`  
 Karakter nitelikler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Türünde bir nesne `basic_ostream`.  
  
### <a name="remarks"></a>Açıklamalar  
 Manipulator çağrıları `Ostr` **.** [put](../standard-library/basic-ostream-class.md#put)( `Elem`( **'\0'**)). Değerini döndürür`Ostr.`  
  
### <a name="example"></a>Örnek  
  
```cpp  
// ostream_ends.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   cout << "a";  
   cout << "b" << ends;  
   cout << "c" << endl;  
}  
```  
  
```Output  
ab c  
```  
  
##  <a name="flush"></a>Temizleme  
 Arabelleği temizler.  
  
```  
template class<Elem, Tr> basic_ostream<Elem, Tr>& flush(basic_ostream<Elem, Tr>& Ostr);
```  
  
### <a name="parameters"></a>Parametreler  
 `Elem`  
 Öğe türü.  
  
 `Ostr`  
 Türünde bir nesne `basic_ostream`.  
  
 `Tr`  
 Karakter nitelikler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Türünde bir nesne `basic_ostream`.  
  
### <a name="remarks"></a>Açıklamalar  
 Manipulator çağrıları `Ostr` **.** [flush](../standard-library/basic-ostream-class.md#flush). Döndürdüğü `Ostr`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// ostream_flush.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   cout << "testing" << flush;  
}  
```  
  
```Output  
testing  
```  
  
##  <a name="swap"></a>değiştirme  
 İki değerlerini alış verişleri `basic_ostream` nesneleri.  
  
```  
template <class Elem, class Tr>  
void swap(
    basic_ostream<Elem, Tr>& left,  
    basic_ostream<Elem, Tr>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 Lvalue başvuru için bir `basic_ostream` nesnesi.  
  
 `right`  
 Lvalue başvuru için bir `basic_ostream` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon işlevi `swap` yürütür `left.swap(right)`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<ostream >](../standard-library/ostream.md)

