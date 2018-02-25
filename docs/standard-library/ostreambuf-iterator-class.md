---
title: "ostreambuf_iterator sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- streambuf/std::ostreambuf_iterator
- iterator/std::ostreambuf_iterator::char_type
- iterator/std::ostreambuf_iterator::ostream_type
- iterator/std::ostreambuf_iterator::streambuf_type
- iterator/std::ostreambuf_iterator::traits_type
- iterator/std::ostreambuf_iterator::failed
dev_langs:
- C++
helpviewer_keywords:
- std::ostreambuf_iterator [C++]
- std::ostreambuf_iterator [C++], char_type
- std::ostreambuf_iterator [C++], ostream_type
- std::ostreambuf_iterator [C++], streambuf_type
- std::ostreambuf_iterator [C++], traits_type
- std::ostreambuf_iterator [C++], failed
ms.assetid: dad1e624-2f45-4e94-8887-a885e95f9071
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 695b8415cd5958d200ba9120e28bebd543614f24
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ostreambufiterator-class"></a>ostreambuf_iterator Sınıfı
Şablon sınıfı ostreambuf_iterator ardışık karakteri öğeleri ile ayıklama çıktı akışı üzerine yazar bir çıktı yineleyici nesneyi tanımlayan **işleci >>**. `ostreambuf_iterator`s olanlardan farklı [ostream_iterator sınıfı](../standard-library/ostream-iterator-class.md) çıkış akışı eklenen nesne türü, genel bir tür yerine karaktere sahip içinde.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class CharType = char class Traits = char_traits <CharType>>
```  
  
#### <a name="parameters"></a>Parametreler  
 `CharType`  
 ostreambuf_iterator için karakter türünü temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `char`.  
  
 `Traits`  
 ostreambuf_iterator için karakter türünü temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `char_traits` \< *CharType >.*  
  
## <a name="remarks"></a>Açıklamalar  
 Ostreambuf_iterator sınıfının, bir çıkış yineleyici için gereksinimleri karşılaması gerekir. Çıkış akışları kullanarak doğrudan algoritmaları yazılabilir bir `ostreambuf_iterator`. Sınıf, karakterlerin biçimindeki ham (biçimlendirilmemiş) G/Ç akışına erişim sağlayarak düşük düzey bir akış ve üst düzey akış yineleyicilerle ilişkili arabelleğe alma işlemini ve karakter çevirilerini atlama özelliği sağlar.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator)|Oluşturan bir `ostreambuf_iterator` karakter çıkış akışına yazmak için başlatıldı.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[char_type](#char_type)|Karakter türü için sağlayan bir türü `ostreambuf_iterator`.|  
|[ostream_type](#ostreambuf_iterator_ostream_type)|Akış türü için sağlayan bir türü `ostream_iterator`.|  
|[streambuf_type](#streambuf_type)|Akış türü için sağlayan bir türü `ostreambuf_iterator`.|  
|[traits_type](#traits_type)|Karakter nitelikler tür sağlayan bir tür `ostream_iterator`.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[Başarısız oldu](#failed)|Çıkış akışı arabelleğine ekleme hatasını sınar.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[operator*](#op_star)|Çıktı yineleyici ifade uygulamak için kullanılan bilgileri başvuru kaldırma işleci * `i`  =  `x`.|  
|[operator++](#op_add_add)|Döndüren bir işlevsel artış işleci bir `ostreambuf_iterator` işlemi çağrılmadan önce de aynı nesneye onu ele.|  
|[operator=](#op_eq)|İşleç, ilişkili akış ara belleğine bir karakter ekler.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<yineleyici >  
  
 **Namespace:** std  
  
##  <a name="char_type"></a>  ostreambuf_iterator::char_type  
 Karakter türü için sağlayan bir türü `ostreambuf_iterator`.  
  
```
typedef CharType char_type;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür **CharType**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// ostreambuf_iterator_char_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef ostreambuf_iterator<char>::char_type CHT1;  
   typedef ostreambuf_iterator<char>::traits_type CHTR1;  
  
   // ostreambuf_iterator for stream cout  
   // with new line delimiter:  
    ostreambuf_iterator< CHT1, CHTR1> charOutBuf ( cout );  
  
   // Standard iterator interface for writing  
   // elements to the output streambuf:  
   cout << "The characters written to the output stream\n"  
        << " by charOutBuf are: ";  
 *charOutBuf = 'O';  
   charOutBuf++;  
 *charOutBuf = 'U';  
   charOutBuf++;  
 *charOutBuf = 'T';  
   charOutBuf++;  
   cout << "." << endl;  
}  
\* Output:   
The characters written to the output stream  
 by charOutBuf are: OUT.  
