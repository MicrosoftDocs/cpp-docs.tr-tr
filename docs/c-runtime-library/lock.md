---
title: _Lock | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 069a13626c2fcfab62c47d3142f2f5b810f0945a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="lock"></a>_lock
Çoklu iş parçacığı kilit alır.  
  
> [!IMPORTANT]
>  Bu işlev artık kullanılmıyor. Visual Studio 2015'te başlayarak, CRT kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __cdecl _lock  
   int locknum  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`locknum`  
 Kilit edinmeye tanımlayıcısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Kilidi zaten alınmış, bu yöntem kilit yine de alır ve bir iç C çalışma zamanı (CRT) hataya neden olur. Yöntemin bir kilidi alamazsa, önemli bir hata ile çıkar ve hata kodu ayarlar `_RT_LOCK`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Kaynak:** mlock.c  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alfabetik işlev başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [_unlock](../c-runtime-library/unlock.md)