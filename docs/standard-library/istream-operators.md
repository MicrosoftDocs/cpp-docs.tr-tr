---
title: IStream&gt; işleçleri &lt;
ms.date: 11/04/2016
f1_keywords:
- istream/std::operator&gt;&gt;
ms.assetid: 7174da41-f301-4a34-b631-0ab918b188d2
ms.openlocfilehash: 5ac5c61488530f99cdad38ca1bfca365b6ac0f8c
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79420129"
---
# <a name="ltistreamgt-operators"></a>IStream&gt; işleçleri &lt;

## <a name="op_gt_gt"></a>işleç&gt;&gt;

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

*Ch*\
Bir karakter.

*ISTR*\
Bir akış.

*str*\
Bir dize.

*val*\
Bir tür.

### <a name="return-value"></a>Dönüş Değeri

Akış

### <a name="remarks"></a>Açıklamalar

`basic_istream` sınıfı ayrıca birkaç ayıklama işleci tanımlar. Daha fazla bilgi için bkz. [basic_istream:: operator > >](../standard-library/basic-istream-class.md#op_gt_gt).

İşlev şablonu:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem* str);
```

`N - 1` en fazla öğeyi ayıklar ve bunları dizide *Str*'dan başlayarak depolar. `Istr.`[Width](../standard-library/ios-base-class.md#width) sıfırdan büyükse, *N* `Istr.width`; Aksi takdirde, bu, bildirilebilecek en büyük `Elem` dizisi boyutudur. İşlevi `Elem()` her zaman değeri saklar. Ayıklama, dosya sonunda, değer `Elem(0)` (ayıklanmayan) veya [WS](../standard-library/istream-functions.md#ws)tarafından atılacak herhangi bir öğede (ayıklanmayan) bir karakter üzerinde erken duraklar. İşlev hiçbir öğe ayıklaıyorsa, `Istr.`[`setstate`](../standard-library/basic-ios-class.md#setstate)`(failbit)`çağırır. Herhangi bir durumda, `Istr.width(0)` çağırır ve *ISTR*döndürür.

**Güvenlik notunun** Giriş akışından ayıklanan null ile sonlandırılmış dizenin hedef arabellek *Str*boyutunu aşmaması gerekir. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/win32/SecBP/avoiding-buffer-overruns).

İşlev şablonu:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem& Ch);
```

Mümkünse bir öğeyi ayıklar ve bunu *ch*içinde depolar. Aksi takdirde, `is.`[`setstate`](../standard-library/basic-ios-class.md#setstate)`(failbit)`çağırır. Herhangi bir durumda, *ISTR*döndürür.

İşlev şablonu:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char* str);
```

`Istr >> ( char * ) str`döndürür.

İşlev şablonu:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char& Ch);
```

`Istr >> ( char& ) Ch`döndürür.

İşlev şablonu:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char* str);
```

`Istr >> ( char * ) str`döndürür.

İşlev şablonu:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char& Ch);
```

`Istr >> ( char& ) Ch`döndürür.

İşlev şablonu:

```cpp
template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

`Istr >> val` döndürür (ve bir rvalue başvurusunu işlem içindeki bir lvalue `Istr` dönüştürür).

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

[IStream > \<](../standard-library/istream.md)
