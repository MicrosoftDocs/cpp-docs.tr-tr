---
title: '&lt;cassert&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cassert>
helpviewer_keywords:
- cassert header
ms.assetid: 6ead15a3-ac45-4075-be8e-350bca995c26
ms.openlocfilehash: b28f4554610d37b881494748f75499f46cd9e8d9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230239"
---
# <a name="ltcassertgt"></a>&lt;cassert&gt;

C standart kitaplığı üst bilgisini içerir \<assert.h> ve ilgili adları `std` ad alanına ekler. Bu üst bilgiyi dahil etmek, C standart kitaplığı üstbilgisinde harici bağlantı kullanılarak belirtilen adların `std` ad alanında bildirilmesini sağlar.

> [!NOTE]
> \<assert.h>**`static_assert`** makroyu tanımlamaz.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <cassert>
```

## <a name="macros"></a>Makrolar

```cpp
#define assert(E)
```

### <a name="remarks"></a>Açıklamalar

`assert(E)`yalnızca bir sabittir, NDEBUG, `assert` son tanımlanan veya yeniden tanımlandı *E* **`true`**

## <a name="see-also"></a>Ayrıca bkz.

[onaylama makrosu, _assert _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)\
[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ standart kitaplığına genel bakış](../standard-library/cpp-standard-library-overview.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
