---
title: oluşturma sabitleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _P_NOWAIT
- _P_OVERLAY
- _P_WAIT
- _P_DETACH
- _P_NOWAITO
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f3a069f9f29f6fd15c3ce21111a37757519af229
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="spawn-constants"></a>oluşturma Sabitleri
## <a name="syntax"></a>Sözdizimi  
  
```  
#include <process.h>  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `mode` Bağımsız değişkeni önce ve oluşturma işlemi sırasında arama işlemi tarafından gerçekleştirilecek eylemi belirler. Aşağıdaki değerleri `mode` mümkündür:  
  
|Sabit|Açıklama|  
|--------------|-------------|  
|`_P_OVERLAY`|Yeni bir işlem olan işlem çağrılırken, arama işlemi yok etme yer paylaşımları (aynı efekt olarak `_exec` çağrıları).|  
|`_P_WAIT`|Yeni işlem yürütme işlemi tamamlanana kadar çağıran iş parçacığı askıya alır (zaman uyumlu `_spawn`).|  
|`_P_NOWAIT`, `_P_NOWAITO`|Eşzamanlı olarak yeni bir işlem çağırma işlemi yürütmeye devam eder (zaman uyumsuz `_spawn`).|  
|`_P_DETACH`|Arama işlemi gerçekleştirilmeye devam eder; Yeni işlem konsolunu veya klavye, hiçbir erişim arka planda çalıştırılır. Çağrılar `_cwait` karşı yeni bir işlem başarısız olur. Zaman uyumsuz bir budur `_spawn`.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_spawn, _wspawn işlevleri](../c-runtime-library/spawn-wspawn-functions.md)   
 [Global Sabitler](../c-runtime-library/global-constants.md)