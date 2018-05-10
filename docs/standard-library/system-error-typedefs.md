---
title: '&lt;system_error&gt; tür tanımları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- system_error/std::generic_errno
ms.assetid: 28cf9f7d-9c28-4baa-a297-67c8260b07fb
ms.openlocfilehash: 6dab6e379d2b36ff7e4c2e7cdee581bd43488e41
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="ltsystemerrorgt-typedefs"></a>&lt;system_error&gt; tür tanımları

||
|-|
|[generic_errno](#generic_errno)|

## <a name="generic_errno"></a>  generic_errno

POSIX içinde tanımlanan tüm hata kodu makroları simgesel adları sağlar numaralandırması temsil eden bir tür `<errno.h>`.

```cpp
typedef errc generic_error;
```

### <a name="remarks"></a>Açıklamalar

Eşanlamlısı türüdür [errc](../standard-library/system-error-enums.md#errc).

## <a name="see-also"></a>Ayrıca bkz.

[<system_error>](../standard-library/system-error.md)<br/>
