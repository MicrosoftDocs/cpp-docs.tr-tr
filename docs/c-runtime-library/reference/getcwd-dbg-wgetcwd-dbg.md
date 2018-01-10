---
title: _getcwd_dbg, _wgetcwd_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wgetcwd_dbg
- _getcwd_dbg
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getcwd_dbg
- _wgetcwd_dbg
- getcwd_dbg
- wgetcwd_dbg
dev_langs: C++
helpviewer_keywords:
- wgetcwd_dbg function
- working directory
- _getcwd_dbg function
- getcwd_dbg function
- current working directory
- _wgetcwd_dbg function
- directories [C++], current working
ms.assetid: 8d5d151f-d844-4aa6-a28c-1c11a22dc00d
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7dfa0f619990045cd6ae1be4f800c2624fd9efe3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="getcwddbg-wgetcwddbg"></a>_getcwd_dbg, _wgetcwd_dbg
Hata ayıklama sürümleri [_getcwd, _wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md) işlevleri (yalnızca hata ayıklama sırasında kullanılabilir).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
char *_getcwd_dbg(   
   char *buffer,  
   int maxlen,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
wchar_t *_wgetcwd_dbg(   
   wchar_t *buffer,  
   int maxlen,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `buffer`  
 Yol için depolama konumu.  
  
 `maxlen`  
 Yolun karakter cinsinden en büyük uzunluğu: `char` için `_getcwd_dbg` ve `wchar_t` için `_wgetcwd_dbg`.  
  
 `blockType`  
 İstenen bellek bloğu türü: `_CLIENT_BLOCK` veya `_NORMAL_BLOCK`.  
  
 `filename`  
 İstenen ayırma işlemi kaynak dosyasının adını işaretçi veya `NULL`.  
  
 `linenumber`  
 Satır numarası ayırma işlemi istenen burada kaynak dosyasında veya `NULL`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi döndürür `buffer`. A `NULL` değeri belirten bir hata döndürür ve `errno` ya da ayarlamak `ENOMEM`, ayırmak için yeterli bellek olduğunu belirten `maxlen` bayt (olduğunda bir `NULL` bağımsız değişken olarak verilen `buffer`), veya `ERANGE`, yolun daha uzun olduğunu belirten `maxlen` karakter.  
  
 Daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `_getcwd_dbg` Ve `_wgetcwd_dbg` işlevleri aynı `_getcwd` ve `_wgetcwd` dışında `_DEBUG` olan tanımlı, bu işlevler hata ayıklama sürümünü kullanmanız `malloc` ve `_malloc_dbg` , bellek ayırmak için `NULL` ilk parametre olarak geçirilir. Daha fazla bilgi için bkz: [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 Çoğu durumda bu işlevleri açıkça çağırmak gerekmez. Bunun yerine, tanımlayabilirsiniz `_CRTDBG_MAP_ALLOC` bayrağı. Zaman `_CRTDBG_MAP_ALLOC` tanımlanır, çağrılar `_getcwd` ve `_wgetcwd` için eşleştirilir `_getcwd_dbg` ve `_wgetcwd_dbg`, sırasıyla ile `blockType` kümesine `_NORMAL_BLOCK`. Bu nedenle, öbek taşı olarak işaretlemek istediğiniz sürece bu işlevleri açıkça çağırın gerekmez `_CLIENT_BLOCK`. Daha fazla bilgi için bkz: [hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tgetcwd_dbg`|`_getcwd_dbg`|`_getcwd_dbg`|`_wgetcwd_dbg`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_getcwd_dbg`|\<crtdbg.h >|  
|`_wgetcwd_dbg`|\<crtdbg.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_getcwd, _wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [Dizin denetimi](../../c-runtime-library/directory-control.md)   
 [Yığın ayırma işlevleri sürümleri hata ayıklama](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)