---
title: "&lt;bitset&gt; işleçleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- bitset/std::operator&amp;
- bitset/std::operator&gt;&gt;
- bitset/std::operator&lt;&lt;
- bitset/std::operator^
- bitset/std::operator|
dev_langs: C++
ms.assetid: 84fe6a13-6f6e-4cdc-bf8f-6f65ab1134d4
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::operator&amp; (bitset)
- std::operator&gt;&gt; (bitset)
- std::operator&lt;&lt; (bitset)
ms.openlocfilehash: 09c3ac2317fce1e539ed02a501078fe83c217ca1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltbitsetgt-operators"></a>&lt;bitset&gt; işleçleri
||||  
|-|-|-|  
|[işleci&amp;](#op_amp)|[işleci&gt;&gt;](#op_gt_gt)|[işleci&lt;&lt;](#op_lt_lt)|  
|[operator ^](#op_xor)|[işleci|](#op_or)|  
  
##  <a name="op_amp"></a>işleci&amp;  
 Bit tabanlı gerçekleştirir `AND` iki bit kümeleri arasında.  
  
```  
template <size_t size>  
bitset<size>  
operator&(
    const bitset<size>& left,  
    const bitset<size>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 İlgili öğeleri olan Bitsel ile birleştirilecek iki bit kümeleri ilk `AND`.  
  
 `right`  
 İlgili öğeleri olan Bitsel ile birleştirilecek iki valarrays ikinci `AND`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeleri olan sonucunu bitset `AND` karşılık gelen öğelerini işlemi `left` ve `right`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// bitset_and.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
#include <string>  
  
using namespace std;  
  
int main()  
{  
   bitset<4> b1 ( string("0101") );  
   bitset<4> b2 ( string("0011") );  
   bitset<4> b3 = b1 & b2;  
   cout << "bitset 1: " << b1 << endl;  
   cout << "bitset 2: " << b2 << endl;  
   cout << "bitset 3: " << b3 << endl;  
}  
```  
  
```Output  
bitset 1: 0101  
bitset 2: 0011  
bitset 3: 0001  
```  
  
##  <a name="op_lt_lt"></a>işleci&lt;&lt;  
 Bit sırası metin gösterimini çıkış akışına ekler.  
  
```  
 
template <class CharType, class Traits, size_t N>  
basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& ostr,  
    const bitset<N>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Türünde bir nesne **bitset\<N >** olan bir dize olarak çıktısı akışa eklenecek.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bit sırayla metin gösterimini **ostr**.  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon işlev aşırı yüklemelerinin **işleci <<**, ilk dizeye dönüştürmeden yazılmalıdır bitset izin verme. Şablon işlevi etkin şekilde şunları yürütür:  
  
 **ostr** << _ *sağ*. [to_string](https://msdn.microsoft.com/library/2f93c55z.aspx) < **CharType**, **nitelikler**, **ayırıcısı** \< **CharType**>> ( )  
  
### <a name="example"></a>Örnek  
  
```cpp  
// bitset_op_insert.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
#include <string>  
  
int main( )  
{  
   using namespace std;  
  
   bitset<5> b1 ( 9 );  
  
   // bitset inserted into output stream directly  
   cout << "The ordered set of bits in the bitset<5> b1(9)"  
        << "\n can be output with the overloaded << as: ( "  
        << b1 << " )" << endl;  
  
   // Compare converting bitset to a string before  
   // inserting it into the output steam  
   string s1;  
   s1 =  b1.template to_string<char,   
      char_traits<char>, allocator<char> >( );  
   cout << "The string returned from the bitset b1"  
        << "\n by the member function to_string( ) is: "  
        << s1 << "." << endl;  
}  
```  
  
##  <a name="op_gt_gt"></a>işleci&gt;&gt;  
 Bit karakter dizesi bitset okur.  
  
```  
 
template <class CharType, class Traits, size_t Bits>  
basic_istream<CharType, Traits>& operator>> (
    basic_istream<CharType, Traits>& 
_Istr,  
    bitset<N>& 
    right);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Istr`  
 Bitset eklenecek Giriş akışı girilir dize.  
  
 `right`  
 BITS giriş akışından alıyor bitset.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Şablon işlevi dizesini döndürür `_Istr`.  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon işlev aşırı yüklemelerinin **işleci >>** depolamak için bitset _ *sağ* değeri bitset ( `str`), burada `str` türünde bir nesne [basic_string ](https://msdn.microsoft.com/library/syxtdd4f.aspx)  <  **CharType**, **nitelikler**, **ayırıcısı** \< **CharType**> >  **&**  ayıklanan `_Istr`.  
  
 Şablon işlevi öğeleri ayıklar `_Istr` ve bunları kadar bitset ekler:  
  
-   Tüm bit öğeleri giriş akışından ayıklanan ve bitset depolanır.  
  
-   Bitset Giriş akışı bitten ile doldurulur.  
  
-   Bir input öğesi türünün 0 veya 1 olan karşılaşıldı.  
  
### <a name="example"></a>Örnek  
  
```cpp  
#include <bitset>  
#include <iostream>  
#include <string>  
  
using namespace std;  
int main()  
{  
  
   bitset<5> b1;  
   cout << "Enter string of (0 or 1) bits for input into bitset<5>.\n"  
        << "Try bit string of length less than or equal to 5,\n"  
        << " (for example: 10110): ";  
   cin >>  b1;  
  
   cout << "The ordered set of bits entered from the "  
        << "keyboard\n has been input into bitset<5> b1 as: ( "  
        << b1 << " )" << endl;  
  
   // Truncation due to longer string of bits than length of bitset  
   bitset<2> b3;  
   cout << "Enter string of bits (0 or 1) for input into bitset<2>.\n"  
        << " Try bit string of length greater than 2,\n"  
        << " (for example: 1011): ";  
   cin >>  b3;  
  
   cout << "The ordered set of bits entered from the "  
        << "keyboard\n has been input into bitset<2> b3 as: ( "  
        << b3 << " )" << endl;  
  
   // Flushing the input stream  
   char buf[100];  
   cin.getline(&buf[0], 99);  
  
   // Truncation with non-bit value  
   bitset<5> b2;  
   cout << "Enter a string for input into  bitset<5>.\n"  
        << " that contains a character than is NOT a 0 or a 1,\n "  
        << " (for example: 10k01): ";  
   cin >>  b2;  
  
   cout << "The string entered from the keyboard\n"  
        << " has been input into bitset<5> b2 as: ( "  
        << b2 << " )" << endl;  
}  
```  
  
##  <a name="op_xor"></a>operator ^  
 Bit tabanlı gerçekleştirir `EXCLUSIVE-OR` iki bit kümeleri arasında.  
  
```  
template <size_t size>  
bitset<size>  
operator^(
    const bitset<size>& left,  
    const bitset<size>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 İlgili öğeleri olan Bitsel ile birleştirilecek iki bit kümeleri ilk `EXCLUSIVE-OR`.  
  
 `right`  
 İlgili öğeleri olan Bitsel ile birleştirilecek iki valarrays ikinci `EXCLUSIVE-OR`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeleri olan sonucunu bitset `EXCLUSIVE-OR` karşılık gelen öğelerini işlemi `left` ve `right`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// bitset_xor.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
#include <string>  
  
using namespace std;  
  
int main()  
{  
   bitset<4> b1 ( string("0101") );  
   bitset<4> b2 ( string("0011") );  
   bitset<4> b3 = b1 ^ b2;  
   cout << "bitset 1: " << b1 << endl;  
   cout << "bitset 2: " << b2 << endl;  
   cout << "bitset 3: " << b3 << endl;  
}  
```  
  
```Output  
bitset 1: 0101  
bitset 2: 0011  
bitset 3: 0110  
```  
  
##  <a name="op_or"></a>operator |  
 Bit tabanlı gerçekleştirir `OR` iki bit kümeleri arasında.  
  
```  
template <size_t size>  
bitset<size>  
operator|(
    const bitset<size>& left,  
    const bitset<size>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 İlgili öğeleri olan Bitsel ile birleştirilecek iki bit kümeleri ilk `OR`.  
  
 `right`  
 İlgili öğeleri olan Bitsel ile birleştirilecek iki valarrays ikinci `OR`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğeleri olan sonucunu bitset `OR` karşılık gelen öğelerini işlemi `left` ve `right`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// bitset_or.cpp  
// compile with: /EHsc  
#include <bitset>  
#include <iostream>  
#include <string>  
  
using namespace std;  
  
int main()  
{  
   bitset<4> b1 ( string("0101") );  
   bitset<4> b2 ( string("0011") );  
   bitset<4> b3 = b1 | b2;  
   cout << "bitset 1: " << b1 << endl;  
   cout << "bitset 2: " << b2 << endl;  
   cout << "bitset 3: " << b3 << endl;  
}  
```  
  
```Output  
bitset 1: 0101  
bitset 2: 0011  
bitset 3: 0111  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<bitset >](../standard-library/bitset.md)

