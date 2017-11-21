---
title: "&lt;dize&gt; işleçleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- string/std::operator!=
- string/std::operator&gt;
- string/std::operator&gt;&gt;
- string/std::operator&gt;=
- string/std::operator&lt;
- string/std::operator&lt;&lt;
- string/std::operator&lt;=
- string/std::operator+
- string/std::operator==
dev_langs: C++
ms.assetid: 33ce8f05-06c7-45d3-a0cb-bcd27cf93910
caps.latest.revision: "11"
manager: ghogen
helpviewer_keywords:
- std::operator!= (string)
- std::operator&gt; (string)
- std::operator&gt;&gt; (string)
- std::operator&gt;= (string)
- std::operator&lt; (string)
- std::operator&lt;&lt; (string)
- std::operator&lt;= (string), std::operator== (string)
ms.openlocfilehash: caa6cad7f0801b5459bd2999ae38a3da52c00469
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltstringgt-operators"></a>&lt;dize&gt; işleçleri
||||  
|-|-|-|  
|[operator! =](#op_neq)|[işleci&gt;](#op_gt)|[işleci&gt;&gt;](#op_gt_gt)|  
|[işleci&gt;=](#op_gt_eq)|[işleci&lt;](#op_lt)|[işleci&lt;&lt;](#op_lt_lt)|  
|[işleci&lt;=](#op_lt_eq)|[operator +](#op_add)|[operator ==](#op_eq_eq)|  
  
##  <a name="op_add"></a>operator +  
 İki dize nesnelerini art arda ekler.  
  
```  
template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator> operator+(
    const basic_string<CharType, Traits, Allocator>& left,  
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator> operator+(
    const basic_string<CharType, Traits, Allocator>& left,  
    const CharType* right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator> operator+(
    const basic_string<CharType, Traits, Allocator>& left,  
    const CharType right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator> operator+(
    const CharType* left,  
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator> operator+(
    const CharType left,  
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>& left,  
    const basic_string<CharType, Traits, Allocator>&& right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,  
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,  
    const basic_string<CharType, Traits, Allocator>&& right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,  
    const CharType* right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,  
    CharType right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator>&& operator+(
    const CharType* left,  
    const basic_string<CharType, Traits, Allocator>&& right);

template <class CharType, class Traits, class Allocator>  
basic_string<CharType, Traits, Allocator>&& operator+(
    CharType left,  
    const basic_string<CharType, Traits, Allocator>&& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 Bir C stili dize veya bir nesne türü `basic_string` birleştirilecek.  
  
 `right`  
 Bir C stili dize veya bir nesne türü `basic_string` birleştirilecek.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Giriş dizelerini yapıdır dize.  
  
### <a name="remarks"></a>Açıklamalar  
 Her işlevleri aşırı `operator+` iki nesne şablonu sınıfının birleştirmek için [basic_string sınıfı](../standard-library/basic-string-class.md). Tüm etkin bir şekilde dönüş `basic_string` \< **CharType**, **nitelikler**, **ayırıcısı**> (_ *sol*). [Append](../standard-library/basic-string-class.md#append)(\_ *sağ*).  
  
### <a name="example"></a>Örnek  
  
```cpp  
// string_op_con.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   // Declaring an object of type basic_string<char>  
   string s1 ( "anti" );  
   string s2 ( "gravity" );  
   cout << "The basic_string s1 = " << s1 << "." << endl;  
   cout << "The basic_string s2 = " << s2 << "." << endl;  
  
   // Declaring a C-style string  
   char *s3 = "heroine";  
   cout << "The C-style string s3 = " << s3 << "." << endl;  
  
   // Declaring a character constant  
   char c1 = '!';  
   cout << "The character constant c1 = " << c1 << "." << endl;  
  
   // First member function: concatenates an  object  
   // of type basic_string with an object of type basic_string  
   string s12 = s1 + s2;  
   cout << "The string concatenating s1 & s2 is: " << s12 << endl;  
  
   // Second & fourth member functions: concatenate an object  
   // of type basic_string with an object of C-syle string type  
   string s1s3 = s1 + s3;  
   cout << "The string concatenating s1 & s3 is: " << s1s3 << endl;  
  
   // Third & fifth member functions: concatenate an object  
   // of type basic_string with a character constant  
   string s1s3c1 = s1s3 + c1;  
   cout << "The string concatenating s1 & s3 is: " << s1s3c1 << endl;  
}  
```  
  
```Output  
The basic_string s1 = anti.  
The basic_string s2 = gravity.  
The C-style string s3 = heroine.  
The character constant c1 = !.  
The string concatenating s1 & s2 is: antigravity  
The string concatenating s1 & s3 is: antiheroine  
The string concatenating s1 & s3 is: antiheroine!  
```  
  
##  <a name="op_neq"></a>operator! =  
 Dize nesnesi işlecinin sol tarafındaki sağ tarafında dize nesnesi eşit değilse, testleri.  
  
```  
template <class CharType, class Traits, class Allocator>  
bool operator!=(
    const basic_string<CharType, Traits, Allocator>& left, 
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
bool operator!=(
    const basic_string<CharType, Traits, Allocator>& left, 
const CharType* right);

template <class CharType, class Traits, class Allocator>  
bool operator!=(
    const CharType* left, 
    const basic_string<CharType, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 Bir C stili dize veya bir nesne türü `basic_string` Karşılaştırılacak.  
  
 `right`  
 Bir C stili dize veya bir nesne türü `basic_string` Karşılaştırılacak.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** işlecinin sol tarafındaki dize nesnesi yoksa lexicographically sağ tarafında dize nesnesi eşit; Aksi takdirde **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 String nesneleri arasındaki karşılaştırma pairwise üzerinde temel kendi karakter lexicographical karşılaştırması. Karakter aynı sayıda varsa ve bunların karşılık gelen karakter değerleri aynı olan iki dizeyi eşit. Aksi takdirde, bunlar eşit.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// string_op_ne.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   // Declaring an objects of type basic_string<char>  
   string s1 ( "pluck" );  
   string s2 ( "strum" );  
   cout << "The basic_string s1 = " << s1 << "." << endl;  
   cout << "The basic_string s2 = " << s2 << "." << endl;  
  
   // Declaring a C-style string  
   char *s3 = "pluck";  
   cout << "The C-style string s3 = " << s3 << "." << endl;  
  
   // First member function: comparison between left-side object  
   // of type basic_string & right-side object of type basic_string  
   if ( s1 != s2 )  
      cout << "The strings s1 & s2 are not equal." << endl;  
   else  
      cout << "The strings s1 & s2 are equal." << endl;  
  
   // Second member function: comparison between left-side object  
   // of type basic_string & right-side object of C-syle string type  
   if ( s1 != s3 )  
      cout << "The strings s1 & s3 are not equal." << endl;  
   else  
      cout << "The strings s1 & s3 are equal." << endl;  
  
   // Third member function: comparison between left-side object  
   // of C-syle string type & right-side object of type basic_string  
   if ( s3 != s2 )  
      cout << "The strings s3 & s2 are not equal." << endl;  
   else  
      cout << "The strings s3 & s2 are equal." << endl;  
}  
```  
  
```Output  
The basic_string s1 = pluck.  
The basic_string s2 = strum.  
The C-style string s3 = pluck.  
The strings s1 & s2 are not equal.  
The strings s1 & s3 are equal.  
The strings s3 & s2 are not equal.  
```  
  
##  <a name="op_eq_eq"></a>operator ==  
 Dize nesnesi sağ tarafında işlecinin sol tarafındaki dize nesnesi eşitse testleri.  
  
```  
template <class CharType, class Traits, class Allocator>  
bool operator==(
    const basic_string<CharType, Traits, Allocator>& left, 
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
bool operator==(
    const basic_string<CharType, Traits, Allocator>& left, 
    const CharType* right);

template <class CharType, class Traits, class Allocator>  
bool operator==(
    const CharType* left, 
    const basic_string<CharType, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 Bir C stili dize veya bir nesne türü `basic_string` Karşılaştırılacak.  
  
 `right`  
 Bir C stili dize veya bir nesne türü `basic_string` Karşılaştırılacak.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** işlecinin sol tarafındaki dize nesnesi eşitse lexicographically dize nesnesine sağ tarafında aksi **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 String nesneleri arasındaki karşılaştırma pairwise üzerinde temel kendi karakter lexicographical karşılaştırması. Karakter aynı sayıda varsa ve bunların karşılık gelen karakter değerleri aynı olan iki dizeyi eşit. Aksi takdirde, bunlar eşit.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// string_op_eq.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   // Declaring an objects of type basic_string<char>  
   string s1 ( "pluck" );  
   string s2 ( "strum" );  
   cout << "The basic_string s1 = " << s1 << "." << endl;  
   cout << "The basic_string s2 = " << s2 << "." << endl;  
  
   // Declaring a C-style string  
   char *s3 = "pluck";  
   cout << "The C-style string s3 = " << s3 << "." << endl;  
  
   // First member function: comparison between left-side object  
   // of type basic_string & right-side object of type basic_string  
   if ( s1 == s2 )  
      cout << "The strings s1 & s2 are equal." << endl;  
   else  
      cout << "The strings s1 & s2 are not equal." << endl;  
  
   // Second member function: comparison between left-side object  
   // of type basic_string & right-side object of C-syle string type  
   if ( s1 == s3 )  
      cout << "The strings s1 & s3 are equal." << endl;  
   else  
      cout << "The strings s1 & s3 are not equal." << endl;  
  
   // Third member function: comparison between left-side object  
   // of C-syle string type & right-side object of type basic_string  
   if ( s3 == s2 )  
      cout << "The strings s3 & s2 are equal." << endl;  
   else  
      cout << "The strings s3 & s2 are not equal." << endl;  
}  
```  
  
```Output  
The basic_string s1 = pluck.  
The basic_string s2 = strum.  
The C-style string s3 = pluck.  
The strings s1 & s2 are not equal.  
The strings s1 & s3 are equal.  
The strings s3 & s2 are not equal.  
```  
  
##  <a name="op_lt"></a>işleci&lt;  
 Dize nesnesi işlecinin sol tarafındaki çok kısa ise test sağ tarafında dize nesnesi.  
  
```  
template <class CharType, class Traits, class Allocator>  
bool operator<(
    const basic_string<CharType, Traits, Allocator>& left, 
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
bool operator<(
    const basic_string<CharType, Traits, Allocator>& left, 
    const CharType* right);

template <class CharType, class Traits, class Allocator>  
bool operator<(
    const CharType* left, 
    const basic_string<CharType, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 Bir C stili dize veya bir nesne türü `basic_string` Karşılaştırılacak.  
  
 `right`  
 Bir C stili dize veya bir nesne türü `basic_string` Karşılaştırılacak.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** işlecinin sol tarafındaki dize nesnesi sağ tarafında; dize nesnesi lexicographically değerinden ise, aksi takdirde **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Dizeleri lexicographical karşılaştırması bunları karakter kadar karşılaştırılır:  
  
-   İki karşılık gelen karakter eşit olmayan bulur ve bunların karşılaştırma sonucu arasında dizeleri karşılaştırma sonucu olarak alınır.  
  
-   Hiçbir inequalities bulur, ancak bir dizesi uzun dize değerinden diğer ve daha kısa bir dize olarak kabul daha fazla karakter içeriyor.  
  
-   Hiçbir inequalities ve aynı sayıda karakter dizeleri olan ve böylece dizeleri eşit bulur bulur.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// string_op_lt.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   // Declaring an objects of type basic_string<char>  
   string s1 ( "strict" );  
   string s2 ( "strum" );  
   cout << "The basic_string s1 = " << s1 << "." << endl;  
   cout << "The basic_string s2 = " << s2 << "." << endl;  
  
   // Declaring a C-style string  
   char *s3 = "strict";  
   cout << "The C-style string s3 = " << s3 << "." << endl;  
  
   // First member function: comparison between left-side object  
   // of type basic_string & right-side object of type basic_string  
   if ( s1 < s2 )  
      cout << "The string s1 is less than the string s2." << endl;  
   else  
      cout << "The string s1 is not less than the string s2." << endl;  
  
   // Second member function: comparison between left-hand object  
   // of type basic_string & right-hand object of C-syle string type  
   if ( s1 < s3 )  
      cout << "The string s1 is less than the string s3." << endl;  
   else  
      cout << "The string s1 is not less than the string s3." << endl;  
  
   // Third member function: comparison between left-hand object  
   // of C-syle string type & right-hand object of type basic_string  
   if ( s3 < s2 )  
      cout << "The string s3 is less than the string s2." << endl;  
   else  
      cout << "The string s3 is not less than the string s2." << endl;  
}  
```  
  
```Output  
The basic_string s1 = strict.  
The basic_string s2 = strum.  
The C-style string s3 = strict.  
The string s1 is less than the string s2.  
The string s1 is not less than the string s3.  
The string s3 is less than the string s2.  
```  
  
##  <a name="op_lt_eq"></a>işleci&lt;=  
 Dize işlecinin sol tarafında nesne sağlayıp sağlamadığını test sağ tarafında dize nesnesine eşit veya daha az olur.  
  
```  
template <class CharType, class Traits, class Allocator>  
bool operator<=(
    const basic_string<CharType, Traits, Allocator>& left, 
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
bool operator<=(
    const basic_string<CharType, Traits, Allocator>& left, 
    const CharType* right);

template <class CharType, class Traits, class Allocator>  
bool operator<=(
    const CharType* left, 
    const basic_string<CharType, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 Bir C stili dize veya bir nesne türü `basic_string` Karşılaştırılacak.  
  
 `right`  
 Bir C stili dize veya bir nesne türü `basic_string` Karşılaştırılacak.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** işlecinin sol tarafındaki dize nesnesi lexicographically daha az veya sağ tarafında dize nesnesi eşit; Aksi takdirde ise **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Dizeleri lexicographical karşılaştırması bunları karakter kadar karşılaştırılır:  
  
-   İki karşılık gelen karakter eşit olmayan bulur ve bunların karşılaştırma sonucu arasında dizeleri karşılaştırma sonucu olarak alınır.  
  
-   Hiçbir inequalities bulur, ancak bir dizesi uzun dize değerinden diğer ve daha kısa bir dize olarak kabul daha fazla karakter içeriyor.  
  
-   Hiçbir inequalities ve dizeleri eşit olacak şekilde dizeleri aynı sayıda karakter olan bulur bulur.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// string_op_le.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   // Declaring an objects of type basic_string<char>  
   string s1 ( "strict" );  
   string s2 ( "strum" );  
   cout << "The basic_string s1 = " << s1 << "." << endl;  
   cout << "The basic_string s2 = " << s2 << "." << endl;  
  
   // Declaring a C-style string  
   char *s3 = "strict";  
   cout << "The C-style string s3 = " << s3 << "." << endl;  
  
   // First member function: comparison between left-side object  
   // of type basic_string & right-side object of type basic_string  
   if ( s1 <= s2 )  
      cout << "The string s1 is less than or equal to "  
           << "the string s2." << endl;  
   else  
      cout << "The string s1 is greater than "  
           << "the string s2." << endl;  
  
   // Second member function: comparison between left-side object  
   // of type basic_string & right-side object of C-syle string type  
   if ( s1 <= s3 )  
      cout << "The string s1 is less than or equal to "  
           << "the string s3." << endl;  
   else  
      cout << "The string s1 is greater than "  
           << "the string s3." << endl;  
  
   // Third member function: comparison between left-side object  
   // of C-syle string type  & right-side object of type basic_string  
   if ( s2 <= s3 )  
      cout << "The string s2 is less than or equal to "  
           << "the string s3." << endl;  
   else  
      cout << "The string s2 is greater than "  
           << "the string s3." << endl;  
}  
```  
  
```Output  
The basic_string s1 = strict.  
The basic_string s2 = strum.  
The C-style string s3 = strict.  
The string s1 is less than or equal to the string s2.  
The string s1 is less than or equal to the string s3.  
The string s2 is greater than the string s3.  
```  
  
##  <a name="op_lt_lt"></a>işleci&lt;&lt;  
 Bir dize çıkış akışına Yazar şablon işlevi.  
  
```  
template <class CharType, class Traits, class Allocator>  
basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& _Ostr, 
    const basic_string<CharType, Traits, Allocator>& str);
```  
  
### <a name="parameters"></a>Parametreler  
 _Ostr  
 Üzerine yazılan çıkış akışı.  
  
 `str`  
 Çıkış akışı girilmesi dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen dize değeri çıkış akışına Yazar `_Ostr`.  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon işlev aşırı yüklemelerinin **işleci <<** eklemek için bir nesne _ *Str* şablon sınıfının [basic_string](../standard-library/basic-string-class.md) akışa \_  *Ostr.* İşlev etkili bir şekilde döndürür \_ *Ostr*. **Yazma**( \_ *Str*. [c_str](../standard-library/basic-string-class.md#c_str), \_ *Str*. [boyutu](../standard-library/basic-string-class.md#size)).  
  
##  <a name="op_gt"></a>işleci&gt;  
 Dize nesnesi işlecinin sol tarafındaki dize nesnesine sağ tarafında büyükse testleri.  
  
```  
template <class CharType, class Traits, class Allocator>  
bool operator>(
    const basic_string<CharType, Traits, Allocator>& left, 
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
bool operator>(
    const basic_string<CharType, Traits, Allocator>& left, 
    const CharType* right);

template <class CharType, class Traits, class Allocator>  
bool operator>(
    const CharType* left, 
    const basic_string<CharType, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 Bir C stili dize veya bir nesne türü `basic_string` Karşılaştırılacak.  
  
 `right`  
 Bir C stili dize veya bir nesne türü `basic_string` Karşılaştırılacak.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** işlecinin sol tarafındaki dize nesnesi lexicographically sağ tarafında dize nesnesi büyüktür; Aksi takdirde ise **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Dizeleri lexicographical karşılaştırması bunları karakter kadar karşılaştırılır:  
  
-   İki karşılık gelen karakter eşit olmayan bulur ve bunların karşılaştırma sonucu arasında dizeleri karşılaştırma sonucu olarak alınır.  
  
-   Hiçbir inequalities bulur, ancak bir dizesi uzun dize değerinden diğer ve daha kısa bir dize olarak kabul daha fazla karakter içeriyor.  
  
-   Hiçbir inequalities ve aynı sayıda karakter dizeleri olan ve böylece dizeleri eşit bulur bulur.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// string_op_gt.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   // Declaring an objects of type basic_string<char>  
   string s1 ( "strict" );  
   string s2 ( "strum" );  
   cout << "The basic_string s1 = " << s1 << "." << endl;  
   cout << "The basic_string s2 = " << s2 << "." << endl;  
  
   // Declaring a C-style string  
   char *s3 = "stricture";  
   cout << "The C-style string s3 = " << s3 << "." << endl;  
  
   // First member function: comparison between left-side object  
   // of type basic_string & right-side object of type basic_string  
   if ( s1 > s2 )  
      cout << "The string s1 is greater than "  
           << "the string s2." << endl;  
   else  
      cout << "The string s1 is not greater than "  
           << "the string s2." << endl;  
  
   // Second member function: comparison between left-side object  
   // of type basic_string & right-side object of C-syle string type  
   if ( s3 > s1 )  
      cout << "The string s3 is greater than "  
           << "the string s1." << endl;  
   else  
      cout << "The string s3 is not greater than "  
           << "the string s1." << endl;  
  
   // Third member function: comparison between left-side object  
   // of C-syle string type & right-side object of type basic_string  
   if ( s2 > s3 )  
      cout << "The string s2 is greater than "  
           << "the string s3." << endl;  
   else  
      cout << "The string s2 is not greater than "  
           << "the string s3." << endl;  
}  
```  
  
```Output  
The basic_string s1 = strict.  
The basic_string s2 = strum.  
The C-style string s3 = stricture.  
The string s1 is not greater than the string s2.  
The string s3 is greater than the string s1.  
The string s2 is greater than the string s3.  
```  
  
##  <a name="op_gt_eq"></a>işleci&gt;=  
 Dize nesnesi işlecinin sol tarafındaki büyük veya ona eşit dize nesnesine sağ tarafında ise testleri.  
  
```  
template <class CharType, class Traits, class Allocator>  
bool operator>=(
    const basic_string<CharType, Traits, Allocator>& left, 
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>  
bool operator>=(
    const basic_string<CharType, Traits, Allocator>& left, 
    const CharType* right);

template <class CharType, class Traits, class Allocator>  
bool operator>=(
    const CharType* left, 
    const basic_string<CharType, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 Bir C stili dize veya bir nesne türü `basic_string` Karşılaştırılacak.  
  
 `right`  
 Bir C stili dize veya bir nesne türü `basic_string` Karşılaştırılacak.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** işlecinin sol tarafındaki dize nesnesi eşitse lexicographically değerinden veya dize nesnesine sağ tarafında aksi **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Dizeleri lexicographical karşılaştırması bunları karakter kadar karşılaştırılır:  
  
-   İki karşılık gelen karakter eşit olmayan bulur ve bunların karşılaştırma sonucu arasında dizeleri karşılaştırma sonucu olarak alınır.  
  
-   Hiçbir inequalities bulur, ancak bir dizesi uzun dize değerinden diğer ve daha kısa bir dize olarak kabul daha fazla karakter içeriyor.  
  
-   Hiçbir inequalities ve aynı sayıda karakter dizeleri olan ve böylece dizeleri eşit bulur bulur.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// string_op_ge.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   // Declaring an objects of type basic_string<char>  
   string s1 ( "strict" );  
   string s2 ( "strum" );  
   cout << "The basic_string s1 = " << s1 << "." << endl;  
   cout << "The basic_string s2 = " << s2 << "." << endl;  
  
   // Declaring a C-style string  
   char *s3 = "stricture";  
   cout << "The C-style string s3 = " << s3 << "." << endl;  
  
   // First member function: comparison between left-side object  
   // of type basic_string & right-side object of type basic_string  
   if ( s1 >= s2 )  
      cout << "The string s1 is greater than or equal to "  
           << "the string s2." << endl;  
   else  
      cout << "The string s1 is less than "  
           << "the string s2." << endl;  
  
   // Second member function: comparison between left-side object  
   // of type basic_string & right-side object of C-syle string type  
   if ( s3 >= s1 )  
      cout << "The string s3 is greater than or equal to "  
           << "the string s1." << endl;  
   else  
      cout << "The string s3 is less than "  
           << "the string s1." << endl;  
  
   // Third member function: comparison between left-side object  
   // of C-syle string type & right-side object of type basic_string  
   if ( s2 >= s3 )  
      cout << "The string s2 is greater than or equal to "  
           << "the string s3." << endl;  
   else  
      cout << "The string s2 is less than "  
           << "the string s3." << endl;  
}  
```  
  
```Output  
The basic_string s1 = strict.  
The basic_string s2 = strum.  
The C-style string s3 = stricture.  
The string s1 is less than the string s2.  
The string s3 is greater than or equal to the string s1.  
The string s2 is greater than or equal to the string s3.  
```  
  
##  <a name="op_gt_gt"></a>işleci&gt;&gt;  
 Bir dizeyi bir giriş akışından okuma şablon işlevi.  
  
```  
template <class CharType, class Traits, class Allocator>  
basic_istream<CharType, Traits>& operator>>(
    basic_istream<CharType, Traits>& _Istr,  
    basic_string<CharType, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Istr`  
 Sıra çıkarmak için kullanılan giriş akışı  
  
 `right`  
 Giriş akışından ayıklanan dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen dize değeri okuyan `_Istr` ve içine döndürür `right`.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleç başında boşluk sürece atlar `skipws` bayrağı ayarlanır. Sonraki karakteri boşluk veya dosya sonuna ulaşıldı kadar tüm karakterlerden okur.  
  
 Şablon işlev aşırı yüklemelerinin **işleci >>** tarafından denetlenen sırasını değiştirmek için `right` akıştan ayıklanan öğe dizisi ile `_Istr`. Ayıklama durdurur:  
  
-   Dosya sonu.  
  
-   İşlev ayıklar sonra `_Istr`. **Genişlik** öğeleri, bu değeri sıfır değilse.  
  
 İşlev ayıklar sonra `_Istr`. [max_size](../standard-library/basic-string-class.md#max_size) öğeleri.  
  
-   Bir öğenin işlevi ayıklar sonra *ch* kendisi için [use_facet](../standard-library/basic-filebuf-class.md#open)< **ctype** \< **CharType**> > ( `getloc`). **olan**( **ctype** \< **CharType**>:: **alanı**, *ch*) karakteri put; bu durumda true Geri.  
  
 Öğe işlevi ayıklar, çağıran [setstate](../standard-library/basic-ios-class.md#setstate)( `ios_base::failbit`). Herhangi bir durumda, çağıran **istr**. **Genişlik**(0) ve döndürür \* **bu**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// string_op_read_.cpp  
// compile with: /EHsc  
#include <string>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   string c0;  
   cout << "Input a string c0 ( try: Fibonacci numbers ): ";  
   cin >> c0;  
   cout << "The string entered is c0 = " << c0 << endl;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<dize >](../standard-library/string.md)
