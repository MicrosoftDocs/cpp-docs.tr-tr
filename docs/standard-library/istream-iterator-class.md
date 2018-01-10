---
title: "istream_iterator sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iterator/std::istream_iterator
- iterator/std::istream_iterator::char_type
- iterator/std::istream_iterator::istream_type
- iterator/std::istream_iterator::traits_type
dev_langs: C++
helpviewer_keywords:
- std::istream_iterator [C++]
- std::istream_iterator [C++], char_type
- std::istream_iterator [C++], istream_type
- std::istream_iterator [C++], traits_type
ms.assetid: fb52a8cd-7f71-48d1-b73e-4b064e2a8d16
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ef5ba7c445325131ad620efcbb6061a0fa49039a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="istreamiterator-class"></a>istream_iterator Sınıfı
Bir giriş yineleyici nesnesi tanımlar. Sınıfın nesnelerini ayıklar `Type` bir giriş akışından hangi BT bir nesne türü depoları eriştiği `pointer` için `basic_istream` <  `CharType`, `Traits`>.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class Type, class CharType = char, class Traits = char_traits<CharType>, class Distance = ptrdiff_t,>  
class istream_iterator
 : public iterator<
    input_iterator_tag, Type, Distance,
    const Type *,
    const Type&>;
```  
  
#### <a name="parameters"></a>Parametreler  
 `Type`  
 Çıkış akışından ayıklanacak nesnenin türü.  
  
 `CharType`  
 Karakter türünü temsil eden tür `istream_iterator`. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `char`.  
  
 `Traits`  
 Karakter türünü temsil eden tür `istream_iterator`. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `char_traits` <  `CharType`>.  
  
 `Distance`  
 Bir oturum için fark türünü temsil eden tamsayı türü `istream_iterator`. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `ptrdiff_t`.  
  
 Oluşturma veya NULL olmayan saklı işaretçiyle sınıfı istream_iterator nesnenin artırma sonra ayıklamak ve türünde bir nesne depolamak nesne çalışır `Type` ilişkili giriş akışından. Ayıklama işlemi başarısız olursa, nesne etkili bir şekilde depolanan işaretçinin yerini alır, böylece bir dizi sonu gösterge oluşturur.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[istream_iterator](#istream_iterator)|Varsayılan olarak bir akış uç yineleyici yapıları `istream_iterator` veya `istream_iterator` yineleyici'nın akış türü için hangi okur başlatıldı.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[char_type](#char_type)|Karakter türü için sağlayan bir türü `istream_iterator`.|  
|[istream_type](#istream_type)|Akış türü için sağlayan bir türü `istream_iterator`.|  
|[traits_type](#traits_type)|Karakter nitelikler tür sağlayan bir tür `istream_iterator`.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleç *](#op_star)|Saklı nesne türünün bilgileri başvuru kaldırma işleci döndürür `Type` tarafından ele `istream_iterator`.|  
|[-> işleci](#operator-_gt)|Varsa, bir üyenin değerini döndürür.|  
|[operator ++](#op_add_add)|Giriş akışındaki artırılmış nesneyi ayıklar ya da artırmadan önce nesneyi kopyalar ve kopyayı döndürür.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<yineleyici >  
  
 **Namespace:** std  
  
##  <a name="char_type"></a>istream_iterator::char_type  
 Karakter türü için sağlayan bir türü `istream_iterator`.  
  
```
typedef CharType char_type;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür **Chartype**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// istream_iterator_char_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef istream_iterator<int>::char_type CHT1;  
   typedef istream_iterator<int>::traits_type CHTR1;  
  
   // Standard iterator interface for reading  
   // elements from the input stream:  
   cout << "Enter integers separated by spaces & then\n"  
        << " any character ( try example: '2 4 f' ): ";  
  
   // istream_iterator for reading int stream  
   istream_iterator<int, CHT1, CHTR1> intRead ( cin );  
  
   // End-of-stream iterator  
   istream_iterator<int, CHT1, CHTR1> EOFintRead;  
  
   while ( intRead != EOFintRead )  
   {  
      cout << "Reading:  " << *intRead << endl;  
      ++intRead;  
   }  
   cout << endl;  
}  
```  
  
##  <a name="istream_iterator"></a>istream_iterator::istream_iterator  
 Varsayılan olarak bir akış uç yineleyici yapıları `istream_iterator` veya `istream_iterator` yineleyici'nın akış türü için hangi okur başlatıldı.  
  
```
istream_iterator();

istream_iterator(istream_type& _Istr);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Istr`  
 Kullanım okumak için giriş akışı başlatmak için `istream_iterator`.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk Oluşturucusu null işaretçi Giriş akışı işaretçiyle başlatır ve akış uç yineleyici oluşturur. Giriş akışı işaretçisi ile ikinci oluşturucu başlatır *& _Istr*, ayıklayın ve türünde bir nesne depolamak denemeleri **türü**.  
  
 Akış uç Yineleyici, test etmek için kullanılabilir olup olmadığını bir `istream_iterator` bir akışın sonuna ulaştı.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// istream_iterator_istream_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <algorithm>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Used in conjunction with copy algorithm  
   // to put elements into a vector read from cin  
   vector<int> vec ( 4 );  
   vector <int>::iterator Iter;  
  
   cout << "Enter 4 integers separated by spaces & then\n"  
        << " a character ( try example: '2 4 6 8 a' ): ";  
   istream_iterator<int> intvecRead ( cin );  
  
   // Default constructor will test equal to end of stream  
   // for delimiting source range of vecor  
   copy ( intvecRead , istream_iterator<int>( ) , vec.begin ( ) );  
   cin.clear ( );  
  
   cout << "vec = ";  
   for ( Iter = vec.begin( ) ; Iter != vec.end( ) ; Iter++ )  
      cout << *Iter << " "; cout << endl;  
}  
```  
  
