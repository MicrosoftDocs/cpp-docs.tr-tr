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
ms.openlocfilehash: b484f068ce94ab7a2a637723641e1206072cf24b
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220276"
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
