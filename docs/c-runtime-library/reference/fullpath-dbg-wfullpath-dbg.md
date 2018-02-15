---
title: _wfullpath_dbg olan _fullpath_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _wfullpath_dbg
- _fullpath_dbg
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
- wfullpath_dbg
- _wfullpath_dbg
- _fullpath_dbg
- fullpath_dbg
dev_langs:
- C++
helpviewer_keywords:
- _fullpath_dbg function
- relative file paths
- absolute paths
- fullpath_dbg function
- _wfullpath_dbg function
- wfullpath_dbg function
ms.assetid: 81f72f85-07da-4f5c-866a-598e0fb03f6b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 96ba8f7d9784bd4f6361159feaef3d855ebee1e3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="fullpathdbg-wfullpathdbg"></a>_fullpath_dbg, _wfullpath_dbg
Sürümleri [_fullpath, _wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md) hata ayıklama sürümünü kullanmak `malloc` bellek ayıramadı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
char *_fullpath_dbg(   
   char *absPath,  
   const char *relPath,  
   size_t maxLength,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
wchar_t *_wfullpath_dbg(   
   wchar_t *absPath,  
   const wchar_t *relPath,  
   size_t maxLength,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `absPath`  
 Mutlak veya tam yol adını içeren bir arabellek işaretçi veya `NULL`.  
  
 `relPath`  
 Göreli yol adı.  
  
 `maxLength`  
 Mutlak bir yol adı arabelleği maksimum uzunluğu (`absPath`). Bu uzunluğudur için bayt cinsinden `_fullpath` ancak geniş karakterler (`wchar_t`) için `_wfullpath`.  
  
 `blockType`  
 İstenen bellek bloğu türü: `_CLIENT_BLOCK` veya `_NORMAL_BLOCK`.  
  
 `filename`  
 İstenen ayırma işlemi kaynak dosyasının adını işaretçi veya `NULL`.  
  
 `linenumber`  
 Satır numarası ayırma işlemi istenen burada kaynak dosyasında veya `NULL`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Her işlevi bir işaretçi mutlak yol adı içeren bir arabellek döndürür (`absPath`). Bir hata varsa (örneğin, değer olarak aktarılırsa `relPath` geçersiz veya bulunamıyor, bir sürücü harfi içerir veya oluşturulan mutlak bir yol adının uzunluğu (`absPath`) değerinden daha büyük `maxLength`) işlevidöndürür`NULL`.  
  
## <a name="remarks"></a>Açıklamalar  
 `_fullpath_dbg` Ve `_wfullpath_dbg` işlevleri aynı `_fullpath` ve `_wfullpath` dışında `_DEBUG` olan tanımlı, bu işlevler hata ayıklama sürümünü kullanın `malloc`, `_malloc_dbg`, NULL ise bellek ayrılamıyor İlk parametre olarak geçirildi. Hata ayıklama özellikleri hakkında bilgi için `_malloc_dbg`, bkz: [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 Çoğu durumda bu işlevleri açıkça çağırmak gerekmez. Bunun yerine, tanımlayabilirsiniz `_CRTDBG_MAP_ALLOC` bayrağı. Zaman `_CRTDBG_MAP_ALLOC` tanımlanır, çağrılar `_fullpath` ve `_wfullpath` için eşleştirilir `_fullpath_dbg` ve `_wfullpath_dbg`, sırasıyla ile `blockType` kümesine `_NORMAL_BLOCK`. Bu nedenle, öbek taşı olarak işaretlemek istediğiniz sürece bu işlevleri açıkça çağırın gerekmez `_CLIENT_BLOCK`. Daha fazla bilgi için bkz: [hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tfullpath_dbg`|`_fullpath_dbg`|`_fullpath_dbg`|`_wfullpath_dbg`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`_fullpath_dbg`|\<crtdbg.h>|  
|`_wfullpath_dbg`|\<crtdbg.h>|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosya işleme](../../c-runtime-library/file-handling.md)   
 [_fullpath, _wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [Yığın ayırma işlevleri sürümleri hata ayıklama](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)