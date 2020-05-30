---
title: '&lt;span &gt; işlevleri'
ms.date: 05/28/2020
f1_keywords:
- span/std::span::as_bytes
- span/std::as_writable_bytes
helpviewer_keywords:
- std::span [C++], as_writable_bytes
- std::as_bytes [C++]
ms.openlocfilehash: 6573ea061673091113244ada0ab0cd84bdd7db75
ms.sourcegitcommit: 1a8fac06478da8bee1f6d70e25afbad94144af1a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/30/2020
ms.locfileid: "84226120"
---
# <a name="ltspangt-functions"></a>&lt;span &gt; işlevleri

\<span>Üst bilgi, nesneleri **yayılmış** nesneler üzerinde çalışan aşağıdaki üye olmayan işlevleri içerir.

| **Üye olmayan işlevler** | **Açıklama** |
|-|-|
|[as_bytes](#as_bytes) | Yayılma alanındaki öğelerin nesne gösteriminin salt okunurdur görünümünü alın. |
|[as_writable_bytes](#as_writable_bytes) | Yayılma alanındaki öğelerin nesne gösteriminin okuma/yazma görünümünü alın. |

## <a name="as_bytes"></a>`as_bytes`

Yayılma alanındaki öğelerin nesne gösteriminin salt okunurdur görünümünü alın.

```cpp
template <class T, size_t Extent>
auto as_bytes(span<T, Extent> s) noexcept;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Yayılma alanındaki öğelerin türü.

*Genişliğini*\
Yayılma alanındaki öğelerin sayısı (derleme sırasında biliniyorsa), aksi takdirde `dynamic_extent` öğe sayısının çalışma zamanına kadar bilinmediğini gösterir.

*malar*\
Ham gösterimini almak için yayılma.

### <a name="return-value"></a>Dönüş Değeri

`span<const byte, S>`' Nin bulunduğu yayılma alanında depolanan ilk öğeye `S``{reinterpret_cast<const std::byte*>(s.data()), s.size_bytes()}`

### <a name="example"></a>Örnek

```cpp
#include <span>
#include <iostream>

using namespace std;

void main()
{
    int a[] = { 0,1,2 };
    span <int> mySpan(a);
    auto bytes = std::as_bytes(mySpan);
}
```

## <a name="as_writable_bytes"></a>`as_writable_bytes`

`T`Değilse `const` , yayılma alanındaki öğelerin ham bayt gösteriminin okuma/yazma görünümünü alır.

```cpp
template <class T, size_t Extent>
auto as_writable_bytes(span<T, Extent> s) noexcept;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Yayılma alanındaki öğelerin türü.

*Genişliğini*\
Yayılma alanındaki öğelerin sayısı (derleme sırasında biliniyorsa), aksi takdirde `dynamic_extent` öğe sayısının çalışma zamanına kadar bilinmediğini gösterir.

*malar*\
Ham gösterimini almak için yayılma.

### <a name="return-value"></a>Dönüş Değeri

`span<byte, S>`' Nin bulunduğu yayılma alanında depolanan ilk öğeye `S``{reinterpret_cast<std::byte*>(s.data()), s.size_bytes()}`

### <a name="example"></a>Örnek

```cpp
#include <span>
#include <iostream>

using namespace std;

void main()
{
    int a[] = { 0,1,2 };
    span <int> mySpan(a);
    auto bytes = as_writable_bytes(mySpan);
}
```

## <a name="see-also"></a>Ayrıca bkz.

[\<span>](span.md)
