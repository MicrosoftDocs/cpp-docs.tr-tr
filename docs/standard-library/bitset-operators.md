---
description: 'Daha fazla bilgi edinin: &lt; bitset &gt; işleçleri'
title: '&lt;bitset &gt; işleçleri'
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
ms.openlocfilehash: 5157b3e8a8fa94152a4a2446b1d9a4c124677ddd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325457"
---
# <a name="ltbitsetgt-operators"></a>&lt;bitset &gt; işleçleri

## <a name="operatoramp"></a><a name="op_amp"></a> işlecinde&amp;

`AND`İki bitsets arasında bir bit düzeyinde gerçekleştirir.

```cpp
template <size_t size>
bitset<size>
operator&(
    const bitset<size>& left,
    const bitset<size>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
İlgili öğeleri bit düzeyinde birleştirilecek olan iki bitsetin ilki `AND` .

*Right*\
İlgili öğeleri bit düzeyinde birleştirilecek olan iki valarışın ikinci değeri `AND` .

### <a name="return-value"></a>Dönüş Değeri

Öğeleri `AND` *sol* ve *sağ* ilgili öğelerinde işlemin sonucu olan bir bitset.

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

## <a name="operatorltlt"></a><a name="op_lt_lt"></a> işlecinde&lt;&lt;

Çıkış akışına bit dizisinin metin gösterimini ekler.

```cpp
template <class CharType, class Traits, size_t N>
basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& ostr,
    const bitset<N>& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Çıkış akışına dize olarak eklenecek **bitset \<N>** türünde bir nesne.

### <a name="return-value"></a>Dönüş Değeri

İçindeki bit dizisinin metin temsili `ostr` .

### <a name="remarks"></a>Açıklamalar

Şablon işlevi `operator<<` , bir bit kümesinin, önce bir dizeye dönüştürmeden yazılmasına izin vererek aşırı yükler. Şablon işlevi etkin şekilde şunları yürütür:

`ostr << right.`[to_string](bitset-class.md)`<CharType, Traits, allocator<CharType>>()`

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

## <a name="operatorgtgt"></a><a name="op_gt_gt"></a> işlecinde&gt;&gt;

Bit kümesindeki bir bit karakter dizesini okur.

```cpp
template <class CharType, class Traits, size_t Bits>
basic_istream<CharType, Traits>& operator>> (
    basic_istream<CharType, Traits>& i_str,
    bitset<N>& right);
```

### <a name="parameters"></a>Parametreler

*i_str*\
Bit kümesine eklenecek giriş akışına girilen dize.

*Right*\
Giriş akışından bitleri alan bit kümesi.

### <a name="return-value"></a>Dönüş Değeri

Şablon işlevi *i_str* dize döndürür.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, `operator>>` bit kümesinde depolamak için aşırı yükler  `bitset(str)` . burada, `str` i_str ayıklanan [basic_string](basic-string-class.md) türü bir nesnedir `< CharType, Traits, allocator< CharType > >&` . 

Şablon işlevi, öğeleri *i_str* ayıklar ve şu kadar bitset 'e ekler:

- Tüm bit öğeleri giriş akışından ayıklandı ve bitset içinde depolanır.

- Bitset, giriş akışından bitler ile doldurulur.

- 0 veya 1 olmayan bir giriş öğesiyle karşılaşıldı.

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

## <a name="operator"></a><a name="op_xor"></a> işleç ^

`EXCLUSIVE-OR`İki bitsets arasında bir bit düzeyinde gerçekleştirir.

```cpp
template <size_t size>
bitset<size>
operator^(
    const bitset<size>& left,
    const bitset<size>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
İlgili öğeleri bit düzeyinde birleştirilecek olan iki bitsetin ilki `EXCLUSIVE-OR` .

*Right*\
İlgili öğeleri bit düzeyinde birleştirilecek olan iki valarışın ikinci değeri `EXCLUSIVE-OR` .

### <a name="return-value"></a>Dönüş Değeri

Öğeleri `EXCLUSIVE-OR` *sol* ve *sağ* ilgili öğelerinde işlemin sonucu olan bir bitset.

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

## <a name="operator124"></a><a name="op_or"></a> işleç&#124;

`OR`İki bitsets arasında bir bit düzeyinde gerçekleştirir.

```cpp
template <size_t size>
bitset<size>
operator|(
    const bitset<size>& left,
    const bitset<size>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
İlgili öğeleri bit düzeyinde birleştirilecek olan iki bitsetin ilki `OR` .

*Right*\
İlgili öğeleri bit düzeyinde birleştirilecek olan iki valarışın ikinci değeri `OR` .

### <a name="return-value"></a>Dönüş Değeri

Öğeleri `OR` *sol* ve *sağ* ilgili öğelerinde işlemin sonucu olan bir bitset.

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
