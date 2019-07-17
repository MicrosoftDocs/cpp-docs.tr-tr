---
title: '&lt;cassert&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cassert>
helpviewer_keywords:
- cassert header
ms.assetid: 6ead15a3-ac45-4075-be8e-350bca995c26
ms.openlocfilehash: 14dda03e835ec411013b2d827bd1ccaa77f8982e
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245013"
---
# <a name="ltcassertgt"></a>&lt;cassert&gt;

Standart C Kitaplığı üstbilgisi içerir \<assert.h > ve ilişkili adlar ekler `std` ad alanı. Bu üstbilginin dahil sağlar, standart C Kitaplığı üstbilgisinde harici bağlantı kullanılarak bildirilen adların bildirilir `std` ad alanı.

> [!NOTE]
> \<Assert.h > tanımlamıyor `static_assert` makrosu.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <cassert>
```

## <a name="macros"></a>Makrolar

```cpp
#define assert(E)
```

### <a name="remarks"></a>Açıklamalar

`assert(E)` yalnızca NDEBUG tanımlanmışsa sabittir burada `assert` son tanımlanan veya yeniden tanımlandı, veya *E* türüne dönüştürülmüş bool değerlendirilen **true**.

## <a name="see-also"></a>Ayrıca bkz.

[assert Makrosu, _assert, _wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)<br/>
[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığına Genel Bakış](../standard-library/cpp-standard-library-overview.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
