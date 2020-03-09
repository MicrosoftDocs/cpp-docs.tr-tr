---
title: '&lt;ostream&gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- ostream/std::swap
- ostream/std::endl
- ostream/std::ends
- ostream/std::flush
ms.assetid: d6e56cc0-c8df-4dbe-be10-98e14c35ed3a
helpviewer_keywords:
- std::swap [C++]
- std::endl [C++]
- std::ends [C++]
- std::flush [C++]
ms.openlocfilehash: 8d93e46b0323058d93c6d0bd8c1ee566998aef61
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78874852"
---
# <a name="ltostreamgt-functions"></a>&lt;ostream&gt; işlevleri

Bunlar, &lt;ostream&gt;tanımlanan genel şablon işlevleridir. Üye işlevleri için [basic_ostream sınıfı](basic-ostream-class.md) belgelerine bakın.

||||
|-|-|-|
|[endl](#endl)|[ucundaki](#ends)|[temizlenemiyor](#flush)|
|[Kur](#swap)|

## <a name="endl"></a>endl

Bir satırı sonlandırır ve arabelleği boşaltır.

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& endl(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>Parametreler

*Eled*\
Öğe türü.

*OSTR*\
**Basic_ostream**türünde bir nesne.

*Tr*\
Karakter nitelikleri.

### <a name="return-value"></a>Dönüş Değeri

**Basic_ostream**türünde bir nesne.

### <a name="remarks"></a>Açıklamalar

İşleici *OSTR*'yi çağırıyor. [PUT](../standard-library/basic-ostream-class.md#put)(*OSTR*.[ ('](../standard-library/basic-ios-class.md#widen)\n ')) ve ardından *OSTR*çağırır. [temizler](../standard-library/basic-ostream-class.md#flush). *OSTR*döndürür.

### <a name="example"></a>Örnek

```cpp
// ostream_endl.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "testing" << endl;
}
```

```Output
testing
```

## <a name="ends"></a>ends

Bir dizeyi sonlandırır.

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& ends(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>Parametreler

*Eled*\
Öğe türü.

*OSTR*\
`basic_ostream` türünün bir nesnesi.

*Tr*\
Karakter nitelikleri.

### <a name="return-value"></a>Dönüş Değeri

`basic_ostream` türünün bir nesnesi.

### <a name="remarks"></a>Açıklamalar

İşleici *OSTR*'yi çağırıyor. [PUT](../standard-library/basic-ostream-class.md#put)(*eled*(' \ 0 ')). *OSTR*döndürür.

### <a name="example"></a>Örnek

```cpp
// ostream_ends.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "a";
   cout << "b" << ends;
   cout << "c" << endl;
}
```

```Output
ab c
```

## <a name="flush"></a>flush

Arabelleği boşaltır.

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& flush(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>Parametreler

*Eled*\
Öğe türü.

*OSTR*\
`basic_ostream` türünün bir nesnesi.

*Tr*\
Karakter nitelikleri.

### <a name="return-value"></a>Dönüş Değeri

`basic_ostream` türünün bir nesnesi.

### <a name="remarks"></a>Açıklamalar

İşleici *OSTR*'yi çağırıyor. [temizler](../standard-library/basic-ostream-class.md#flush). *OSTR*döndürür.

### <a name="example"></a>Örnek

```cpp
// ostream_flush.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "testing" << flush;
}
```

```Output
testing
```

## <a name="swap"></a>swap

İki `basic_ostream` nesnesinin değerlerini değiş tokuş eder.

```cpp
template <class Elem, class Tr>
void swap(
   basic_ostream<Elem, Tr>& left,
   basic_ostream<Elem, Tr>& right);
```

### <a name="parameters"></a>Parametreler

*Eled*\
Öğe türü.

*Tr*\
Karakter nitelikleri.

*sol*\
`basic_ostream` nesnesine bir lvalue başvurusu.

*sağ*\
`basic_ostream` nesnesine bir lvalue başvurusu.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi `left.swap(right)`yürütür `swap`.

## <a name="see-also"></a>Ayrıca bkz.

[ostream > \<](../standard-library/ostream.md)
