---
title: "&lt;ayarlama&gt; işleçleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- set/std::operator!=
- set/std::operator&gt;
- set/std::operator&gt;=
- set/std::operator&lt;
- set/std::operator&lt;=
- set/std::operator==
dev_langs:
- C++
ms.assetid: b4256ebc-c449-4688-95db-fced42d20d4d
caps.latest.revision: 
manager: ghogen
helpviewer_keywords:
- std::operator!= (set)
- std::operator&gt; (set)
- std::operator&gt;= (set)
- std::operator&lt; (set)
- std::operator&lt;= (set)
- std::operator== (set)
ms.openlocfilehash: d5058b75af8b26b6e7ddc9a8a7b487b0cd8b8e91
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ltsetgt-operators"></a>&lt;ayarlama&gt; işleçleri
||||  
|-|-|-|  
|[operator! = (set)](#op_neq)|[İşleç&gt; (ayarlayın)](#op_gt)|[İşleç&gt;= (set)](#eq)|  
|[İşleç&lt; (ayarlayın)](#op_lt)|[İşleç&lt;= (set)](#eq)|[operator == (set)](#op_eq_eq)|  
|[operator! = (multiset)](#op_neq_multiset)|[İşleç&gt; (multiset)](#op_gt_multiset)|[İşleç&gt;= (multiset)](#op_gt_eq_multiset)|  
|[İşleç&lt; (multiset)](#op_lt_multiset)|[İşleç&lt;= (multiset)](#op_lt_eq_multiset)|[operator == (multiset)](#op_eq_eq_multiset)|  
  
##  <a name="op_neq">operator! = (set)</a>  
 Testleri kümesi nesnesi işlecinin sol tarafındaki sağ tarafında kümesi nesnesine eşit değil.  
  
```
bool operator!=(const set <Key, Traits, Allocator>& left, const set <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 Türünde bir nesne **ayarlamak**.  
  
 `right`  
 Türünde bir nesne **ayarlamak**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** kümeleri eşit; değilse **false** kümeleri eşit olması durumunda.  
  
### <a name="remarks"></a>Açıklamalar  
 Kümesi nesnelerini karşılaştırması öğeleri arasında ikili karşılaştırma temel alır. İki kümenin aynı sayıda öğe varsa ve bunların ilgili öğeleri aynı değerlere eşit. Aksi takdirde, bunlar eşit.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// set_op_ne.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   set <int> s1, s2, s3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i );  
   }  
  
   if ( s1 != s2 )  
      cout << "The sets s1 and s2 are not equal." << endl;  
   else  
      cout << "The sets s1 and s2 are equal." << endl;  
  
   if ( s1 != s3 )  
      cout << "The sets s1 and s3 are not equal." << endl;  
   else  
      cout << "The sets s1 and s3 are equal." << endl;  
}  
\* Output:   
The sets s1 and s2 are not equal.  
The sets s1 and s3 are equal.  
*\  
```  
  
##  <a name="op_lt"></a>  İşleç&lt; (ayarlayın)  
 Testleri kümesi nesnesi işlecinin sol tarafındaki kümesi nesnesi sağ tarafındaki'dan küçük.  
  
```
bool operator<(const set <Key, Traits, Allocator>& left, const set <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 Türünde bir nesne **ayarlamak**.  
  
 `right`  
 Türünde bir nesne **ayarlamak**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** işlecinin sol tarafındaki; işlecinin sağ tarafında kümesi kesinlikle değerinden ayarlanırsa aksi **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Kümesi nesnelerini karşılaştırması öğelerini pairwise karşılaştırması hakkında temel alır. Küçüktür-iki nesne arasındaki ilişki ilk çiftlerini eşit olmayan bir karşılaştırmasını alan daha.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// set_op_lt.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   set <int> s1, s2, s3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i - 1 );  
   }  
  
   if ( s1 < s2 )  
      cout << "The set s1 is less than the set s2." << endl;  
   else  
      cout << "The set s1 is not less than the set s2." << endl;  
  
   if ( s1 < s3 )  
      cout << "The set s1 is less than the set s3." << endl;  
   else  
      cout << "The set s1 is not less than the set s3." << endl;  
}  
\* Output:   
The set s1 is less than the set s2.  
The set s1 is not less than the set s3.  
*\  
```  
  
##  <a name="op_lt_eq"></a>  İşleç&lt;= (set)  
 Belirlenen işlecinin sol tarafında nesne sağlayıp sağlamadığını test sağ tarafında kümesi nesnesi eşit veya daha az olur.  
  
```
bool operator!<=(const set <Key, Traits, Allocator>& left, const set <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 Türünde bir nesne **ayarlamak**.  
  
 `right`  
 Türünde bir nesne **ayarlamak**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** işlecinin sol tarafındaki kümesi veya işlecinin sağ tarafında kümesine eşit; Aksi takdirde düşükse **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Kümesi nesnelerini karşılaştırması öğelerini pairwise karşılaştırması hakkında temel alır. İki nesne arasındaki ilişki için küçük veya eşittir ilk çiftlerini eşit olmayan bir karşılaştırmasını temel alır.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// set_op_le.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   set <int> s1, s2, s3, s4;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i - 1 );  
      s4.insert ( i );  
   }  
  
   if ( s1 <= s2 )  
      cout << "Set s1 is less than or equal to the set s2." << endl;  
   else  
      cout << "The set s1 is greater than the set s2." << endl;  
  
   if ( s1 <= s3 )  
      cout << "Set s1 is less than or equal to the set s3." << endl;  
   else  
      cout << "The set s1 is greater than the set s3." << endl;  
  
   if ( s1 <= s4 )  
      cout << "Set s1 is less than or equal to the set s4." << endl;  
   else  
      cout << "The set s1 is greater than the set s4." << endl;  
}  
\* Output:   
Set s1 is less than or equal to the set s2.  
The set s1 is greater than the set s3.  
Set s1 is less than or equal to the set s4.  
*\  
```  
  
##  <a name="op_eq_eq">operator == (set)</a>  
 Sağ taraftaki kümesi nesnesi işlecinin sol tarafındaki kümesi nesnesi eşitse testleri.  
  
```
bool operator!==(const set <Key, Traits, Allocator>& left, const set <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 Türünde bir nesne **ayarlamak**.  
  
 `right`  
 Türünde bir nesne **ayarlamak**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** işlecinin sol tarafındaki ayarlanırsa işlecinin sağ tarafında kümesine eşit; Aksi takdirde **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Kümesi nesnelerini karşılaştırması öğelerini pairwise karşılaştırması hakkında temel alır. İki kümenin aynı sayıda öğe varsa ve bunların ilgili öğeleri aynı değerlere eşit. Aksi takdirde, bunlar eşit.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// set_op_eq.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   set <int> s1, s2, s3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i );  
   }  
  
   if ( s1 == s2 )  
      cout << "The sets s1 and s2 are equal." << endl;  
   else  
      cout << "The sets s1 and s2 are not equal." << endl;  
  
   if ( s1 == s3 )  
      cout << "The sets s1 and s3 are equal." << endl;  
   else  
      cout << "The sets s1 and s3 are not equal." << endl;  
}  
\* Output:   
The sets s1 and s2 are not equal.  
The sets s1 and s3 are equal.  
*\  
```  
  
##  <a name="op_gt"></a>  İşleç&gt; (ayarlayın)  
 Testleri kümesi nesnesi işlecinin sol tarafındaki sağ tarafında kümesi nesnesi değerinden daha büyük.  
  
```
bool operator>(const set <Key, Traits, Allocator>& left, const set <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 Türünde bir nesne **ayarlamak**.  
  
 `right`  
 Türünde bir nesne **ayarlamak**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** işlecinin sol tarafındaki ayarlanırsa işlecinin sağ tarafında kümesi büyük; Aksi takdirde **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Kümesi nesnelerini karşılaştırması öğelerini pairwise karşılaştırması hakkında temel alır. Büyük-iki nesne arasındaki ilişki ilk çiftlerini eşit olmayan bir karşılaştırmasını alan daha.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// set_op_gt.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   set <int> s1, s2, s3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i - 1 );  
   }  
  
   if ( s1 > s2 )  
      cout << "The set s1 is greater than the set s2." << endl;  
   else  
      cout << "The set s1 is not greater than the set s2." << endl;  
  
   if ( s1 > s3 )  
      cout << "The set s1 is greater than the set s3." << endl;  
   else  
      cout << "The set s1 is not greater than the set s3." << endl;  
}  
\* Output:   
The set s1 is not greater than the set s2.  
The set s1 is greater than the set s3.  
*\  
```  
  
##  <a name="op_gt_eq"></a>  İşleç&gt;= (set)  
 Testleri kümesi nesnesi işlecinin sol tarafındaki sağ tarafında kümesi nesnesi eşit veya daha büyük.  
  
```
bool operator!>=(const set <Key, Traits, Allocator>& left, const set <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 Türünde bir nesne **ayarlamak**.  
  
 `right`  
 Türünde bir nesne **ayarlamak**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** işlecinin sol tarafındaki ayarlanırsa büyük veya eşit listesinin sağ taraftaki kümesine; tersi durumda **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Kümesi nesnelerini karşılaştırması öğelerini pairwise karşılaştırması hakkında temel alır. Büyük veya ona eşit iki nesne arasındaki ilişki için ilk çiftlerini eşit olmayan bir karşılaştırmasını temel alır.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// set_op_ge.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   set <int> s1, s2, s3, s4;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i - 1 );  
      s4.insert ( i );  
   }  
  
   if ( s1 >= s2 )  
      cout << "Set s1 is greater than or equal to set s2." << endl;  
   else  
      cout << "The set s1 is less than the set s2." << endl;  
  
   if ( s1 >= s3 )  
      cout << "Set s1 is greater than or equal to set s3." << endl;  
   else  
      cout << "The set s1 is less than the set s3." << endl;  
  
   if ( s1 >= s4 )  
      cout << "Set s1 is greater than or equal to set s4." << endl;  
   else  
      cout << "The set s1 is less than the set s4." << endl;  
}  
\* Output:   
The set s1 is less than the set s2.  
Set s1 is greater than or equal to set s3.  
Set s1 is greater than or equal to set s4.  
*\  
```  
  
##  <a name="op_neq_multiset">operator! = (multiset)</a>  
 Çok kümeli nesne işlecinin sol tarafındaki sağ tarafında multiset nesne eşit değilse testleri.  
  
```
bool operator!=(const multiset <Key, Traits, Allocator>& left, const multiset <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 Türünde bir nesne `multiset`.  
  
 `right`  
 Türünde bir nesne `multiset`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** kümeleri veya multisets eşit; değilse **false** kümeleri veya multisets eşit olması durumunda.  
  
### <a name="remarks"></a>Açıklamalar  
 Çok kümeli nesneler arasındaki karşılaştırmayı ikili karşılaştırma kendi öğeler arasında temel alır. İki kümeleri veya multisets aynı sayıda öğe varsa ve bunların ilgili öğeleri aynı değerlere eşittir. Aksi takdirde, bunlar eşit.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_op_ne.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multiset <int> s1, s2, s3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i );  
   }  
  
   if ( s1 != s2 )  
      cout << "The multisets s1 and s2 are not equal." << endl;  
   else  
      cout << "The multisets s1 and s2 are equal." << endl;  
  
   if ( s1 != s3 )  
      cout << "The multisets s1 and s3 are not equal." << endl;  
   else  
      cout << "The multisets s1 and s3 are equal." << endl;  
}  
\* Output:   
The multisets s1 and s2 are not equal.  
The multisets s1 and s3 are equal.  
*\  
```  
  
##  <a name="op_lt_multiset"></a>  İşleç&lt; (multiset)  
 Çok kümeli nesne işlecinin sol tarafındaki sağ tarafında multiset nesne küçükse testleri.  
  
```
bool operator<(const multiset <Key, Traits, Allocator>& left, const multiset <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 Türünde bir nesne `multiset`.  
  
 `right`  
 Türünde bir nesne `multiset`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** işlecinin sol tarafındaki multiset; işlecinin sağ tarafında multiset kesinlikle değerinden ise, aksi takdirde **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Çok kümeli nesneler arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. Küçüktür-iki nesne arasındaki ilişki ilk çiftlerini eşit olmayan bir karşılaştırmasını alan daha.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_op_lt.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multiset <int> s1, s2, s3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i - 1 );  
   }  
  
   if ( s1 < s2 )  
      cout << "The multiset s1 is less than "  
           << "the multiset s2." << endl;  
   else  
      cout << "The multiset s1 is not less than "  
           << "the multiset s2." << endl;  
  
   if ( s1 < s3 )  
      cout << "The multiset s1 is less than "  
           << "the multiset s3." << endl;  
   else  
      cout << "The multiset s1 is not less than "  
           << "the multiset s3." << endl;  
}  
\* Output:   
The multiset s1 is less than the multiset s2.  
The multiset s1 is not less than the multiset s3.  
*\  
```  
  
##  <a name="op_lt_eq_multiset"></a>  İşleç&lt;= (multiset)  
 Multiset işlecinin sol tarafında nesne sağlayıp sağlamadığını test sağ tarafında multiset nesnesine eşit veya daha az olur.  
  
```
bool operator!<=(const multiset <Key, Traits, Allocator>& left, const multiset <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 Türünde bir nesne `multiset`.  
  
 `right`  
 Türünde bir nesne `multiset`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** işlecinin sol tarafındaki multiset veya multiset işlecinin sağ tarafında eşit; Aksi takdirde düşükse **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Çok kümeli nesneler arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. İki nesne arasındaki ilişki için küçük veya eşittir ilk çiftlerini eşit olmayan bir karşılaştırmasını temel alır.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_op_le.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multiset <int> s1, s2, s3, s4;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i - 1 );  
      s4.insert ( i );  
   }  
  
   if ( s1 <= s2 )  
      cout << "The multiset s1 is less than "  
           << "or equal to the multiset s2." << endl;  
   else  
      cout << "The multiset s1 is greater than "  
           << "the multiset s2." << endl;  
  
   if ( s1 <= s3 )  
      cout << "The multiset s1 is less than "  
           << "or equal to the multiset s3." << endl;  
   else  
      cout << "The multiset s1 is greater than "  
           << "the multiset s3." << endl;  
  
   if ( s1 <= s4 )  
      cout << "The multiset s1 is less than "  
           << "or equal to the multiset s4." << endl;  
   else  
      cout << "The multiset s1 is greater than "  
           << "the multiset s4." << endl;  
}  
\* Output:   
The multiset s1 is less than or equal to the multiset s2.  
The multiset s1 is greater than the multiset s3.  
The multiset s1 is less than or equal to the multiset s4.  
*\  
```  
  
##  <a name="op_eq_eq_multiset">operator == (multiset)</a>  
 Çok kümeli nesnesine sağ tarafında işlecinin sol tarafındaki multiset nesne eşitse testleri.  
  
```
bool operator!==(const multiset <Key, Traits, Allocator>& left, const multiset <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 Türünde bir nesne `multiset`.  
  
 `right`  
 Türünde bir nesne `multiset`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** multiset işlecinin sol tarafındaki işlecinin sağ tarafında multiset eşit; tersi durumda ise **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Çok kümeli nesneler arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. İki kümeleri veya multisets aynı sayıda öğe varsa ve bunların ilgili öğeleri aynı değerlere eşittir. Aksi takdirde, bunlar eşit.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_op_eq.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multiset <int> s1, s2, s3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i );  
   }  
  
   if ( s1 == s2 )  
      cout << "The multisets s1 and s2 are equal." << endl;  
   else  
      cout << "The multisets s1 and s2 are not equal." << endl;  
  
   if ( s1 == s3 )  
      cout << "The multisets s1 and s3 are equal." << endl;  
   else  
      cout << "The multisets s1 and s3 are not equal." << endl;  
}  
\* Output:   
The multisets s1 and s2 are not equal.  
The multisets s1 and s3 are equal.  
*\  
```  
  
##  <a name="op_gt_multiset"></a>  İşleç&gt; (multiset)  
 Çok kümeli nesne işlecinin sol tarafındaki sağ tarafında multiset nesne büyükse testleri.  
  
```
bool operator>(const multiset <Key, Traits, Allocator>& left, const multiset <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 Türünde bir nesne `multiset`.  
  
 `right`  
 Türünde bir nesne `multiset`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** multiset işlecinin sol tarafındaki işlecinin sağ tarafında multiset büyük; tersi durumda ise **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Çok kümeli nesneler arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. Büyük-iki nesne arasındaki ilişki ilk çiftlerini eşit olmayan bir karşılaştırmasını alan daha.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_op_gt.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multiset <int> s1, s2, s3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i - 1 );  
   }  
  
   if ( s1 > s2 )  
      cout << "The multiset s1 is greater than "  
           << "the multiset s2." << endl;  
   else  
      cout << "The multiset s1 is not greater "  
           << "than the multiset s2." << endl;  
  
   if ( s1 > s3 )  
      cout << "The multiset s1 is greater than "  
           << "the multiset s3." << endl;  
   else  
      cout << "The multiset s1 is not greater than "  
           << "the multiset s3." << endl;  
}  
\* Output:   
The multiset s1 is not greater than the multiset s2.  
The multiset s1 is greater than the multiset s3.  
*\  
```  
  
##  <a name="op_gt_eq_multiset"></a>  İşleç&gt;= (multiset)  
 Çok kümeli nesne işlecinin sol tarafındaki değerinden büyük veya çok kümeli nesnesine sağ tarafında eşit ise testleri.  
  
```
bool operator!>=(const multiset <Key, Traits, Allocator>& left, const multiset <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `left`  
 Türünde bir nesne `multiset`.  
  
 `right`  
 Türünde bir nesne `multiset`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **doğru** işlecinin sol tarafındaki multiset büyüktür veya listesinin sağ taraftaki multiset eşit; tersi durumda ise **false**.  
  
### <a name="remarks"></a>Açıklamalar  
 Çok kümeli nesneler arasındaki karşılaştırma öğelerini pairwise karşılaştırması hakkında temel alır. Büyük veya ona eşit iki nesne arasındaki ilişki için ilk çiftlerini eşit olmayan bir karşılaştırmasını temel alır.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// multiset_op_ge.cpp  
// compile with: /EHsc  
#include <set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   multiset <int> s1, s2, s3, s4;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i - 1 );  
      s4.insert ( i );  
   }  
  
   if ( s1 >= s2 )  
      cout << "The multiset s1 is greater than "  
           << "or equal to the multiset s2." << endl;  
   else  
      cout << "The multiset s1 is less than "  
           << "the multiset s2." << endl;  
  
   if ( s1 >= s3 )  
      cout << "The multiset s1 is greater than "  
           << "or equal to the multiset s3." << endl;  
   else  
      cout << "The multiset s1 is less than "  
           << "the multiset s3." << endl;  
  
   if ( s1 >= s4 )  
      cout << "The multiset s1 is greater than "  
           << "or equal to the multiset s4." << endl;  
   else  
      cout << "The multiset s1 is less than "  
           << "the multiset s4." << endl;  
}  
\* Output:   
The multiset s1 is less than the multiset s2.  
The multiset s1 is greater than or equal to the multiset s3.  
The multiset s1 is greater than or equal to the multiset s4.  
*\  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<Ayarlama >](../standard-library/set.md)



