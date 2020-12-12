---
description: 'Daha fazla bilgi edinin: üretme sabitleri'
title: oluşturma Sabitleri
ms.date: 11/04/2016
f1_keywords:
- _P_NOWAIT
- _P_OVERLAY
- _P_WAIT
- _P_DETACH
- _P_NOWAITO
helpviewer_keywords:
- _P_OVERLAY constant
- P_DETACH constant
- P_OVERLAY constant
- P_NOWAIT constant
- _P_DETACH constant
- _P_NOWAIT constant
- _P_NOWAITO constant
- P_NOWAITO constant
- spawn constants
- P_WAIT constant
- _P_WAIT constant
ms.assetid: e0533e88-d362-46fc-b53c-5f193226d879
ms.openlocfilehash: 0bac30346c974fa63d65da78a097cb24768cb313
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276965"
---
# <a name="spawn-constants"></a>oluşturma Sabitleri

## <a name="syntax"></a>Syntax

```
#include <process.h>
```

## <a name="remarks"></a>Açıklamalar

`mode`Bağımsız değişkeni, bir oluşturma işleminden önce ve sırasında çağırma işlemi tarafından gerçekleştirilecek eylemi belirler. İçin aşağıdaki değerler `mode` mümkündür:

|Sabit|Anlamı|
|--------------|-------------|
|`_P_OVERLAY`|Yeni işlemle işlem çağırma, çağırma işlemini yok etme (çağrılarla aynı etkiye `_exec` ).|
|`_P_WAIT`|Yeni işlemin yürütülmesi tamamlanana kadar iş parçacığının çağrılmasını askıya alır (zaman uyumlu `_spawn` ).|
|`_P_NOWAIT`, `_P_NOWAITO`|Çağırma işlemini yeni işlemle aynı anda yürütmeye devam eder (zaman uyumsuz `_spawn` ).|
|`_P_DETACH`|Çağırma işlemini yürütmeye devam eder; Yeni işlem, konsol veya klavyeye erişim olmadan arka planda çalışır. `_cwait`Yeni işleme yönelik çağrılar başarısız olur. Bu bir zaman uyumsuz `_spawn` .|

## <a name="see-also"></a>Ayrıca bkz.

[_spawn, _wspawn Işlevleri](../c-runtime-library/spawn-wspawn-functions.md)<br/>
[Global sabitler](../c-runtime-library/global-constants.md)
