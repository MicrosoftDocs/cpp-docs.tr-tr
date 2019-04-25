---
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
ms.openlocfilehash: 988cc5e1b982f0c5577db77ae94f1df46c95ec0e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62267891"
---
# <a name="spawn-constants"></a>oluşturma Sabitleri

## <a name="syntax"></a>Sözdizimi

```
#include <process.h>
```

## <a name="remarks"></a>Açıklamalar

`mode` Bağımsız değişken önce ve üretme işlemi sırasında arama işlemi tarafından gerçekleştirilecek eylemi belirler. Aşağıdaki değerleri `mode` mümkündür:

|Sabit|Açıklama|
|--------------|-------------|
|`_P_OVERLAY`|Çağırma işlemi ile yeni bir işlem, arama işlemi yok etme yer paylaşımları (aynı efekt olarak `_exec` çağırır).|
|`_P_WAIT`|Yeni işlem yürütme işlemi tamamlanana kadar çağıran iş parçacığını askıya alır (zaman uyumlu `_spawn`).|
|`_P_NOWAIT`, `_P_NOWAITO`|Yeni işlem aynı anda arama işlemi yürütmeye devam eder (zaman uyumsuz `_spawn`).|
|`_P_DETACH`|Arama işlemi yürütmeye devam eder; Yeni işlem konsolunda veya klavye erişim olmaksızın arka planda çalıştırılır. Çağrılar `_cwait` karşı yeni bir işlem başarısız olur. Zaman uyumsuz budur `_spawn`.|

## <a name="see-also"></a>Ayrıca bkz.

[_spawn, _wspawn İşlevleri](../c-runtime-library/spawn-wspawn-functions.md)<br/>
[Global Sabitler](../c-runtime-library/global-constants.md)
