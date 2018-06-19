---
title: _local_unwind2 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _local_unwind2
apilocation:
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- _local_unwind2
- local_unwind2
dev_langs:
- C++
helpviewer_keywords:
- _local_unwind2 function
- local_unwind2 function
ms.assetid: 44f1fa82-e01e-490f-a6e6-18fc6811c28c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5bee1decf5b5a3676e6111960282c19e87628c48
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32391385"
---
# <a name="localunwind2"></a>_local_unwind2
İç CRT işlevi. Belirtilen kapsam tabloda listelenen tüm sonlandırma işleyicileri çalışır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void _local_unwind2(  
   PEXCEPTION_REGISTRATION xr,  
   int stop  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in] `xr`  
 Bir kapsam tablo ile ilişkilendirilmiş bir kaydolma kaydı.  
  
 [in] `stop`  
 Yeri gösteren sözcük düzeyi `_local_unwind2` durdurmanız gerekir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem yalnızca çalışma zamanı ortamı tarafından kullanılır. Yöntemi, kodunuzda çağırmayın.  
  
 Sonlandırma işleyicileri bu yöntem yürütür, geçerli sözcük düzeyinde başlar ve works kendi şekilde düzeyi, ulaşana kadar sözcük düzeylerinde tarafından belirtilir `stop`. Sonlandırma işleyicileri tarafından gösterilen düzeyinde yürütmez `stop`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alfabetik İşlev Başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)