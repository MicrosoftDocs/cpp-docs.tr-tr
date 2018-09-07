---
title: istream_iterator sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- iterator/std::istream_iterator
- iterator/std::istream_iterator::char_type
- iterator/std::istream_iterator::istream_type
- iterator/std::istream_iterator::traits_type
dev_langs:
- C++
helpviewer_keywords:
- std::istream_iterator [C++]
- std::istream_iterator [C++], char_type
- std::istream_iterator [C++], istream_type
- std::istream_iterator [C++], traits_type
ms.assetid: fb52a8cd-7f71-48d1-b73e-4b064e2a8d16
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e565d5f10bdb06bff6ad8c17047ed3e11070364d
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44099596"
---
# <a name="istreamiterator-class"></a>istream_iterator Sınıfı

Bir giriş yineleyici nesnesi tanımlar. Sınıfın nesneleri ayıklar `Type` , giriş akışından hangi BT nesneyle depoladığı türü erişir `pointer` için `basic_istream` <  `CharType`, `Traits`>.

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

*Türü*<br/>
Çıkış akışından ayıklanacak nesnenin türü.

*CharType*<br/>
İçin karakter türünü temsil eden tür `istream_iterator`. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer **char**.

*Nitelikler*<br/>
İçin karakter türünü temsil eden tür `istream_iterator`. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `char_traits` <  `CharType`>.

*uzaklık*<br/>
İşaretli için fark türünü temsil eden tamsayı türü `istream_iterator`. Bu bağımsız değişken isteğe bağlıdır ve varsayılan değer `ptrdiff_t`.

Veya NULL olmayan depolanmış bir işaretçiyle ile sınıfı istream_iterator artırılmasının ardından, nesne ayıklayın ve türünde bir nesne depolamayı dener `Type` ilişkili giriş akışından. Ayıklama işlemi başarısız olursa, nesne etkili bir şekilde depolanan işaretçinin yerini alır, böylece bir dizi sonu gösterge oluşturur.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[istream_iterator](#istream_iterator)|Varsayılan olarak bir akış uç yineleyici oluşturur `istream_iterator` veya `istream_iterator` da okuduğu yineleyici akış türüne başlatılan.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|İçin karakter türünü sağlayan bir tür `istream_iterator`.|
|[istream_type](#istream_type)|Akış türü için sağlayan bir tür `istream_iterator`.|
|[traits_type](#traits_type)|Karakter nitelikleri için sağlayan bir tür türü `istream_iterator`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator *](#op_star)|Başvuru kaldırma işleci akıştaki türü depolanmış nesne döndürür `Type` tarafından ele alınan `istream_iterator`.|
|[-> işleci](#op_arrow)|Varsa, bir üyenin değerini döndürür.|
|[operator ++](#op_add_add)|Giriş akışındaki artırılmış nesneyi ayıklar ya da artırmadan önce nesneyi kopyalar ve kopyayı döndürür.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yineleyici >

**Namespace:** std

## <a name="char_type"></a>  istream_iterator::char_type

İçin karakter türünü sağlayan bir tür `istream_iterator`.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `Chartype`.

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

## <a name="istream_iterator"></a>  istream_iterator::istream_iterator

Varsayılan olarak bir akış uç yineleyici oluşturur `istream_iterator` veya `istream_iterator` da okuduğu yineleyici akış türüne başlatılan.

```cpp
istream_iterator();

istream_iterator(istream_type& _Istr);
```

### <a name="parameters"></a>Parametreler

*_Istr*<br/>
Kullanım okunacağı Giriş akışı başlatmak için `istream_iterator`.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, bir null işaretçi Giriş akışı işaretçiyle başlatır ve akış sonu bir yineleyici oluşturur. İkinci oluşturucu başlatır ve Giriş akışı işaretçiyle *& _Istr*, çıkarmayı ve depolamayı bir nesne türü çalışır `Type`.

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

## <a name="istream_type"></a>  istream_iterator::istream_type

Akış türü için sağlayan bir tür `istream_iterator`.

```cpp
typedef basic_istream<CharType, Traits> istream_type;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `basic_istream` \< **CharType**, **nitelikler**>.

### <a name="example"></a>Örnek

Bkz: [istream_iterator](#istream_iterator) bildirme ve kullanma konusunda bir örnek için `istream_type`.

## <a name="op_star"></a>  istream_iterator::operator *

Başvuru kaldırma işleci akıştaki türü depolanmış nesne döndürür `Type` tarafından ele alınan `istream_iterator`.

```cpp
const Type& operator*() const;
```

### <a name="return-value"></a>Dönüş Değeri

Türü depolanmış nesne `Type`.

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

## <a name="op_arrow"></a>  istream_iterator::operator-&gt;

Varsa, bir üyenin değerini döndürür.

```cpp
const Type* operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

Varsa, bir üyenin değeri.

### <a name="remarks"></a>Açıklamalar

*Ben* -> eşdeğerdir (\* *miyim*). *m*

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

## <a name="op_add_add"></a>  istream_iterator::operator++

Giriş akışındaki artırılmış nesneyi ayıklar ya da artırmadan önce nesneyi kopyalar ve kopyayı döndürür.

```cpp
istream_iterator<Type, CharType, Traits, Distance>& operator++();

istream_iterator<Type, CharType, Traits, Distance> operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk üye işleci türünde artan nesnesine bir başvuru döndürür `Type` ayıklanan Giriş akışı ve bir nesnenin bir kopyasını ikinci üye işlevi döndürür.

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

## <a name="traits_type"></a>  istream_iterator::traits_type

Karakter nitelikleri için sağlayan bir tür türü `istream_iterator`.

```cpp
typedef Traits traits_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür *nitelikler*.

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

[input_iterator_tag Yapısı](../standard-library/input-iterator-tag-struct.md)<br/>
[iterator Yapısı](../standard-library/iterator-struct.md)<br/>
[\<Yineleyici >](../standard-library/iterator.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
