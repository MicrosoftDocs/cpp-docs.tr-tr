---
title: "istreambuf_iterator sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- streambuf/std::istreambuf_iterator
- iterator/std::istreambuf_iterator::char_type
- iterator/std::istreambuf_iterator::int_type
- iterator/std::istreambuf_iterator::istream_type
- iterator/std::istreambuf_iterator::streambuf_type
- iterator/std::istreambuf_iterator::traits_type
- iterator/std::istreambuf_iterator::equal
dev_langs:
- C++
helpviewer_keywords:
- std::istreambuf_iterator [C++]
- std::istreambuf_iterator [C++], char_type
- std::istreambuf_iterator [C++], int_type
- std::istreambuf_iterator [C++], istream_type
- std::istreambuf_iterator [C++], streambuf_type
- std::istreambuf_iterator [C++], traits_type
- std::istreambuf_iterator [C++], equal
ms.assetid: 39002da2-61a6-48a5-9d0c-5df8271f6038
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dc69f36b5dae84775025b2e7e8086321dfe55fd5
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="istreambufiterator-class"></a>istreambuf_iterator Sınıfı
Şablon sınıfı istreambuf_iterator depoladığı, türü işaretçinin nesnesi aracılığıyla erişen bir giriş akışı arabellek gelen karakter öğeleri ayıklar bir giriş yineleyici nesneyi tanımlayan `basic_streambuf` \< **CharType** , **Nitelikler**>.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class CharType class Traits = char_traits <CharType>>  
class istreambuf_iterator 
: public iterator<input_iterator_tag, CharType, typename Traits ::off_type, CharType*, CharType&>
```  
  
#### <a name="parameters"></a>Parametreler  
 `CharType`  
 istreambuf_iterator için karakter türünü temsil eden tür.  
  
 `Traits`  
 istreambuf_iterator için karakter türünü temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `char_traits` \< *CharType >.*  
  
## <a name="remarks"></a>Açıklamalar  
 istreambuf_iterator sınıfının, bir giriş yineleyici için gereksinimleri karşılaması gerekir.  
  
 Oluşturma veya null olmayan saklı işaretçiyle sınıfı istreambuf_iterator nesnenin artırma sonra nesneyi etkili bir şekilde ayıklayın ve türünde bir nesne depolamak çalışır **CharType** ilişkili giriş akışından. Ayıklama, ancak nesne başvurusu kaldırılana veya kopyalanana kadar gecikebilir. Ayıklama işlemi başarısız olursa, nesne etkili bir şekilde depolanan işaretçinin yerini alır, böylece bir dizi sonu gösterge oluşturur.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[istreambuf_iterator](#istreambuf_iterator)|Oluşturan bir `istreambuf_iterator` karakter giriş akışından okumaya başlatıldı.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[char_type](#char_type)|Karakter türü için sağlayan bir türü `ostreambuf_iterator`.|  
|[int_type](#int_type)|Bir tamsayı türü için sağlayan bir türü bir `istreambuf_iterator`.|  
|[istream_type](#istream_type)|Akış türü için sağlayan bir türü `istream_iterator`.|  
|[streambuf_type](#streambuf_type)|Akış türü için sağlayan bir türü `istreambuf_iterator`.|  
|[traits_type](../standard-library/istream-iterator-class.md#traits_type)|Karakter nitelikler tür sağlayan bir tür `istream_iterator`.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[Eşittir](#equal)|İki giriş akışı önbelleği yineleyicisi arasındaki eşitliği sınar.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[operator*](#op_star)|Başvuru kaldırma işleci akıştaki sonraki karakteri döndürür.|  
|[operator++](#op_add_add)|Giriş akışındaki sonraki öğeyi döndürür ya da artırmadan önce nesneyi kopyalar ve kopyayı döndürür.|  
|[operator->](#operator-_gt)|Varsa, bir üyenin değerini döndürür.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<yineleyici >  
  
 **Namespace:** std  
  
##  <a name="char_type"></a>  istreambuf_iterator::char_type  
 Karakter türü için sağlayan bir türü `ostreambuf_iterator`.  
  
```
typedef CharType char_type;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür **CharType**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// istreambuf_iterator_char_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
#include <algorithm>  
  
