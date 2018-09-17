---
title: _Lock | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _lock
apilocation:
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- msvcr90.dll
- msvcr80.dll
- msvcr110.dll
- msvcrt.dll
- msvcr120_clr0400.dll
apitype: DLLExport
f1_keywords:
- lock
- _lock
dev_langs:
- C++
helpviewer_keywords:
- lock function
- _lock function
ms.assetid: 29f77c37-30de-4b3d-91b6-030216e645a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 57b1cfca4740b3190c2afb8eb557fabded3895bd
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707622"
---
# <a name="lock"></a>_lock
Çoklu iş parçacığı kilidi alır.  
  
> [!IMPORTANT]
>  Bu işlev artık kullanılmıyor. Visual Studio 2015'te başlayarak, CRT içinde kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __cdecl _lock  
   int locknum  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
*locknum*<br/>
[in] Kilit almaya tanımlayıcısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Kilidi zaten alınmış, bu yöntem kilit yine de alır ve bir iç C çalışma zamanı (CRT) hata neden olur. Yöntem bir kilit alınamıyor, önemli bir hata ile çıkar ve hata kodunu ayarlar `_RT_LOCK`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Kaynak:** mlock.c  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alfabetik işlev başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [_unlock](../c-runtime-library/unlock.md)