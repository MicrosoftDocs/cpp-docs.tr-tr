---
title: _WAIT_CHILD, _WAIT_GRANDCHILD | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _WAIT_GRANDCHILD
- WAIT_CHILD
- WAIT_GRANDCHILD
- _WAIT_CHILD
dev_langs:
- C++
helpviewer_keywords:
- WAIT_CHILD constant
- WAIT_GRANDCHILD constant
- _WAIT_CHILD constant
- _WAIT_GRANDCHILD constant
ms.assetid: 7acd96fa-d118-4339-bb00-e5afaf286945
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7dd7b3fab51c382413c507831572afedd824c3f7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018346"
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