int main( )  
{  
   using namespace std;  
  
   typedef istreambuf_iterator<char>::char_type CHT1;  
   typedef istreambuf_iterator<char>::traits_type CHTR1;  
  
   cout << "(Try the example: 'So many dots to be done'\n"  
        << " then an Enter key to insert into the output,\n"  
        << " & use a ctrl-Z Enter key combination to exit): ";  
  
   // istreambuf_iterator for input stream  
   istreambuf_iterator< CHT1, CHTR1> charInBuf ( cin );  
   ostreambuf_iterator<char> charOut ( cout );  
  
   // Used in conjunction with replace_copy algorithm  
   // to insert into output stream and replace spaces  
   // with dot-separators  
   replace_copy ( charInBuf , istreambuf_iterator<char>( ),  
        charOut , ' ' , '.' );  
}  
```  
  
##  <a name="equal"></a>  istreambuf_iterator::Equal  
 İki giriş akışı arabellek yineleyiciler arasında eşdeğer için testleri.  
  
```
bool equal(const istreambuf_iterator<CharType, Traits>& right) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Yineleyici eşitlik için denetlemek üzere.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** her iki `istreambuf_iterator`s: akış uç yineleyiciler veya, bir akış uç yineleyici; olup aksi **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir aralık tarafından tanımlanan `istreambuf_iterator` geçerli konumu ve akış uç Yineleyici, ancak tüm olmayan-end-of akış itibaren yineleyiciler altında eşdeğer **eşit** üye işlevi, tüm alt aralıklara tanımlamanızı mümkün değildir kullanarak `istreambuf_iterator`s. `==` Ve `!=` operatörleri aynı semantiğini sahiptir.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// istreambuf_iterator_equal.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   cout << "(Try the example: 'Hello world!'\n"  
        << " then an Enter key to insert into the output,\n"  
        << " & use a ctrl-Z Enter key combination to exit): ";  
  
   istreambuf_iterator<char> charReadIn1 ( cin );  
   istreambuf_iterator<char> charReadIn2 ( cin );  
  
   bool b1 = charReadIn1.equal ( charReadIn2 );  
  
   if (b1)  
      cout << "The iterators are equal." << endl;  
   else  
      cout << "The iterators are not equal." << endl;  
}  
```  
  
##  <a name="int_type"></a>  istreambuf_iterator::int_type  
 Bir tamsayı türü için sağlayan bir türü bir `istreambuf_iterator`.  
  
```
typedef typename traits_type::int_type int_type;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eşanlamlısı türüdür **Traits::int_type**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// istreambuf_iterator_int_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   istreambuf_iterator<char>::int_type inttype1 = 100;  
   cout << "The inttype1 = " << inttype1 << "." << endl;  
}  
\* Output:   
The inttype1 = 100.  
*\  
```  
  
##  <a name="istream_type"></a>  istreambuf_iterator::istream_type  
 Akış türü için sağlayan bir türü `istreambuf_iterator`.  
  
```
typedef basic_istream<CharType, Traits> istream_type;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eşanlamlısı türüdür `basic_istream` \< **CharType**, **nitelikler**>.  
  