##  <a name="istream_type"></a>istream_iterator::istream_type  
 Akış türü için sağlayan bir türü `istream_iterator`.  
  
```
typedef basic_istream<CharType, Traits> istream_type;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Eşanlamlısı türüdür `basic_istream` \< **CharType**, **nitelikler**>.  
  
### <a name="example"></a>Örnek  
  Bkz: [istream_iterator](#istream_iterator) bildirme ve kullanma konusunda bir örnek için `istream_type`.  
  
##  <a name="op_star"></a>istream_iterator::operator *  
 Saklı nesne türünün bilgileri başvuru kaldırma işleci döndürür **türü** tarafından ele `istream_iterator`.  
  
```
const Type& operator*() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Saklı nesne türünün **türü**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// istream_iterator_operator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <algorithm>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   cout << "Enter integers separated by spaces & then\n"  
        << " a character ( try example: '2 4 6 8 a' ): ";  
  
   // istream_iterator from stream cin  
   istream_iterator<int> intRead ( cin );  
  
   // End-of-stream iterator  
   istream_iterator<int> EOFintRead;  
  
   while ( intRead != EOFintRead )  
   {  
      cout << "Reading:  " << *intRead << endl;  
      ++intRead;  
   }  
   cout << endl;  
}  
```  
  
##  <a name="istream_iterator__operator-_gt"></a>istream_iterator::operator-&gt;  
 Varsa, bir üyenin değerini döndürür.  
  
```
const Type* operator->() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Herhangi bir üye değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 *ı* -> eşdeğerdir (\* *ı*). *m*  
  
 İşleç döndürür  **& \* \*bu**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// istream_iterator_operator_vm.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>  
#include <complex>  
  
using namespace std;  
  
int main( )  
{  
   cout << "Enter complex numbers separated by spaces & then\n"  
        << " a character pair ( try example: '(1,2) (3,4) (a,b)' ): ";  
  
   // istream_iterator from stream cin  
   istream_iterator< complex<double> > intRead ( cin );  
  
   // End-of-stream iterator  
   istream_iterator<complex<double> > EOFintRead;  
  
   while ( intRead != EOFintRead )  
   {  
      cout << "Reading the real part: " << intRead ->real( ) << endl;  
      cout << "Reading the imaginary part: " << intRead ->imag( ) << endl;  
      ++intRead;  
   }  
   cout << endl;  
}  
```  
  
##  <a name="op_add_add"></a>istream_iterator::operator ++  
 Giriş akışındaki artırılmış nesneyi ayıklar ya da artırmadan önce nesneyi kopyalar ve kopyayı döndürür.  
  
```
istream_iterator<Type, CharType, Traits, Distance>& operator++();

istream_iterator<Type, CharType, Traits, Distance> operator++(int);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk üye işleci artırılır nesne türünün referansı döndürür **türü** ayıklanan Giriş akışı ve nesne kopyasını ikinci üye işlevi döndürür.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// istream_iterator_operator_incr.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <algorithm>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   cout << "Enter integers separated by spaces & then\n"  
        << " a character ( try example: '2 4 6 8 a' ): ";  
  
   // istream_iterator from stream cin  
   istream_iterator<int> intRead ( cin );  
  
   // End-of-stream iterator  
   istream_iterator<int> EOFintRead;  
  
   while ( intRead != EOFintRead )  
   {  
      cout << "Reading:  " << *intRead << endl;  
      ++intRead;  
   }  
   cout << endl;  
}  
```  
  
##  <a name="traits_type"></a>istream_iterator::traits_type  
 Karakter nitelikler tür sağlayan bir tür `istream_iterator`.  
  
```
typedef Traits traits_type;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür **nitelikler**.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// istream_iterator_traits_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef istream_iterator<int>::char_type CHT1;  
   typedef istream_iterator<int>::traits_type CHTR1;  
  
   // Standard iterator interface for reading  
   // elements from the input stream:  
   cout << "Enter integers separated by spaces & then\n"  
        << " any character ( try example: '10 20 a' ): ";  
  
   // istream_iterator for reading int stream  
   istream_iterator<int, CHT1, CHTR1> intRead ( cin );  
  
   // End-of-stream iterator  
   istream_iterator<int, CHT1, CHTR1> EOFintRead;  
  
   while ( intRead != EOFintRead )  
   {  
      cout << "Reading:  " << *intRead << endl;  
      ++intRead;  
   }  
   cout << endl;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [input_iterator_tag yapısı](../standard-library/input-iterator-tag-struct.md)   
 [iterator yapısı](../standard-library/iterator-struct.md)   
 [\<Yineleyici >](../standard-library/iterator.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)



