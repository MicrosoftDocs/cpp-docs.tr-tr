---
title: '&lt;cassert&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cassert>
helpviewer_keywords:
- cassert header
ms.assetid: 6ead15a3-ac45-4075-be8e-350bca995c26
ms.openlocfilehash: 58ebd91fb4fa32cf31d2c49429d0445b92fe0c82
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449915"
---
# <a name="ltcassertgt"></a>&lt;cassert&gt;

C Standart Kitaplığı başlığı \<onayı. h > içerir ve ilişkili adları `std` ad alanına ekler. Bu üst bilgiyi dahil etmek, C standart kitaplığı üstbilgisinde harici bağlantı kullanılarak belirtilen adların `std` ad alanında bildirilmesini sağlar.

> [!NOTE]
> \<onaylama. h >, `static_assert` makroyu tanımlamaz.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <cassert>
```

## <a name="macros"></a>Makrolar

```cpp
#define assert(E)
```

### <a name="remarks"></a>Açıklamalar

`assert(E)`yalnızca, ndebug tanımlanıyorsa `assert` veya yeniden tanımlandığında, ya da bool değerine dönüştürülmüş bir değer  **true**olarak değerlendirilirse bir sabittir.

## <a name="see-also"></a>Ayrıca bkz.

[onaylama makrosu, _Onay, _TatLı](../c-runtime-library/reference/assert-macro-assert-wassert.md)\
[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++Standart kitaplığa genel bakış](../standard-library/cpp-standard-library-overview.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
