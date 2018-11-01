---
title: '&lt;system_error&gt; tür tanımları'
ms.date: 11/04/2016
f1_keywords:
- system_error/std::generic_errno
ms.assetid: 28cf9f7d-9c28-4baa-a297-67c8260b07fb
ms.openlocfilehash: 95b2cb22d4fbff4f92cf28041e70ae599c318cbc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531068"
---
# <a name="ltsystemerrorgt-typedefs"></a>&lt;system_error&gt; tür tanımları

||
|-|
|[generic_errno](#generic_errno)|

## <a name="generic_errno"></a>  generic_errno

Posıx'te tarafından tanımlanan tüm hata kodu makroları için simgesel adlar sağlar numaralandırma temsil eden bir tür `<errno.h>`.

```cpp
typedef errc generic_error;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır [errc](../standard-library/system-error-enums.md#errc).

## <a name="see-also"></a>Ayrıca bkz.

[<system_error>](../standard-library/system-error.md)<br/>
