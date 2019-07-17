---
title: '&lt;csetjmp&gt;'
ms.date: 11/04/2016
f1_keywords:
- <csetjmp>
helpviewer_keywords:
- csetjmp header
ms.assetid: 8f21fddd-5e9b-4219-a848-581cdd3569d9
ms.openlocfilehash: 3eba0b4521c0abf414de1416f02039a67c896644
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244513"
---
# <a name="ltcsetjmpgt"></a>&lt;csetjmp&gt;

Standart C Kitaplığı üstbilgisi içerir \<setjmp.h > ve ilişkili adlar ekler `std` ad alanı.

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

Bu üstbilginin dahil sağlar, standart C Kitaplığı üstbilgisinde harici bağlantı kullanılarak bildirilen adların bildirilir `std` ad alanı.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığına Genel Bakış](../standard-library/cpp-standard-library-overview.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
