---
description: 'Daha fazla bilgi edinin: &lt; ostream &gt; işlevleri'
title: '&lt;ostream &gt; işlevleri'
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
ms.openlocfilehash: fb99b713db4c29fe42b45858588181536aec4f5e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280527"
---
# <a name="ltostreamgt-functions"></a>&lt;ostream &gt; işlevleri

Bunlar, ostream 'de tanımlanan genel şablon işlevleridir &lt; &gt; . Üye işlevleri için [basic_ostream sınıfı](basic-ostream-class.md) belgelerine bakın.

[endl](#endl)\
[ucundaki](#ends)\
[temizlenemiyor](#flush)\
[Kur](#swap)

## <a name="endl"></a>endl

Bir satırı sonlandırır ve arabelleği boşaltır.

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& endl(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>Parametreler

*Elem*\
Öğe türü.

*OSTR*\
**Basic_ostream** türünde bir nesne.

*Tr*\
Karakter nitelikleri.

### <a name="return-value"></a>Dönüş Değeri

**Basic_ostream** türünde bir nesne.

### <a name="remarks"></a>Açıklamalar

İşleici *OSTR*'yi çağırıyor. [PUT](../standard-library/basic-ostream-class.md#put)(*OSTR*.[ ('](../standard-library/basic-ios-class.md#widen)\n ')) ve ardından *OSTR* çağırır. [temizler](../standard-library/basic-ostream-class.md#flush). *OSTR* döndürür.

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

*Elem*\
Öğe türü.

*OSTR*\
`basic_ostream` türünün bir nesnesi.

*Tr*\
Karakter nitelikleri.

### <a name="return-value"></a>Dönüş Değeri

`basic_ostream` türünün bir nesnesi.

### <a name="remarks"></a>Açıklamalar

İşleici *OSTR*'yi çağırıyor. [PUT](../standard-library/basic-ostream-class.md#put)(*eled*(' \ 0 ')). *OSTR* döndürür.

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

*Elem*\
Öğe türü.

*OSTR*\
`basic_ostream` türünün bir nesnesi.

*Tr*\
Karakter nitelikleri.

### <a name="return-value"></a>Dönüş Değeri

`basic_ostream` türünün bir nesnesi.

### <a name="remarks"></a>Açıklamalar

İşleici *OSTR*'yi çağırıyor. [temizler](../standard-library/basic-ostream-class.md#flush). *OSTR* döndürür.

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

İki nesnenin değerlerini değiş tokuş eder `basic_ostream` .

```cpp
template <class Elem, class Tr>
void swap(
   basic_ostream<Elem, Tr>& left,
   basic_ostream<Elem, Tr>& right);
```

### <a name="parameters"></a>Parametreler

*Elem*\
Öğe türü.

*Tr*\
Karakter nitelikleri.

*tarafta*\
Bir nesneye lvalue başvurusu `basic_ostream` .

*Right*\
Bir nesneye lvalue başvurusu `basic_ostream` .

### <a name="remarks"></a>Açıklamalar

Şablon işlevi `swap` yürütülür `left.swap(right)` .

## <a name="see-also"></a>Ayrıca bkz.

[\<ostream>](../standard-library/ostream.md)
