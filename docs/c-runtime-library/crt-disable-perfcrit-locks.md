---
title: _CRT_DISABLE_PERFCRIT_LOCKS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _CRT_DISABLE_PERFCRIT_LOCKS
- CRT_DISABLE_PERFCRIT_LOCKS
dev_langs:
- C++
helpviewer_keywords:
- CRT_DISABLE_PERFCRIT_LOCKS constant
- _CRT_DISABLE_PERFCRIT_LOCKS constant
ms.assetid: 36cc2d86-cdb1-4b2b-a03c-c0d3818e7c6f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 07962266c94743968ff407aa5be78f66e189f6aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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