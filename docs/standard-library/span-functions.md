---
description: 'Daha fazla bilgi edinin: &lt; span &gt; işlevleri'
title: '&lt;span &gt; işlevleri'
ms.date: 05/28/2020
f1_keywords:
- span/std::span::as_bytes
- span/std::as_writable_bytes
helpviewer_keywords:
- std::span [C++], as_writable_bytes
- std::as_bytes [C++]
ms.openlocfilehash: 09d712d6dfffee2aa24e0e8cecca4031a27923f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169196"
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

`T`Değilse **`const`** , yayılma alanındaki öğelerin ham bayt gösteriminin okuma/yazma görünümünü alır.

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
