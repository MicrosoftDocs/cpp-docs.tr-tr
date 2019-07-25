---
title: '&lt;csetjmp&gt;'
ms.date: 11/04/2016
f1_keywords:
- <csetjmp>
helpviewer_keywords:
- csetjmp header
ms.assetid: 8f21fddd-5e9b-4219-a848-581cdd3569d9
ms.openlocfilehash: 8f3a1a622776d5dd2ef3d22aaa3436933c5a7137
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452392"
---
# <a name="ltcsetjmpgt"></a>&lt;csetjmp&gt;

Standart C Kitaplığı üstbilgisi \<setjmp. h > içerir ve ilişkili adları `std` ad alanına ekler.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <csetjmp>

using jmp_buf = see below;
```

## <a name="functions"></a>İşlevler

```cpp
[[noreturn]] void longjmp(jmp_buf env, int val);
```

## <a name="macros"></a>Makrolar

```cpp
#define setjmp(env)
```

## <a name="remarks"></a>Açıklamalar

Bu üstbilginin dahil edilmesi, standart C Kitaplığı üstbilgisinde harici bağlantı kullanılarak belirtilen adların `std` ad alanında bildirilmesini sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++Standart kitaplığa genel bakış](../standard-library/cpp-standard-library-overview.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