*\  
```  
  
##  <a name="failed"></a>  ostreambuf_iterator::failed  
 Çıkış akışı arabelleğine ekleme hatasını sınar.  
  
```
bool failed() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** hiçbir çıkış akışı arabelleği ekleme başarısız oldu, daha önce; Aksi halde **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür **true** herhangi bir üyenin önceki kullanımda IF `operator=`, çağrısı **alt**_ -> `sputc` döndürülen **eof**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// ostreambuf_iterator_failed.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostreambuf_iterator for stream cout  
   ostreambuf_iterator<char> charOut ( cout );  
  
 *charOut = 'a';  
   charOut ++;  
 *charOut  = 'b';  
   charOut ++;     
 *charOut = 'c';  
   cout << " are characters output individually." << endl;  
  
   bool b1 = charOut.failed ( );  
   if (b1)   
       cout << "At least one insertion failed." << endl;  
   else  
       cout << "No insertions failed." << endl;  
}  
\* Output:   
abc are characters output individually.  
No insertions failed.  
*\  
```  
  
##  <a name="op_star"></a>  ostreambuf_iterator::operator*  
 Çıktı yineleyici ifade uygulamak için kullanılan bir işlevsel bilgileri başvuru kaldırma işleci \* *ı* = *x*.  
  
```
ostreambuf_iterator<CharType, Traits>& operator*();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ostreambuf yineleyici nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işleç işlevleri yalnızca çıktı yineleyici ifadesinde \* *ı* = *x* akışı arabelleğe çıkış karakter. Ostreambuf yineleyici uygulanan, yineleyici döndürür;  **\*iter** döndürür **iter**,  
  
### <a name="example"></a>Örnek  
  
```cpp  
// ostreambuf_iterator_op_deref.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostreambuf_iterator for stream cout  
   // with new line delimiter  
   ostreambuf_iterator<char> charOutBuf ( cout );  
  
   // Standard iterator interface for writing  
   // elements to the output stream  
   cout << "Elements written to output stream:" << endl;  
 *charOutBuf = 'O';  
   charOutBuf++;   // no effect on iterator position  
 *charOutBuf = 'U';  
 *charOutBuf = 'T';  
}  
\* Output:   
Elements written to output stream:  
OUT  
*\  
```  
  
##  <a name="op_add_add"></a>  ostreambuf_iterator::operator++  
 Ostream yineleyici işlemi önce ele aynı karakter döndürür işlevsel artış işleci çağrıldı.  
  
```
ostreambuf_iterator<CharType, Traits>& operator++();
ostreambuf_iterator<CharType, Traits>& operator++(int);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk olarak ele karakter veya parametresinin uygulama tanımlı bir nesneye başvuru `ostreambuf_iterator` \< **CharType**, **nitelikler**>.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç çıkış yineleyici ifade uygulamak için kullanılan \* *ı* = *x*.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// ostreambuf_iterator_op_incr.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostreambuf_iterator for stream cout  
   // with new line delimiter  
   ostreambuf_iterator<char> charOutBuf ( cout );  
  
   // Standard iterator interface for writing  
   // elements to the output stream  
   cout << "Elements written to output stream:" << endl;  
 *charOutBuf = 'O';  
   charOutBuf++;      // No effect on iterator position  
 *charOutBuf = 'U';  
 *charOutBuf = 'T';     
}  
\* Output:   
Elements written to output stream:  
OUT  
*\  
```  
  
##  <a name="op_eq"></a>  ostreambuf_iterator::operator=  
 İşleç, ilişkili akış ara belleğine bir karakter ekler.  
  
```
ostreambuf_iterator<CharType, Traits>& operator=(CharType _Char);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Char`  
 Akışı arabelleğe eklenecek karakter.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Akışı arabelleğe eklenen karakter referansı.  
  
