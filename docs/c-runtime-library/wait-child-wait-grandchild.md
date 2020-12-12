---
description: 'Hakkında daha fazla bilgi edinin: _WAIT_CHILD _WAIT_GRANDCHILD'
title: _WAIT_CHILD, _WAIT_GRANDCHILD
ms.date: 11/04/2016
f1_keywords:
- _WAIT_GRANDCHILD
- WAIT_CHILD
- WAIT_GRANDCHILD
- _WAIT_CHILD
helpviewer_keywords:
- WAIT_CHILD constant
- WAIT_GRANDCHILD constant
- _WAIT_CHILD constant
- _WAIT_GRANDCHILD constant
ms.assetid: 7acd96fa-d118-4339-bb00-e5afaf286945
ms.openlocfilehash: b14586232258f635b428b6c197213782591c8af1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181663"
---
# <a name="_wait_child-_wait_grandchild"></a>_WAIT_CHILD, _WAIT_GRANDCHILD

## <a name="syntax"></a>Syntax

```
#include <process.h>
```

## <a name="remarks"></a>Açıklamalar

`_cwait`İşlevi herhangi bir işlem tarafından herhangi bir işlem için beklemek için kullanılabilir (Işlem kimliği biliniyorsa). Eylem bağımsız değişkeni aşağıdaki değerlerden biri olabilir:

|Sabit|Anlamı|
|--------------|-------------|
|`_WAIT_CHILD`|Çağıran işlem, belirtilen yeni işlem sonlanana kadar bekler.|
|`_WAIT_GRANDCHILD`|Çağıran işlem, belirtilen yeni işlem ve bu yeni işlem tarafından oluşturulan tüm işlemler bitene kadar bekler.|

## <a name="see-also"></a>Ayrıca bkz.

[_cwait](../c-runtime-library/reference/cwait.md)<br/>
[Global sabitler](../c-runtime-library/global-constants.md)
