---
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
ms.openlocfilehash: 50519ffe8e2de784a9596a1dc748741bbd4cd278
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613960"
---
# <a name="waitchild-waitgrandchild"></a>_WAIT_CHILD, _WAIT_GRANDCHILD

## <a name="syntax"></a>Sözdizimi

```

#include <process.h>

```

## <a name="remarks"></a>Açıklamalar

`_cwait` İşlevi (işlem kimliği biliniyorsa) herhangi bir işlem için beklenecek herhangi bir işlem tarafından kullanılabilir. Eylem bağımsız değişkeni aşağıdaki değerlerden biri olabilir:

|Sabit|Açıklama|
|--------------|-------------|
|`_WAIT_CHILD`|Çağırma işlemi, belirtilen yeni işlem sonlanana kadar bekler.|
|`_WAIT_GRANDCHILD`|Belirtilen yeni işlem ve bu yeni bir işlem tarafından oluşturulan tüm işlemler kadar işlem bekler arama sonlandırın.|

## <a name="see-also"></a>Ayrıca Bkz.

[_cwait](../c-runtime-library/reference/cwait.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)