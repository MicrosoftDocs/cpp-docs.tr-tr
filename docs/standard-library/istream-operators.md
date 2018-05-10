---
title: '&lt;istream&gt; işleçleri | Microsoft Docs'
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
ms.openlocfilehash: 5068c0bd540b1c44d2cdc484c2e511276bd12666
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="ltistreamgt-operators"></a>&lt;istream&gt; işleçleri

## <a name="op_gt_gt"></a>  işleci&gt;&gt;

Karakterler ve dizeleri akıştan ayıklar.

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

`Ch` Karakter.

`Istr` Bir akış.

`str` Bir dize.

`val` Bir tür.

### <a name="return-value"></a>Dönüş Değeri

Akış

### <a name="remarks"></a>Açıklamalar

`basic_istream` Sınıfı ayrıca birkaç ayıklama işleçlerini tanımlar. Daha fazla bilgi için bkz: [basic_istream::operator >>](../standard-library/basic-istream-class.md#op_gt_gt).

Şablon işlevi:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem* str);
```

en fazla ayıklar *N* - 1 öğeleri ve başlatma sırasında _ dizi depolar *Str*. Varsa `Istr`. [Genişlik](../standard-library/ios-base-class.md#width) , sıfırdan büyük *N* olan `Istr`. **Genişlik**; Aksi halde, en büyük dizi boyutu olan **Elem** , bildirilebilir. İşlev değeri her zaman depolar **Elem()** herhangi depoladığı öğeleri ayıklanan sonra. Ayıklama durdurur erken dosya sonu, değeri olan bir karakter üzerinde üzerinde **Elem**(0) (hangi değil ayıklanır), veya tarafından atılmak (hangi değil ayıklanır) herhangi bir öğeyi [ws](../standard-library/istream-functions.md#ws). Öğe işlevi ayıklar, çağıran `Istr`. [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**). Herhangi bir durumda, çağıran `Istr`. **Genişlik**(0) ve döndürür `Istr`.

**Güvenlik Notu** giriş akışından ayıklanırken null ile sonlandırılmış dize hedef arabellek boyutunu aşmamalıdır `str`. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795).

Şablon işlevi:

```cpp
template <class Elem, class Tr>
basic_istream<Elem, Tr>& operator>>(
    basic_istream<Elem, Tr>& Istr, Elem& Ch);
```

bir öğenin olasıdır ve depolar ayıklar `Ch`. Aksi takdirde, çağıran **olan**. [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**). Her iki durumda da döndürür `Istr`.

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

döndürür `Istr` `>>` `val` (ve dönüştüren bir `rvalue reference` için `Istr` için bir `lvalue` işleminde).

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
