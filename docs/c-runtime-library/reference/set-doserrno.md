---
title: _set_doserrno | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _set_doserrno
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_doserrno
- set_doserrno
dev_langs:
- C++
helpviewer_keywords:
- _set_doserrno function
- doserrno global variable
- set_doserrno function
- _doserrno global variable
ms.assetid: 8686c159-3797-4705-a53e-7457869ca6f3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f31e353bc901a2a29d80f4c02ff9e860ed5f6fa
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="setdoserrno"></a>_set_doserrno
Değerini ayarlar [_doserrno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) genel değişkeni.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t _set_doserrno(   
   int value   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in] `value`  
 Yeni değeri `_doserrno`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Olası değerler Errno.h içinde tanımlanır.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|---------------------|  
|`_set_doserrno`|\<stdlib.h>|\<errno.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_get_doserrno](../../c-runtime-library/reference/get-doserrno.md)   
 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)