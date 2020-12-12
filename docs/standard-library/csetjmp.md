---
description: 'Daha fazla bilgi edinin: &lt; csetjmp&gt;'
title: '&lt;csetjmp&gt;'
ms.date: 11/04/2016
f1_keywords:
- <csetjmp>
helpviewer_keywords:
- csetjmp header
ms.assetid: 8f21fddd-5e9b-4219-a848-581cdd3569d9
ms.openlocfilehash: ebd3acefbdf96c8dd2b0cba569e7cd2ffc128d31
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324780"
---
# <a name="ltcsetjmpgt"></a>&lt;csetjmp&gt;

Standart C Kitaplığı üst bilgisini içerir \<setjmp.h> ve ilgili adları `std` ad alanına ekler.

## <a name="syntax"></a>Syntax

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
[C++ standart kitaplığına genel bakış](../standard-library/cpp-standard-library-overview.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
