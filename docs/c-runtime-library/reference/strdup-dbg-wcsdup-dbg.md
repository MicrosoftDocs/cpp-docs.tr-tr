---
title: _strdup_dbg, _wcsdup_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _strdup_dbg
- _wcsdup_dbg
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
- _wcsdup_dbg
- strdup_dbg
- _strdup_dbg
- wcsdup_dbg
dev_langs: C++
helpviewer_keywords:
- _wcsdup_dbg function
- stdup_dbg function
- copying strings
- duplicating strings
- strings [C++], copying
- strings [C++], duplicating
- _strdup_dbg function
- wcsdup_dbg function
ms.assetid: 681db70c-d124-43ab-b83e-5eeea9035097
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: abc8cfa4e21ea0a263224628a1e896493bd902e0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="strdupdbg-wcsdupdbg"></a>_strdup_dbg, _wcsdup_dbg
Sürümleri [_strdup ve _wcsdup](../../c-runtime-library/reference/strdup-wcsdup-mbsdup.md) hata ayıklama sürümünü kullanmak `malloc`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
char *_strdup_dbg(  
   const char *strSource,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
wchar_t *_wcsdup_dbg(  
   const wchar_t *strSource,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `strSource`  
 Sonlandırılmış kaynak dizesi.  
  
 `blockType`  
 İstenen bellek bloğu türü: `_CLIENT_BLOCK` veya `_NORMAL_BLOCK`.  
  
 `filename`  
 İşaretçi ayırma işlemi ya da NULL istenen kaynak dosyasının adı.  
  
 `linenumber`  
 Satır numarası burada ayırma işlemi istendi, ancak kaynak dosyasında veya NULL.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu işlevlerin her biri bir işaretçi kopyalanan dize için depolama konumunu döndürür veya `NULL` depolama ayırdığınızda.  
  
## <a name="remarks"></a>Açıklamalar  
 `_strdup_dbg` Ve `_wcsdup_dbg` işlevleri aynı `_strdup` ve `_wcsdup` dışında `_DEBUG` olan tanımlı, bu işlevler hata ayıklama sürümünü kullanmanız `malloc`, `_malloc_dbg`, için bellek ayrılamadı Yinelenen dizesi. Hata ayıklama özellikleri hakkında bilgi için `_malloc_dbg`, bkz: [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 Çoğu durumda bu işlevleri açıkça çağırmak gerekmez. Bunun yerine, bayrağı tanımlayabilirsiniz `_CRTDBG_MAP_ALLOC`. Zaman `_CRTDBG_MAP_ALLOC` tanımlanır, çağrılar `_strdup` ve `_wcsdup` için eşleştirilir `_strdup_dbg` ve `_wcsdup_dbg`, sırasıyla ile `blockType` kümesine `_NORMAL_BLOCK`. Bu nedenle, öbek taşı olarak işaretlemek istediğiniz sürece bu işlevleri açıkça çağırın gerekmez `_CLIENT_BLOCK`. Blok türleri hakkında daha fazla bilgi için bkz: [hata ayıklama yığınındaki blokları türlerini](/visualstudio/debugger/crt-debug-heap-details).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsdup_dbg`|`_strdup_dbg`|`_mbsdup`|`_wcsdup_dbg`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_strdup_dbg`, `_wcsdup_dbg`|\<crtdbg.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri hata ayıklama [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)   
 [_strdup, _wcsdup, _mbsdup](../../c-runtime-library/reference/strdup-wcsdup-mbsdup.md)   
 [Yığın ayırma işlevleri sürümleri hata ayıklama](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)