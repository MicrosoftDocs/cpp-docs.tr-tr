---
title: _CRT_DISABLE_PERFCRIT_LOCKS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _CRT_DISABLE_PERFCRIT_LOCKS
- CRT_DISABLE_PERFCRIT_LOCKS
dev_langs:
- C++
helpviewer_keywords:
- CRT_DISABLE_PERFCRIT_LOCKS constant
- _CRT_DISABLE_PERFCRIT_LOCKS constant
ms.assetid: 36cc2d86-cdb1-4b2b-a03c-c0d3818e7c6f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 128403009595d85e44007d79c9110b5df530b45e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32386663"
---
# <a name="crtdisableperfcritlocks"></a>_CRT_DISABLE_PERFCRIT_LOCKS
Performans açısından kritik g/ç işlemlerinde kilitleme devre dışı bırakır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#define _CRT_DISABLE_PERFCRIT_LOCKS  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu simge tanımlama tek iş parçacıklı g/Ç-bağlı programlarda tek iş parçacıklı g/ç modeli varsaymak tüm g/ç işlemleri zorlayarak performansı artırabilir. Daha fazla bilgi için bkz: [birden çok iş parçacıklı kitaplık performansı](../c-runtime-library/multithreaded-libraries-performance.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Global Sabitler](../c-runtime-library/global-constants.md)