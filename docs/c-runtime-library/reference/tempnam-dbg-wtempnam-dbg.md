---
title: _tempnam_dbg, _wtempnam_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _wtempnam_dbg
- _tempnam_dbg
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
- wtempnam_dbg
- tempnam_dbg
- _tempnam_dbg
- _wtempnam_dbg
dev_langs:
- C++
helpviewer_keywords:
- file names [C++], creating temporary
- tempnam_dbg function
- temporary files, creating
- file names [C++], temporary
- wtempnam_dbg function
- _tempnam_dbg function
- _wtempnam_dbg function
ms.assetid: e3760bb4-bb01-4808-b689-2c45af56a170
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7fc8ef1427937ce4f263c81c55100045b30d24a3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="tempnamdbg-wtempnamdbg"></a>_tempnam_dbg, _wtempnam_dbg
İşlev sürümlerini [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) hata ayıklama sürümünü kullanmak `malloc, _malloc_dbg`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
char *_tempnam_dbg(  
   const char *dir,  
   const char *prefix,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
wchar_t *_wtempnam_dbg(  
   const wchar_t *dir,  
   const wchar_t *prefix,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dir`  
 Dosya adında hiçbir TMP ortam değişkeni ise veya TMP geçerli bir dizin değil ise kullanılan yol.  
  
 `prefix`  
 Bekletilen tarafından döndürülen adlarına olacaktır dize `_tempnam`.  
  
 `blockType`  
 İstenen bellek bloğu türü: `_CLIENT_BLOCK` veya `_NORMAL_BLOCK`.  
  
 `filename`  
 İstenen ayırma işlemi kaynak dosyasının adını işaretçi veya `NULL`.  
  
 `linenumber`  
 Satır numarası ayırma işlemi istenen burada kaynak dosyasında veya `NULL`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Her işlev işaretçisi oluşturulan adı döndürür veya `NULL` bir hata olduğunda. Belirtilen TMP ortam değişkeni ve içinde geçersiz dizin adı ise hata oluşabilir `dir` parametresi.  
  
> [!NOTE]
>  `free` (veya `free_dbg`) tarafından ayrılmış işaretçileri için çağrılması gerekmez `_tempnam_dbg` ve `_wtempnam_dbg`.  
  
## <a name="remarks"></a>Açıklamalar  
 `_tempnam_dbg` Ve `_wtempnam_dbg` işlevleri aynı `_tempnam` ve `_wtempnam` dışında `_DEBUG` olan tanımlı, bu işlevler hata ayıklama sürümünü kullanmanız `malloc` ve `_malloc_dbg`, bellek, ayırmak için `NULL` ilk parametre olarak geçirilir. Daha fazla bilgi için bkz: [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 Çoğu durumda bu işlevleri açıkça çağırmak gerekmez. Bunun yerine, bayrağı tanımlayabilirsiniz `_CRTDBG_MAP_ALLOC`. Zaman `_CRTDBG_MAP_ALLOC` tanımlanır, çağrılar `_tempnam` ve `_wtempnam` için eşleştirilir `_tempnam_dbg` ve `_wtempnam_dbg`, sırasıyla ile `blockType` kümesine `_NORMAL_BLOCK`. Bu nedenle, öbek taşı olarak işaretlemek istediğiniz sürece bu işlevleri açıkça çağırın gerekmez `_CLIENT_BLOCK`. Daha fazla bilgi için bkz: [hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ttempnam_dbg`|`_tempnam_dbg`|`_tempnam_dbg`|`_wtempnam_dbg`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_tempnam_dbg`, `_wtempnam_dbg`|\<crtdbg.h>|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [Yığın ayırma işlevleri sürümleri hata ayıklama](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)