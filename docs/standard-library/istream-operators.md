---
title: '&lt;istream&gt; operatörleri'
ms.date: 11/04/2016
f1_keywords:
- istream/std::operator&gt;&gt;
ms.assetid: 7174da41-f301-4a34-b631-0ab918b188d2
ms.openlocfilehash: 3b9521fde1b5a03389bfc1ad3e35fa407d9d6ac0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363034"
---
# <a name="ltistreamgt-operators"></a>&lt;istream&gt; operatörleri

## <a name="operatorgtgt"></a><a name="op_gt_gt"></a>Işleç&gt;&gt;

Akışları ayıklar karakterler ve dizeleri ayıklar.

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

*Caner*\
Bir karakter.

*Istr*\
Bir dere.

*Str*\
Bir ip.

*Val*\
Bir tür.

### <a name="return-value"></a>Dönüş Değeri

Akış

### <a name="remarks"></a>Açıklamalar

Sınıf `basic_istream` ayrıca birkaç çıkarma işleci tanımlar. Daha fazla bilgi için [basic_istream::operator>>. ](../standard-library/basic-istream-class.md#op_gt_gt)

İşlev şablonu:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem* str);
```

elemanlara `N - 1` kadar ayıklar ve *str*başlayan dizi onları depolar . `Istr.` [Genişlik](../standard-library/ios-base-class.md#width) sıfırdan büyükse, *N;* `Istr.width` aksi takdirde, bu ilan edilebilir en `Elem` büyük dizi boyutu. İşlev her zaman `Elem()` depolanan herhangi bir öğeden sonra değeri depolar. Ayıklama dosyanın sonunda, değeri `Elem(0)` olan bir karakterde (ayıklanmadı) veya [ws](../standard-library/istream-functions.md#ws)tarafından atılabilecek herhangi bir öğede (ayıklanmadı) durur. İşlev hiçbir öğe yitirmezse, çağırır. `Istr.` [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)` Her durumda, arar `Istr.width(0)` ve *Istr*döndürür.

**Güvenlik Notu** Giriş akışından çıkarılan null-sonlandırılan dize, hedef arabellek *str*boyutunu aşmamalıdır. Daha fazla bilgi için [bkz.](/windows/win32/SecBP/avoiding-buffer-overruns)

İşlev şablonu:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem& Ch);
```

mümkünse bir öğe ayıklar ve *Ch*depolar . Aksi takdirde, `is.` [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)`çağırır . Her durumda, *Istr*döndürür.

İşlev şablonu:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char* str);
```

döndürür. `Istr >> ( char * ) str`

İşlev şablonu:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char& Ch);
```

döndürür. `Istr >> ( char& ) Ch`

İşlev şablonu:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char* str);
```

döndürür. `Istr >> ( char * ) str`

İşlev şablonu:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char& Ch);
```

döndürür. `Istr >> ( char& ) Ch`

İşlev şablonu:

```cpp
template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

döndürür `Istr >> val` (ve işlemdeki `Istr` bir lvalue'a bir rvalue referansı dönüştürür).

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