### <a name="example"></a>Örnek  
  Bkz: [istreambuf_iterator](#istreambuf_iterator) bildirme ve kullanma konusunda bir örnek için `istream_type`.  
  
##  <a name="istreambuf_iterator"></a>  istreambuf_iterator::istreambuf_iterator  
 Karakter giriş akışından okuma için başlatılan bir istreambuf_iterator oluşturur.  
  
```
istreambuf_iterator(streambuf_type* strbuf = 0) throw();
istreambuf_iterator(istream_type& _Istr) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `strbuf`  
 Giriş akışı arabelleğe `istreambuf_iterator` iliştirilmekte.  
  
 `_Istr`  
 Giriş akış `istreambuf_iterator` iliştirilmekte.  
  
### <a name="remarks"></a>Açıklamalar  
 Giriş akışı arabelleği işaretçisi ile ilk Oluşturucu başlatır `strbuf`. Giriş akışı arabelleği işaretçisi ile ikinci oluşturucu başlatır `_Istr`. `rdbuf`ve ayıklamak ve türünde bir nesne depolamak sonunda girişimleri **CharType**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// istreambuf_iterator_istreambuf_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <algorithm>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Following declarations will not compile:  
   istreambuf_iterator<char>::istream_type &istrm = cin;  
   istreambuf_iterator<char>::streambuf_type *strmbf = cin.rdbuf( );  
  
   cout << "(Try the example: 'Oh what a world!'\n"  
      << " then an Enter key to insert into the output,\n"  
      << " & use a ctrl-Z Enter key combination to exit): ";  
   istreambuf_iterator<char> charReadIn ( cin );  
   ostreambuf_iterator<char> charOut ( cout );  
  
   // Used in conjunction with replace_copy algorithm  
   // to insert into output stream and replace spaces  
   // with hyphen-separators  
   replace_copy ( charReadIn , istreambuf_iterator<char>( ),  
      charOut , ' ' , '-' );  
}  
```  
  
##  <a name="op_star"></a>  istreambuf_iterator::operator*  
 Başvuru kaldırma işleci akıştaki sonraki karakteri döndürür.  
  
```
CharType operator*() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Akıştaki sonraki karakteri.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// istreambuf_iterator_operator_deref.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   cout << "Type string of characters & enter to output it,\n"  
      << " with stream buffer iterators,(try: 'I'll be back.')\n"  
      << " repeat as many times as desired,\n"   
      << " then keystroke ctrl-Z Enter to exit program: ";  
   istreambuf_iterator<char> inpos ( cin );  
   istreambuf_iterator<char> endpos;  
   ostreambuf_iterator<char> outpos ( cout );  
   while ( inpos != endpos )  
   {  
 *outpos = *inpos;   //Put value of outpos equal to inpos  
      ++inpos;  
      ++outpos;  
   }  
}  
```  
  
##  <a name="op_add_add"></a>  istreambuf_iterator::operator++  
 Giriş akışındaki sonraki öğeyi döndürür ya da artırmadan önce nesneyi kopyalar ve kopyayı döndürür.  
  
```
istreambuf_iterator<CharType, Traits>& operator++();
istreambuf_iterator<CharType, Traits> operator++(int);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir `istreambuf_iterator` veya bir başvuru bir `istreambuf_iterator`.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk işleci sonunda ayıklayın ve türünde bir nesne depolamak girişiminde **CharType** ilişkili giriş akışından. İkinci işleci nesne bir kopyasını oluşturur, nesne artırır ve kopyayı döndürür.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// istreambuf_iterator_operator_incr.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   cout << "Type string of characters & enter to output it,\n"  
      << " with stream buffer iterators,(try: 'I'll be back.')\n"  
      << " repeat as many times as desired,\n"   
      << " then keystroke ctrl-Z Enter to exit program: ";  
   istreambuf_iterator<char> inpos ( cin );  
   istreambuf_iterator<char> endpos;  
   ostreambuf_iterator<char> outpos ( cout );  
   while ( inpos != endpos )  
   {  
 *outpos = *inpos;  
      ++inpos;   //Increment istreambuf_iterator  
      ++outpos;  
   }  
}  
```  
  
##  <a name="istreambuf_iterator__operator-_gt"></a>  istreambuf_iterator::operator-&gt;  
 Varsa, bir üyenin değerini döndürür.  
  
```
const Elem* operator->() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşleç döndürür  **& \* \*bu**.  
  
##  <a name="streambuf_type"></a>  istreambuf_iterator::streambuf_type  
 İstreambuf_iterator akışı türü için sağlayan türü.  
  
```
typedef basic_streambuf<CharType, Traits> streambuf_type;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eşanlamlısı türüdür `basic_streambuf` \< **CharType**, **nitelikler**>.  
  
### <a name="example"></a>Örnek  
  Bkz: [istreambuf_iterator](#istreambuf_iterator) bildirme ve kullanma konusunda bir örnek için **istreambuf_type**.  
  
##  <a name="traits_type"></a>  istreambuf_iterator::traits_type  
 Karakter nitelikler tür sağlayan bir tür `istream_iterator`.  
  
```
typedef Traits traits_type;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür **nitelikler**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// istreambuf_iterator_traits_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
#include <algorithm>  
  
int main( )  
{  
   using namespace std;  
  
   typedef istreambuf_iterator<char>::char_type CHT1;  
   typedef istreambuf_iterator<char>::traits_type CHTR1;  
  
   cout << "(Try the example: 'So many dots to be done'\n"  
        << " then an Enter key to insert into the output,\n"  
        << " & use a ctrl-Z Enter key combination to exit): ";  
  
   // istreambuf_iterator for input stream  
   istreambuf_iterator< CHT1, CHTR1> charInBuf ( cin );  
   ostreambuf_iterator<char> charOut ( cout );  
  
   // Used in conjunction with replace_copy algorithm  
   // to insert into output stream and replace spaces  
   // with dot-separators  
   replace_copy ( charInBuf , istreambuf_iterator<char>( ),  
        charOut , ' ' , '.' );  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [iterator yapısı](../standard-library/iterator-struct.md)   
 [\<iterator>](../standard-library/iterator.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)



