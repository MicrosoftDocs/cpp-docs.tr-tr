---
description: 'Daha fazla bilgi edinin: &lt; IStream &gt; işleçleri'
title: '&lt;IStream &gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- istream/std::operator&gt;&gt;
ms.assetid: 7174da41-f301-4a34-b631-0ab918b188d2
ms.openlocfilehash: 68bf59480af68248533f55ef32de4525a4d900d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277888"
---
# <a name="ltistreamgt-operators"></a>&lt;IStream &gt; işleçleri

## <a name="operatorgtgt"></a><a name="op_gt_gt"></a> işlecinde&gt;&gt;

Akıştan karakterler ve dizeler ayıklar.

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,
    Elem* str);

template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr,
    Elem& Ch);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    signed char* str);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    signed char& Ch);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    unsigned char* str);

template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr,
    unsigned char& Ch);

template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

### <a name="parameters"></a>Parametreler

*Denetleyebilirsiniz*\
Bir karakter.

*İstr*\
Bir akış.

*üstbilgisine*\
Bir dize.

*Acil*\
Bir tür.

### <a name="return-value"></a>Dönüş Değeri

Akış

### <a name="remarks"></a>Açıklamalar

`basic_istream`Sınıfı ayrıca birkaç ayıklama işleci tanımlar. Daha fazla bilgi için bkz. [basic_istream:: operator>>](../standard-library/basic-istream-class.md#op_gt_gt).

İşlev şablonu:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem* str);
```

en fazla `N - 1` öğeyi ayıklar ve bunlara *Str*'den başlayarak dizide depolar. `Istr.` [Genişlik](../standard-library/ios-base-class.md#width) sıfırdan büyükse, *N* ise `Istr.width` ; Aksi takdirde, bildirilebilecek en büyük dizisinin boyutudur `Elem` . İşlev her zaman değeri, `Elem()` depoladığı herhangi bir ayıklanan öğeden sonra saklar. Ayıklama, dosyanın sonunda, değerine sahip bir karakter üzerinde `Elem(0)` (ayıklanmayan) veya [WS](../standard-library/istream-functions.md#ws)tarafından atılacak herhangi bir öğede (ayıklanmayan) erken duraklar. İşlev hiçbir öğe ayıklaıyorsa, çağırır `Istr.` [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)` . Herhangi bir durumda, çağırır `Istr.width(0)` ve *ISTR* döndürür.

**Güvenlik notunun** Giriş akışından ayıklanan null ile sonlandırılmış dizenin hedef arabellek *Str* boyutunu aşmaması gerekir. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/win32/SecBP/avoiding-buffer-overruns).

İşlev şablonu:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem& Ch);
```

Mümkünse bir öğeyi ayıklar ve bunu *ch* içinde depolar. Aksi takdirde, çağırır `is.` [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)` . Herhangi bir durumda, *ISTR* döndürür.

İşlev şablonu:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char* str);
```

döndürür `Istr >> ( char * ) str` .

İşlev şablonu:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char& Ch);
```

döndürür `Istr >> ( char& ) Ch` .

İşlev şablonu:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char* str);
```

döndürür `Istr >> ( char * ) str` .

İşlev şablonu:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char& Ch);
```

döndürür `Istr >> ( char& ) Ch` .

İşlev şablonu:

```cpp
template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

döndürür `Istr >> val` (ve bir rvalue başvurusunu `Istr` işlemdeki bir lvalue öğesine dönüştürür).

### <a name="example"></a>Örnek

```cpp
// istream_op_extract.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   ws( cin );
   char c[10];

   cin.width( 9 );
   cin >> c;
   cout << c << endl;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[\<istream>](../standard-library/istream.md)