### <a name="remarks"></a>Açıklamalar  
 Çıktı yineleyici ifade uygulamak için kullanılan atama işleci \* *ı* = *x* çıkış akışına yazmak için.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// ostreambuf_iterator_op_assign.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostreambuf_iterator for stream cout  
   // with new line delimiter  
   ostreambuf_iterator<char> charOutBuf ( cout );  
  
   // Standard iterator interface for writing  
   // elements to the output stream  
   cout << "Elements written to output stream:" << endl;  
 *charOutBuf = 'O';  
   charOutBuf++;      // No effect on iterator position  
 *charOutBuf = 'U';  
 *charOutBuf = 'T';     
}  
\* Output:   
Elements written to output stream:  
OUT  
*\  
```  
  
##  <a name="ostreambuf_iterator_ostreambuf_iterator"></a>  ostreambuf_iterator::ostreambuf_iterator  
 Oluşturan bir `ostreambuf_iterator` karakter çıkış akışına yazmak için başlatıldı.  
  
```
ostreambuf_iterator(streambuf_type* strbuf) throw();
ostreambuf_iterator(ostream_type& Ostr) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `strbuf`  
 Çıkış akışı arabellek işaretçisi başlatmak için kullanılan çıkış streambuf nesnesi.  
  
 `Ostr`  
 Çıkış akışı arabellek işaretçisi başlatmak için kullanılan çıkış akış nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Çıkış akışı arabellek işaretçiyle ilk Oluşturucu başlatır `strbuf`.  
  
 İkinci Oluşturucu, çıkış akışı arabellek işaretçi başlatır `Ostr`. `rdbuf`. Saklı işaretçisi null işaretçi olmaması gerekir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// ostreambuf_iteratorOstreambuf_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostreambuf_iterator for stream cout  
   ostreambuf_iterator<char> charOut ( cout );  
  
 *charOut = 'O';  
   charOut ++;  
 *charOut  = 'U';  
   charOut ++;     
 *charOut = 'T';  
   cout << " are characters output individually." << endl;  
  
   ostreambuf_iterator<char> strOut ( cout );  
   string str = "These characters are being written to the output stream.\n ";  
   copy ( str.begin ( ), str. end ( ), strOut );  
}  
\* Output:   
OUT are characters output individually.  
These characters are being written to the output stream.  
*\  
```  
  
##  <a name="ostreambuf_iterator_ostream_type"></a>  ostreambuf_iterator::ostream_type  
 Akış türü için sağlayan bir türü `ostream_iterator`.  
  
```
typedef basicOstream<CharType, Traits> ostream_type;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eşanlamlısı türüdür `basicOstream` \< **CharType**, **özellikleri**>  
  
### <a name="example"></a>Örnek  
  Bkz: [ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator) bildirme ve kullanma konusunda bir örnek için `ostream_type`.  
  
##  <a name="streambuf_type"></a>  ostreambuf_iterator::streambuf_type  
 Akış türü için sağlayan bir türü `ostreambuf_iterator`.  
  
```
typedef basic_streambuf<CharType, Traits> streambuf_type;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eşanlamlısı türüdür `basic_streambuf` \< **CharType**, **nitelikler**>, haline gelen bir akış sınıfı g/ç arabellekleri için `streambuf` karakter türü özelleştirilmişzaman`char`.  
  
### <a name="example"></a>Örnek  
  Bkz: [ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator) bildirme ve kullanma konusunda bir örnek için `streambuf_type`.  
  
##  <a name="traits_type"></a>  ostreambuf_iterator::traits_type  
 Karakter nitelikler tür sağlayan bir tür `ostream_iterator`.  
  
```
typedef Traits traits_type;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür **nitelikler**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// ostreambuf_iterator_traits_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef ostreambuf_iterator<char>::char_type CHT1;  
   typedef ostreambuf_iterator<char>::traits_type CHTR1;  
  
   // ostreambuf_iterator for stream cout  
   // with new line delimiter:  
    ostreambuf_iterator< CHT1, CHTR1> charOutBuf ( cout );  
  
   // Standard iterator interface for writing  
   // elements to the output streambuf:  
   cout << "The characters written to the output stream\n"  
        << " by charOutBuf are: ";  
 *charOutBuf = 'O';  
   charOutBuf++;  
 *charOutBuf = 'U';  
   charOutBuf++;  
 *charOutBuf = 'T';  
   charOutBuf++;  
   cout << "." << endl;  
}  
\* Output:   
The characters written to the output stream  
 by charOutBuf are: OUT.  
*\  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<iterator>](../standard-library/iterator.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)



