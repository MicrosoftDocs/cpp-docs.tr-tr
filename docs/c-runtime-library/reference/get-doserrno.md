---
title: _get_doserrno | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _get_doserrno
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
- _get_doserrno
- get_doserrno
dev_langs: C++
helpviewer_keywords:
- get_doserrno function
- _get_doserrno function
ms.assetid: 7fec7be3-6e39-4181-846b-8ef24489361c
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c8eff0ac1a97c9a1d48b82601eb0d6dc0bb8bed0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="getdoserrno"></a>_get_doserrno
İçine çevrilen önce işletim sistemi tarafından döndürülen hata değerini alır bir `errno` değeri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t _get_doserrno(   
   int * pValue   
);   
```  
  
#### <a name="parameters"></a>Parametreler  
 [out]`pValue`  
 Tamsayı geçerli değeri ile doldurulması için bir işaretçi `_doserrno` genel makrosu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Varsa `_get_doserrno` başarılı, sıfır döndürür; başarısız olursa bir hata kodu döndürür. Varsa `pValue` olan `NULL`, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev devam etmek için yürütülmesine izin veriliyorsa, ayarlar `errno` için `EINVAL` ve döndürür `EINVAL`.  
  
## <a name="remarks"></a>Açıklamalar  
 `_doserrno` Genel makrosu CRT başlatma sırasında sıfır olarak ayarlandığında, yürütme işleminden önce başlar. Bir işletim sistemi hata veren tüm sistem düzeyindeki işlevi çağrı tarafından döndürülen işletim sistemi hata değerini ayarlayın ve onu hiç yürütme sırasında sıfır sıfırlanır. Döndürülen bir işlev tarafından her zaman açık olduğunda hata değerini denetlemek için kod yazma `_doserrno` kullanarak [_set_doserrno](../../c-runtime-library/reference/set-doserrno.md) işlev çağrısı önce. Başka bir işlev çağrısı üzerine çünkü `_doserrno`, kullanarak değerini denetleyin `_get_doserrno` işlev çağrısının hemen sonra.  
  
 Öneririz [_get_errno](../../c-runtime-library/reference/get-errno.md) yerine `_get_doserrno` taşınabilir hata kodları için.  
  
 Olası değerlerini `_doserrno` tanımlanan \<errno.h >.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|---------------------|  
|`_get_doserrno`|\<stdlib.h >, \<cstdlib > (C++)|\<errno.h >, \<cerrno > (C++)|  
  
 `_get_doserrno`bir Microsoft uzantısıdır. Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_set_doserrno](../../c-runtime-library/reference/set-doserrno.md)   
 [errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)