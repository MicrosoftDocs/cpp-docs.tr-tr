---
title: '&lt;bitset&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- bitset/std::operator&amp;
- bitset/std::operator&gt;&gt;
- bitset/std::operator&lt;&lt;
- bitset/std::operator^
- bitset/std::operator|
ms.assetid: 84fe6a13-6f6e-4cdc-bf8f-6f65ab1134d4
helpviewer_keywords:
- std::operator&amp; (bitset)
- std::operator&gt;&gt; (bitset)
- std::operator&lt;&lt; (bitset)
ms.openlocfilehash: 1c4c1b6f6c023514a1d3ae46f6670247e4bf99d4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62380201"
---
# <a name="ltbitsetgt-operators"></a>&lt;bitset&gt; işleçleri

||||
|-|-|-|
|[İşleci&amp;](#op_amp)|[İşleci&gt;&gt;](#op_gt_gt)|[İşleci&lt;&lt;](#op_lt_lt)|
|[operator ^](#op_xor)|[operator&#124;](#op_or)| |

## <a name="op_amp"></a>  İşleci&amp;

Bit düzeyinde gerçekleştirir `AND` iki bitsets arasında.

```cpp
template <size_t size>
bitset<size>
operator&(
    const bitset<size>& left,
    const bitset<size>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
İlgili öğeleri olan bit ile birleştirilecek iki bitsets ilk `AND`.

*sağ*<br/>
İki valarrays ilgili öğeleri olan bit ile birleştirilecek ikinci `AND`.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri olan sonucunu bir bitset `AND` karşılık gelen öğeleri üzerinde işlem *sol* ve *doğru*.

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

## <a name="op_lt_lt"></a>  İşleci&lt;&lt;

Bit sırayı bir metin temsili çıkış akışına ekler.

```
template <class CharType, class Traits, size_t N>
basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& ostr,
    const bitset<N>& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Bir nesne türü **bitset\<N >** olan dize olarak çıkış akışına içine eklenecek.

### <a name="return-value"></a>Dönüş Değeri

Bit sırayı bir metin temsili `ostr`.

### <a name="remarks"></a>Açıklamalar

Şablonu işlev aşırı yüklemelerinin `operator<<`, ilk dizeye değiştirmeden yazılmalıdır bir bitset izin verme. Şablon işlevi etkin şekilde şunları yürütür:

**ostr** << _ *sağ*. [to_string](bitset-class.md) < **CharType**, **nitelikler**, **ayırıcı** \< **CharType**>>)

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

## <a name="op_gt_gt"></a>  İşleci&gt;&gt;

Bir bitset bir bit karakter dizesini okur.

```
template <class CharType, class Traits, size_t Bits>
basic_istream<CharType, Traits>& operator>> (
    basic_istream<CharType, Traits>&
_Istr,
    bitset<N>&
    right);
```

### <a name="parameters"></a>Parametreler

*_Istr*<br/>
Bitset eklenecek giriş akışının içine girilen bir dize.

*sağ*<br/>
BITS, giriş akışından alıyor bitset.

### <a name="return-value"></a>Dönüş Değeri

Dize şablon işlevinin döndürdüğü *_Istr*.

### <a name="remarks"></a>Açıklamalar

Şablonu işlev aşırı yüklemelerinin `operator>>` depolamak için bitset _ *sağ* değer bitset (`str`), burada `str` türünde bir nesnedir [basic_string](basic-string-class.md)  <  **CharType**, **nitelikler**, **ayırıcı** \< **CharType**>> **&** ayıklanan *_Istr*.

Şablon işlevi öğeleri ayıklar *_Istr* ve bunları kadar bitset ekler:

- Tüm bit öğeleri girdi akışından ayıklanır ve bitset içinde depolanır.

- Bitset giriş akışından BITS ile doldurulur.

- Bir input öğesi 0 ya da 1 olan karşılaşıldı.

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

## <a name="op_xor"></a>  operator ^

Bit düzeyinde gerçekleştirir `EXCLUSIVE-OR` iki bitsets arasında.

```cpp
template <size_t size>
bitset<size>
operator^(
    const bitset<size>& left,
    const bitset<size>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
İlgili öğeleri olan bit ile birleştirilecek iki bitsets ilk `EXCLUSIVE-OR`.

*sağ*<br/>
İki valarrays ilgili öğeleri olan bit ile birleştirilecek ikinci `EXCLUSIVE-OR`.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri olan sonucunu bir bitset `EXCLUSIVE-OR` karşılık gelen öğeleri üzerinde işlem *sol* ve *doğru*.

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

## <a name="op_or"></a>  işleci&#124;

Bit düzeyinde gerçekleştirir `OR` iki bitsets arasında.

```cpp
template <size_t size>
bitset<size>
operator|(
    const bitset<size>& left,
    const bitset<size>& right);
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
İlgili öğeleri olan bit ile birleştirilecek iki bitsets ilk `OR`.

*sağ*<br/>
İki valarrays ilgili öğeleri olan bit ile birleştirilecek ikinci `OR`.

### <a name="return-value"></a>Dönüş Değeri

Öğeleri olan sonucunu bir bitset `OR` karşılık gelen öğeleri üzerinde işlem *sol* ve *doğru*.

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

## <a name="see-also"></a>Ayrıca bkz.

[\<bitset >](../standard-library/bitset.md)<br/>
