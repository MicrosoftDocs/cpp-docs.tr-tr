---
title: '&lt;istream&gt; işleçler | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- istream/std::operator&gt;&gt;
dev_langs:
- C++
ms.assetid: 7174da41-f301-4a34-b631-0ab918b188d2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 60ec526dd8874529b60558f7131c31f0bf4a2d3b
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38961119"
---
# <a name="ltistreamgt-operators"></a>&lt;istream&gt; işleçleri

## <a name="op_gt_gt"></a>  İşleci&gt;&gt;

Karakterlerin ve dizelerin akıştan ayıklar.

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

*CH* bir karakter.

*Istr* bir akış.

*str* bir dize.

*VAL* bir tür.

### <a name="return-value"></a>Dönüş Değeri

Akış

### <a name="remarks"></a>Açıklamalar

`basic_istream` Sınıfı da birkaç ayıklama işleçlerini tanımlar. Daha fazla bilgi için [basic_istream::operator >>](../standard-library/basic-istream-class.md#op_gt_gt).

Şablon işlevi:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem* str);
```

en fazla ayıklar *N* - 1 öğeleri ve başlatma _ dizide saklar *Str*. Varsa `Istr`. [Genişlik](../standard-library/ios-base-class.md#width) , sıfırdan büyük *N* olduğu `Istr`. **Genişlik**; Aksi takdirde, en büyük dizi boyutu olan `Elem` , bildirilebilir. İşlev her zaman değeri depolar `Elem()` herhangi depoladığı öğeleri ayıklanan sonra. Ayıklama durdurur erken dosya sonu, bir karakter değeri ile üzerinde bulunan **Elem**(0) (hangi değil ayıklanır), veya herhangi bir öğede tarafından atılan (Bu ayıklanmadı) [ws](../standard-library/istream-functions.md#ws). Hiçbir öğe işlevi ayıklar, çağırdığı `Istr`. [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**). Her durumda çağıran `Istr`. **Genişlik**(0) ve döndürür *Istr*.

**Güvenlik Notu** girdi akışından ayıklanırken null ile sonlandırılmış dize hedef arabelleğinin boyutunu aşamaz *str*. Daha fazla bilgi için [arabellek taşmalarını](http://msdn.microsoft.com/library/windows/desktop/ms717795).

Şablon işlevi:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem& Ch);
```

bir öğe mümkündür ve depolar ayıklar *Ch*. Aksi takdirde, çağrı **olduğu**. [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**). Her durumda döndürür *Istr*.

Şablon işlevi:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char* str);
```

döndürür `Istr` >> ( `char` **\***) `str`.

Şablon işlevi:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char& Ch);
```

döndürür `Istr` >> ( **char &**) `Ch`.

Şablon işlevi:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char* str);
```

döndürür `Istr` >> ( **char \*** ) `str`.

Şablon işlevi:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char& Ch);
```

döndürür `Istr` >> ( **char &**) `Ch`.

Şablon işlevi:

```cpp
template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

döndürür `Istr` `>>` `val` (ve dönüştüren bir `rvalue reference` için `Istr` için bir `lvalue` işlemdeki).

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

[\<istream >](../standard-library/istream.md)<br/>
