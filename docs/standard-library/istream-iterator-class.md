---
title: istream_iterator Sınıfı
ms.date: 11/04/2016
f1_keywords:
- iterator/std::istream_iterator
- iterator/std::istream_iterator::char_type
- iterator/std::istream_iterator::istream_type
- iterator/std::istream_iterator::traits_type
helpviewer_keywords:
- std::istream_iterator [C++]
- std::istream_iterator [C++], char_type
- std::istream_iterator [C++], istream_type
- std::istream_iterator [C++], traits_type
ms.assetid: fb52a8cd-7f71-48d1-b73e-4b064e2a8d16
ms.openlocfilehash: 941d625e388edc75dfe25a2de0e609c6d955ff19
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447752"
---
# <a name="istreamiterator-class"></a>istream_iterator Sınıfı

Bir giriş yineleyici nesnesi tanımlar. `Type` Bir giriş akışından sınıfının nesnelerini ayıklar ve bu, `basic_istream` <  `CharType`türü `pointer` `Traits`, > olan bir nesneden erişir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type, class CharType = char, class Traits = char_traits<CharType>, class Distance = ptrdiff_t,>
class istream_iterator
: public iterator<
    input_iterator_tag, Type, Distance,
    const Type *,
    const Type&>;
```

### <a name="parameters"></a>Parametreler

*Türüyle*\
Çıkış akışından ayıklanacak nesnenin türü.

*CharType*\
İçin karakter türünü temsil eden tür `istream_iterator`. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer **char**' dır.

*Lerdir*\
İçin karakter türünü temsil eden tür `istream_iterator`. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `char_traits` <  `CharType`>.

*Uzaklık*\
İçin fark türünü temsil eden imzalı bir integral türü `istream_iterator`. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değerdir `ptrdiff_t`.

Null olmayan bir saklı işaretçiyle istream_iterator sınıfının bir nesnesini oluşturduktan veya artırdıktan sonra, nesnesi ilişkili giriş akışından türünde `Type` bir nesne ayıklamaya ve depolamaya çalışır. Ayıklama işlemi başarısız olursa, nesne etkili bir şekilde depolanan işaretçinin yerini alır, böylece bir dizi sonu gösterge oluşturur.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[istream_iterator](#istream_iterator)|Varsayılan olarak bir akış sonu yineleyicisi veya tarafından okunan Yineleyici akış `istream_iterator` türü için `istream_iterator` başlatılmış bir değer oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Öğesinin karakter türü için sağlayan bir tür `istream_iterator`.|
|[istream_type](#istream_type)|Akış türü `istream_iterator`için sağlayan bir tür.|
|[traits_type](#traits_type)|Öğesinin karakter nitelikleri türü için sağlayan bir tür `istream_iterator`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işlecinde](#op_star)|Başvuru kaldırma işleci, `Type` `istream_iterator`tarafından bahsedilen saklanan nesne türünü döndürür.|
|[operator->](#op_arrow)|Varsa, bir üyenin değerini döndürür.|
|[işleç + +](#op_add_add)|Giriş akışındaki artırılmış nesneyi ayıklar ya da artırmadan önce nesneyi kopyalar ve kopyayı döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<Yineleyici >

**Ad alanı:** std

## <a name="char_type"></a>istream_iterator::char_type

Öğesinin karakter türü için sağlayan bir tür `istream_iterator`.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `Chartype`için bir eş anlamlı.

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

## <a name="istream_iterator"></a>istream_iterator::istream_iterator

Varsayılan olarak bir akış sonu yineleyicisi veya tarafından okunan Yineleyici akış `istream_iterator` türü için `istream_iterator` başlatılmış bir değer oluşturur.

```cpp
istream_iterator();

istream_iterator(istream_type& _Istr);
```

### <a name="parameters"></a>Parametreler

*_Istr*\
Öğesini başlatmak `istream_iterator`için kullanılacak giriş akışı.

### <a name="remarks"></a>Açıklamalar

Ilk Oluşturucu, giriş akışı işaretçisini null işaretçiyle başlatır ve akış sonu Yineleyici oluşturur. İkinci Oluşturucu, giriş akışı işaretçisini *& _Istr*ile başlatır, ardından türünde `Type`bir nesne ayıklamaya ve depolamaya çalışır.

Akış sonu yineleyicisi, bir `istream_iterator` akışın sonuna ulaşıp ulaşılmadığını test etmek için kullanılabilir.

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

## <a name="istream_type"></a>istream_iterator::istream_type

Akış türü `istream_iterator`için sağlayan bir tür.

```cpp
typedef basic_istream<CharType, Traits> istream_type;
```

### <a name="remarks"></a>Açıklamalar

`basic_istream` Tür, **CharType**, **nitelikler**> için \< bir eş anlamlı.

### <a name="example"></a>Örnek

Bildirme [](#istream_iterator) ve kullanma `istream_type`hakkında bir örnek için bkz. istream_iterator.

## <a name="op_star"></a>istream_iterator:: operator *

Başvuru kaldırma işleci, `Type` `istream_iterator`tarafından bahsedilen saklanan nesne türünü döndürür.

```cpp
const Type& operator*() const;
```

### <a name="return-value"></a>Dönüş Değeri

Türündeki `Type`saklı nesne.

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

## <a name="op_arrow"></a>istream_iterator:: operator-&gt;

Varsa, bir üyenin değerini döndürür.

```cpp
const Type* operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir üyenin değeri (varsa).

### <a name="remarks"></a>Açıklamalar

`i->m`eşdeğerdir`(*i).m`

İşleci döndürülür `&*this`.

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

## <a name="op_add_add"></a>  istream_iterator::operator++

Giriş akışındaki artırılmış nesneyi ayıklar ya da artırmadan önce nesneyi kopyalar ve kopyayı döndürür.

```cpp
istream_iterator<Type, CharType, Traits, Distance>& operator++();

istream_iterator<Type, CharType, Traits, Distance> operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk üye işleci, giriş akışından ayıklanan türün `Type` artılan nesnesine bir başvuru döndürür ve ikinci üye işlevi nesnenin bir kopyasını döndürür.

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

## <a name="traits_type"></a>istream_iterator::traits_type

Öğesinin karakter nitelikleri türü için sağlayan bir tür `istream_iterator`.

```cpp
typedef Traits traits_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi *nitelikleri*için bir eş anlamlı.

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

## <a name="see-also"></a>Ayrıca bkz.

[input_iterator_tag yapısı](../standard-library/input-iterator-tag-struct.md)\
[Yineleyici yapısı](../standard-library/iterator-struct.md)\
[\<Yineleyici >](../standard-library/iterator.md)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
