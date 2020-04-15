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
ms.openlocfilehash: 3766a93d7cba9096ce3ff775d94c17a85456fb00
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363098"
---
# <a name="istream_iterator-class"></a>istream_iterator Sınıfı

Bir giriş yineleyici nesnesi tanımlar. `Type` Sınıf nesnelerini, `pointer` depoladığı `basic_istream` <  `CharType`bir nesne aracılığıyla erişerek `Traits`>.

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

*Türü*\
Çıkış akışından ayıklanacak nesnenin türü.

*Chartype*\
`istream_iterator`Için karakter türünü temsil eden tür. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer **char'** dır.

*Özellik*\
`istream_iterator`Için karakter türünü temsil eden tür. Bu bağımsız değişken isteğe `char_traits` <  `CharType` bağlıdır ve varsayılan değer>.

*Mesafe*\
`istream_iterator`Için fark türünü temsil eden imzalı bir integral türü. Bu bağımsız değişken isteğe `ptrdiff_t`bağlıdır ve varsayılan değer .

Sınıf istream_iterator bir nesnesini null depolanmış olmayan bir işaretçiyle oluşturma veya artış yaptıktan sonra, `Type` nesne ilişkili giriş akışından bir tür nesnesini ayıklayıp depolamaya çalışır. Ayıklama işlemi başarısız olursa, nesne etkili bir şekilde depolanan işaretçinin yerini alır, böylece bir dizi sonu gösterge oluşturur.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[istream_iterator](#istream_iterator)|Varsayılan `istream_iterator` olarak bir akış sonu yineleyici veya okuduğu yinelemenin akış türüne `istream_iterator` başharflefürün oluşturulmasını kolaylaştırır.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Char_type](#char_type)|`istream_iterator`Karakter türünü sağlayan bir tür.|
|[istream_type](#istream_type)|Akış türünü sağlayan bir `istream_iterator`tür.|
|[traits_type](#traits_type)|`istream_iterator`Karakter özellikleri türünü sağlayan bir tür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç*](#op_star)|Dereferencing işleci tarafından adreslenen `Type` tür depolanan `istream_iterator`nesne döndürür .|
|[operatör->](#op_arrow)|Varsa, bir üyenin değerini döndürür.|
|[işleç++](#op_add_add)|Giriş akışındaki artırılmış nesneyi ayıklar ya da artırmadan önce nesneyi kopyalar ve kopyayı döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<yineleyici>

**Ad alanı:** std

## <a name="istream_iteratorchar_type"></a><a name="char_type"></a>istream_iterator:char_type

`istream_iterator`Karakter türünü sağlayan bir tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `Chartype`ile eş anlamlıdır.

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

## <a name="istream_iteratoristream_iterator"></a><a name="istream_iterator"></a>istream_iterator:istream_iterator

Varsayılan `istream_iterator` olarak bir akış sonu yineleyici veya okuduğu yinelemenin akış türüne `istream_iterator` başharflefürün oluşturulmasını kolaylaştırır.

```cpp
istream_iterator();

istream_iterator(istream_type& _Istr);
```

### <a name="parameters"></a>Parametreler

*_Istr*\
Okunacak giriş akışı, `istream_iterator`'' harfini initialize etmek için kullanılır.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu, giriş akışı işaretçisini null işaretçiyle başolarak adlandırır ve akış sonu yineleyicisi oluşturur. İkinci oluşturucu giriş akışı işaretçisini *&_Istr*ile başharfe çıkarır, ardından `Type`türdeki bir nesneyi ayıklamayı ve depolamayı dener.

Akış sonu yineleyici, bir `istream_iterator` akışın sonuna ulaşıp ulaşmadığını test etmek için kullanılabilir.

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

## <a name="istream_iteratoristream_type"></a><a name="istream_type"></a>istream_iterator:istream_type

Akış türünü sağlayan bir `istream_iterator`tür.

```cpp
typedef basic_istream<CharType, Traits> istream_type;
```

### <a name="remarks"></a>Açıklamalar

Türü `basic_istream` \< **CharType**için eşanlamlıdır , **Özellikler**>.

### <a name="example"></a>Örnek

Nasıl [istream_iterator](#istream_iterator) bildirilir ve kullanılacağına `istream_type`ilgili bir örnek için istream_iterator bakın.

## <a name="istream_iteratoroperator"></a><a name="op_star"></a>istream_iterator::operatör*

Dereferencing işleci tarafından adreslenen `Type` tür depolanan `istream_iterator`nesne döndürür .

```cpp
const Type& operator*() const;
```

### <a name="return-value"></a>Dönüş Değeri

Türünde depolanan `Type`nesne.

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

## <a name="istream_iteratoroperator-gt"></a><a name="op_arrow"></a>istream_iterator::operatör-&gt;

Varsa, bir üyenin değerini döndürür.

```cpp
const Type* operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

Varsa bir üyenin değeri.

### <a name="remarks"></a>Açıklamalar

`i->m`eşdeğerdir`(*i).m`

Operatör döndürür. `&*this`

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

## <a name="istream_iteratoroperator"></a><a name="op_add_add"></a>istream_iterator::operator++

Giriş akışındaki artırılmış nesneyi ayıklar ya da artırmadan önce nesneyi kopyalar ve kopyayı döndürür.

```cpp
istream_iterator<Type, CharType, Traits, Distance>& operator++();

istream_iterator<Type, CharType, Traits, Distance> operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk üye işleç, giriş akışından çıkarılan türdeki `Type` artışlı nesneye bir başvuru döndürür ve ikinci üye işlev nesnenin bir kopyasını döndürür.

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

## <a name="istream_iteratortraits_type"></a><a name="traits_type"></a>istream_iterator:traits_type

`istream_iterator`Karakter özellikleri türünü sağlayan bir tür.

```cpp
typedef Traits traits_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi *Özellikleri*ile eş anlamlıdır.

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

[input_iterator_tag Yapı](../standard-library/input-iterator-tag-struct.md)\
[iterator Yapıt](../standard-library/iterator-struct.md)\
[\<iterator>](../standard-library/iterator.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kütüphane Başvurusu](../standard-library/cpp-standard-library-reference.md)
