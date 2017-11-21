---
title: _getdcwd_dbg, _wgetdcwd_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _getdcwd_dbg
- _wgetdcwd_dbg
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
apitype: DLLExport
f1_keywords:
- _getdcwd_dbg
- getdcwd_dbg
- _wgetdcwd_dbg
- wgetdcwd_dbg
dev_langs: C++
helpviewer_keywords:
- working directory
- _getdcwd_dbg function
- wgetdcwd_dbg function
- current working directory
- getdcwd_dbg function
- _wgetdcwd_dbg function
- directories [C++], current working
ms.assetid: 266bf6f0-0417-497f-963d-2e0f306d9385
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8afa6156185ac1d375834bdc22df35f2a94638fd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="getdcwddbg-wgetdcwddbg"></a>_getdcwd_dbg, _wgetdcwd_dbg
Hata ayıklama sürümleri [_getdcwd, _wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md) işlevleri (yalnızca hata ayıklama sırasında kullanılabilir).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
char *_getdcwd_dbg(  
   int drive,  
   char *buffer,  
   int maxlen,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
wchar_t *_wgetdcwd_dbg(  
   int drive,  
   wchar_t *buffer,  
   int maxlen,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `drive`  
 Disk sürücüsünün adı.  
  
 `buffer`  
 Yol için depolama konumu.  
  
 `maxlen`  
 Yolun karakter cinsinden en büyük uzunluğu: `char` için `_getdcwd_dbg` ve `wchar_t` için `_wgetdcwd_dbg`.  
  
 `blockType`  
 İstenen bellek bloğu türü: `_CLIENT_BLOCK` veya `_NORMAL_BLOCK`.  
  
 `filename`  
 İstenen ayırma işlemi kaynak dosyasının adını işaretçi veya `NULL`.  
  
 `linenumber`  
 Satır numarası ayırma işlemi istenen burada kaynak dosyasında veya `NULL`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi döndürür `buffer`. A `NULL` değeri belirten bir hata döndürür ve `errno` ya da ayarlamak `ENOMEM`, ayırmak için yeterli bellek olduğunu belirten `maxlen` bayt (olduğunda bir `NULL` bağımsız değişken olarak verilen `buffer`), veya `ERANGE`, yolun daha uzun olduğunu belirten `maxlen` karakter. Daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `_getdcwd_dbg` Ve `_wgetdcwd_dbg` işlevleri aynı `_getdcwd` ve `_wgetdcwd` dışında `_DEBUG` olan tanımlı, bu işlevler hata ayıklama sürümünü kullanmanız `malloc` ve `_malloc_dbg` , bellek ayırmak için `NULL` olarak geçirilen `buffer` parametresi. Daha fazla bilgi için bkz: [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 Çoğu durumda bu işlevleri açıkça çağırmak gerekmez. Bunun yerine, tanımlayabilirsiniz `_CRTDBG_MAP_ALLOC` bayrağı. Zaman `_CRTDBG_MAP_ALLOC` tanımlanır, çağrılar `_getdcwd` ve `_wgetdcwd` için eşleştirilir `_getdcwd_dbg` ve `_wgetdcwd_dbg`, sırasıyla ile `blockType` kümesine `_NORMAL_BLOCK`. Bu nedenle, öbek taşı olarak işaretlemek istediğiniz sürece bu işlevleri açıkça çağırın gerekmez `_CLIENT_BLOCK`. Daha fazla bilgi için bkz: [hata ayıklama yığınındaki blokları türleri](/visualstudio/debugger/crt-debug-heap-details).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tgetdcwd_dbg`|`_getdcwd_dbg`|`_getdcwd_dbg`|`_wgetdcwd_dbg`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_getdcwd_dbg`|\<crtdbg.h >|  
|`_wgetdcwd_dbg`|\<crtdbg.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_getdcwd, _wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md)   
 [Dizin denetimi](../../c-runtime-library/directory-control.md)   
 [Yığın ayırma işlevleri sürümleri hata ayıklama](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)