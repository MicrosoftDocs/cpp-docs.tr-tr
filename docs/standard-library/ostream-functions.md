---
title: '&lt;ostream&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- ostream/std::swap
- ostream/std::endl
- ostream/std::ends
- ostream/std::flush
ms.assetid: d6e56cc0-c8df-4dbe-be10-98e14c35ed3a
caps.latest.revision: 15
manager: ghogen
helpviewer_keywords:
- std::swap [C++]
- std::endl [C++]
- std::ends [C++]
- std::flush [C++]
ms.openlocfilehash: 41463d912b3ab33812a1f7c0a0ea5f8172036e57
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ltostreamgt-functions"></a>&lt;ostream&gt; işlevleri

Tanımlanan genel şablon işlevleri bunlar &lt;ostream&gt;. Üye işlevleri için bkz: [basic_ostream sınıfı](basic-ostream-class.md) belgeleri.

||||
|-|-|-|
|[endl](#endl)|[sona erer](#ends)|[Temizleme](#flush)|
|[Değiştirme](#swap)|

## <a name="endl"></a>endl

Bir satır sonlandırır ve arabelleği temizler.

```cpp
template class<Elem, Tr>
basic_ostream<Elem, Tr>& endl(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>Parametreler

*Elem* öğe türü.

*Ostr* türünde bir nesne **basic_ostream**.

*Tr* nitelikler karakter.

### <a name="return-value"></a>Dönüş Değeri

Türünde bir nesne **basic_ostream**.

### <a name="remarks"></a>Açıklamalar

Manipulator çağrıları *Ostr*.[ PUT](../standard-library/basic-ostream-class.md#put)(*Ostr*.[ widen](../standard-library/basic-ios-class.md#widen)('\n')) ve ardından çağırır *Ostr*.[ Flush](../standard-library/basic-ostream-class.md#flush). Döndürdüğü *Ostr*.

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

*Elem* öğe türü.

*Ostr* türünde bir nesne **basic_ostream**.

*Tr* nitelikler karakter.

### <a name="return-value"></a>Dönüş Değeri

Türünde bir nesne **basic_ostream**.

### <a name="remarks"></a>Açıklamalar

Manipulator çağrıları *Ostr*.[ PUT](../standard-library/basic-ostream-class.md#put)(*Elem*('\0')). Döndürdüğü *Ostr*.

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

*Elem* öğe türü.

*Ostr* türünde bir nesne **basic_ostream**.

*Tr* nitelikler karakter.

### <a name="return-value"></a>Dönüş Değeri

Türünde bir nesne **basic_ostream**.

### <a name="remarks"></a>Açıklamalar

Manipulator çağrıları *Ostr*.[ Flush](../standard-library/basic-ostream-class.md#flush). Döndürdüğü *Ostr*.

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

İki değerlerini alış verişleri **basic_ostream** nesneleri.

```cpp
template <class Elem, class Tr>
void swap(
   basic_ostream<Elem, Tr>& left,
   basic_ostream<Elem, Tr>& right);
```

### <a name="parameters"></a>Parametreler

*Elem* öğe türü.

*Tr* nitelikler karakter.

*Sol* lvalue başvuru için bir **basic_ostream** nesnesi.

*sağ* lvalue başvuru için bir **basic_ostream** nesnesi.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi **takas** yürütür `left.swap(right)`.

## <a name="see-also"></a>Ayrıca bkz.

[\<ostream >](../standard-library/ostream.md)
