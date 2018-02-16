---
title: _get_pgmptr | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _get_pgmptr
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
- get_pgmptr
- _get_pgmptr
dev_langs:
- C++
helpviewer_keywords:
- get_pgmptr function
- _get_pgmptr function
- pgmptr global variable
- _pgmptr global variable
ms.assetid: 29f16a9f-a685-4721-add3-7fad4f67eece
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5c5fc146c3b1385879172ecd9e2c6862bca135d0
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="getpgmptr"></a>_get_pgmptr
Geçerli değerini alır `_pgmptr` genel değişkeni.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t _get_pgmptr(   
   char **pValue   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [out] `pValue`  
 Geçerli değeri ile doldurulması için bir dize için bir işaretçi `_pgmptr` değişkeni.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır döndürür; hatasında bir hata kodu. Varsa `pValue` olan `NULL`, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev devam etmek için yürütülmesine izin veriliyorsa, ayarlar `errno` için `EINVAL` ve döndürür `EINVAL`.  
  
## <a name="remarks"></a>Açıklamalar  
 Yalnızca çağrısı `_get_pgmptr` programınızın dar giriş noktası varsa, ister `main()` veya `WinMain()`. `_pgmptr` Genel değişkeni işlemle ilişkili yürütülebilir dosyanın tam yolunu içerir. Daha fazla bilgi için bkz: [_pgmptr, _wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_get_pgmptr`|\<stdlib.h>|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_get_wpgmptr](../../c-runtime-library/reference/get-wpgmptr.md)
