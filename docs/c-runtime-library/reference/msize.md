---
title: _msize | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _msize
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- msize
- _msize
dev_langs:
- C++
helpviewer_keywords:
- memory blocks
- msize function
- _msize function
ms.assetid: 02b1f89e-d0d7-4f12-938a-9eeba48a0f88
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2fdf8e5b6c9b0f6b63ac14784a90a4dc94b6abdc
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="msize"></a>_msize
Yığın ayrılan bellek bloğu boyutu döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      size_t _msize(  
   void *memblock   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `memblock`  
 Bellek bloğu işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_msize` Boyutu (bayt) imzalanmamış tamsayı olarak döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `_msize` İşlevi için bir çağrı tarafından ayrılan bellek bloğu bayt cinsinden boyutu döndürüyor `calloc`, `malloc`, veya `realloc`.  
  
 Uygulama hata ayıklama sürümü C çalışma zamanı kitaplıkları ile bağlandığında `_msize` çözümler [_msize_dbg](../../c-runtime-library/reference/msize-dbg.md). Öbek hata ayıklama işlemi sırasında nasıl yönetilir hakkında daha fazla bilgi için bkz: [CRT hata ayıklama yığını](/visualstudio/debugger/crt-debug-heap-details).  
  
 Bu işlev, parametre doğrular. Varsa `memblock` null işaretçi `_msize` açıklandığı gibi bir geçersiz parametre işleyiciyi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Hata işleniyorsa işlevi ayarlar `errno` için `EINVAL` ve -1 döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_msize`|\<malloc.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [realloc](../../c-runtime-library/reference/realloc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bellek ayırma](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [siteyi g_enişlet](../../c-runtime-library/reference/expand.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)