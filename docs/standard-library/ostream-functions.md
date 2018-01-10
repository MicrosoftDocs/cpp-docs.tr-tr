---
title: "&lt;ostream&gt; işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ostream/std::swap
- ostream/std::endl
- ostream/std::ends
- ostream/std::flush
ms.assetid: d6e56cc0-c8df-4dbe-be10-98e14c35ed3a
caps.latest.revision: "15"
manager: ghogen
helpviewer_keywords:
- std::swap [C++]
- std::endl [C++]
- std::ends [C++]
- std::flush [C++]
ms.openlocfilehash: 9b9f64f67b1649c1c2f3d65f63636fd62601d06a
ms.sourcegitcommit: a7e4956c1150273e8dd39fda8b41655a6cf2cb98
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/08/2017
---
# <a name="ltostreamgt-functions"></a>&lt;ostream&gt; işlevleri

Tanımlanan genel şablon işlevleri bunlar &lt;ostream&gt;. Üye işlevleri için bkz: [basic_ostream sınıfı](basic-ostream-class.md) belgeleri.

||||
|-|-|-|
|[endl](#endl)|[sona erer](#ends)|[Temizleme](#flush)|
|[değiştirme](#swap)|

## <a name="endl"></a>endl

Bir satır sonlandırır ve arabelleği temizler.

```cpp
template class<Elem, Tr> 
basic_ostream<Elem, Tr>& endl(
   basic_ostream<Elem, Tr>& Ostr);
```

### <a name="parameters"></a>Parametreler

*Elem*  
Öğe türü.

*Ostr*  
Türünde bir nesne **basic_ostream**.

*Tr*  
Karakter nitelikler.

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

*Elem*  
Öğe türü.

*Ostr*  
Türünde bir nesne **basic_ostream**.

*Tr*  
Karakter nitelikler.

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

*Elem*  
Öğe türü.

*Ostr*  
Türünde bir nesne **basic_ostream**.

*Tr*  
Karakter nitelikler.

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

*Elem*  
Öğe türü.

*Tr*  
Karakter nitelikler.

*Sol*  
Lvalue başvuru için bir **basic_ostream** nesnesi.

*sağ*  
Lvalue başvuru için bir **basic_ostream** nesnesi.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi **takas** yürütür `left.swap(right)`.

## <a name="see-also"></a>Ayrıca bkz.

[\<ostream >](../standard-library/ostream.md)  
