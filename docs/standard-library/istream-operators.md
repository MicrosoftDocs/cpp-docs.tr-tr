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
ms.openlocfilehash: 82a5a02ed85e3a02c1131a413eb8588dd49dee90
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100904"
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

*Ch*<br/>
Bir karakter.

*Istr*<br/>
Bir akış.

*str*<br/>
Bir dize.

*VAL*<br/>
Bir tür.

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

**Güvenlik Notu** girdi akışından ayıklanırken null ile sonlandırılmış dize hedef arabelleğinin boyutunu aşamaz *str*. Daha fazla bilgi için [arabellek taşmalarını](/windows/desktop/SecBP/avoiding-buffer-overruns).

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

Döndürür `Istr >> ( char * ) str`.

Şablon işlevi:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, signed char& Ch);
```

Döndürür `Istr >> ( char& ) Ch`.

Şablon işlevi:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char* str);
```

Döndürür `Istr >> ( char * ) str`.

Şablon işlevi:

```cpp
template <class Tr>
basic_istream<char, Tr>& operator>>(
    basic_istream<char, Tr>& Istr, unsigned char& Ch);
```

Döndürür `Istr >> ( char& ) Ch`.

Şablon işlevi:

```cpp
template <class Elem, class Tr, class Type>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<char, Tr>&& Istr,
    Type& val);
```

döndürür `Istr >> val` (ve rvalue başvurusuna çevirir `Istr` işleminde bir lvalue için).

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
