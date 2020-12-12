---
description: 'Daha fazla bilgi edinin: &lt; cassert&gt;'
title: '&lt;cassert&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cassert>
helpviewer_keywords:
- cassert header
ms.assetid: 6ead15a3-ac45-4075-be8e-350bca995c26
ms.openlocfilehash: e2b515fe492e6847c4d0cc5841dc43a2d879dd99
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325362"
---
# <a name="ltcassertgt"></a>&lt;cassert&gt;

C standart kitaplığı üst bilgisini içerir \<assert.h> ve ilgili adları `std` ad alanına ekler. Bu üst bilgiyi dahil etmek, C standart kitaplığı üstbilgisinde harici bağlantı kullanılarak belirtilen adların `std` ad alanında bildirilmesini sağlar.

> [!NOTE]
> \<assert.h>**`static_assert`** makroyu tanımlamaz.

## <a name="syntax"></a>Syntax

```cpp
#include <cassert>
```

## <a name="macros"></a>Makrolar

```cpp
#define assert(E)
```

### <a name="remarks"></a>Açıklamalar

`assert(E)`yalnızca bir sabittir, NDEBUG, `assert` son tanımlanan veya yeniden tanımlandı  **`true`**

## <a name="see-also"></a>Ayrıca bkz.

[onaylama makrosu, _assert _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)\
[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ standart kitaplığına genel bakış](../standard-library/cpp-standard-library-overview.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
