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
ms.openlocfilehash: fa498f4acbb151eab4321bcddc6af027ee266237
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62371004"
---
# <a name="ltostreamgt-functions"></a>&lt;ostream&gt; işlevleri

Tanımlanan genel şablon işlevleri bunlar &lt;ostream&gt;. Üye işlevleri için bkz: [basic_ostream sınıfı](basic-ostream-class.md) belgeleri.

||||
|-|-|-|
|[endl](#endl)|[sona erer](#ends)|[Temizleme](#flush)|
|[değiştirme](#swap)|

## <a name="endl"></a>endl

Bir satır sonlandırır ve arabelleğini aktarır.

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& endl(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>Parametreler

*Elem*<br/>
Öğe türü.

*Ostr*<br/>
Bir nesne türü **basic_ostream**.

*tr*<br/>
Karakter nitelikleri.

### <a name="return-value"></a>Dönüş Değeri

Bir nesne türü **basic_ostream**.

### <a name="remarks"></a>Açıklamalar

İşleyici çağrıları *Ostr*.[ PUT](../standard-library/basic-ostream-class.md#put)(*Ostr*.[ genişletmek](../standard-library/basic-ios-class.md#widen)('\n')) ve ardından çağırır *Ostr*.[ Flush](../standard-library/basic-ostream-class.md#flush). Döndürür *Ostr*.

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

Bir dize sonlandırır.

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& ends(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>Parametreler

*Elem*<br/>
Öğe türü.

*Ostr*<br/>
Bir nesne türü `basic_ostream`.

*tr*<br/>
Karakter nitelikleri.

### <a name="return-value"></a>Dönüş Değeri

Bir nesne türü `basic_ostream`.

### <a name="remarks"></a>Açıklamalar

İşleyici çağrıları *Ostr*.[ PUT](../standard-library/basic-ostream-class.md#put)(*Elem*('\0')). Döndürür *Ostr*.

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

Arabelleği temizler.

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& flush(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>Parametreler

*Elem*<br/>
Öğe türü.

*Ostr*<br/>
Bir nesne türü `basic_ostream`.

*tr*<br/>
Karakter nitelikleri.

### <a name="return-value"></a>Dönüş Değeri

Bir nesne türü `basic_ostream`.

### <a name="remarks"></a>Açıklamalar

İşleyici çağrıları *Ostr*.[ Flush](../standard-library/basic-ostream-class.md#flush). Döndürür *Ostr*.

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

İki değeri birbiriyle değiştirir `basic_ostream` nesneleri.

```cpp
template <class Elem, class Tr>
void swap(
   basic_ostream<Elem, Tr>& left,
   basic_ostream<Elem, Tr>& right);
```

### <a name="parameters"></a>Parametreler

*Elem*<br/>
Öğe türü.

*tr*<br/>
Karakter nitelikleri.

*Sol*<br/>
Bir lvalue başvurusuna bir `basic_ostream` nesne.

*sağ*<br/>
Bir lvalue başvurusuna bir `basic_ostream` nesne.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi `swap` yürütür `left.swap(right)`.

## <a name="see-also"></a>Ayrıca bkz.

[\<ostream >](../standard-library/ostream.md)
