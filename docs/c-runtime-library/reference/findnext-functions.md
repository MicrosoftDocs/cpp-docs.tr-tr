---
title: _findnext, _findnext32, _findnext32i64, _findnext64, _findnext64i32, _findnexti64, _wfindnext, _wfindnext32, _wfindnext32i64, _wfindnext64, _wfindnext64i32, _wfindnexti64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wfindnext
- _findnext
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- findnext
- _wfindnext32i64
- _tfindnext64i32
- findnext32
- findnext32i64
- wfindnext64i32
- _wfindnext
- tfindnext64
- findnexti64
- _findnexti64
- _tfindnexti64
- _findnext64i32
- tfindnexti64
- tfindnext32
- _wfindnext64i32
- findnext64i32
- _findnext
- _tfindnext32i64
- _wfindnext64
- wfindnext
- wfindnext32
- tfindnext32i64
- _findnext64
- _tfindnext64
- _wfindnext32
- findnext64
- _findnext32i64
- tfindnext
- wfindnexti64
- tfindnext64i32
- _tfindnext32
- wfindnext32i64
- wfindnext64
- _wfindnexti64
- _tfindnext
- _findnext32
dev_langs: C++
helpviewer_keywords:
- _wfindnexti64 function
- _tfindnext32 function
- wfindnexti64 function
- _wfindnext32i64 function
- findnext32i64 function
- tfindnext64i32 function
- _tfindnext64i32 function
- _findnext function
- findnext64i32 function
- _tfindnext function
- findnext32 function
- tfindnext32 function
- _findnext32 function
- _tfindnext32i64 function
- _wfindnext function
- tfindnext function
- _findnext64 function
- findnext64 function
- _findnext64i32 function
- wfindnext32i64 function
- findnext function
- wfindnext32 function
- _wfindnext64i32 function
- findnexti64 function
- _wfindnext64 function
- _findnext32i64 function
- _findnexti64 function
- _tfindnext64 function
- wfindnext64i32 function
- tfindnexti64 function
- wfindnext64 function
- wfindnext function
- tfindnext64 function
- _wfindnext32 function
- tfindnext32i64 function
- _tfindnexti64 function
ms.assetid: 75d97188-5add-4698-a46c-4c492378f0f8
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9b095eabd6c0875bad0b3b42f488e36451f02bb3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="findnext-findnext32-findnext32i64-findnext64-findnext64i32-findnexti64-wfindnext-wfindnext32-wfindnext32i64-wfindnext64-wfindnext64i32-wfindnexti64"></a>_findnext, _findnext32, _findnext32i64, _findnext64, _findnext64i32, _findnexti64, _wfindnext, _wfindnext32, _wfindnext32i64, _wfindnext64, _wfindnext64i32, _wfindnexti64
Sonraki adı varsa, eşleşen bulma `filespec` önceki çağrı değişkeninde [_findfirst](../../c-runtime-library/reference/findfirst-functions.md)ve ardından alter `fileinfo` yapısı içeriği uygun şekilde.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _findnext(  
   intptr_t handle,  
   struct _finddata_t *fileinfo   
);  
int _findnext32(  
   intptr_t handle,  
   struct _finddata32_t *fileinfo   
);  
int _findnext64(  
   intptr_t handle,  
   struct __finddata64_t *fileinfo   
);  
int _findnexti64(  
   intptr_t handle,  
   struct __finddatai64_t *fileinfo   
);  
int _findnext32i64(  
   intptr_t handle,  
   struct _finddata32i64_t *fileinfo   
);  
int _findnext64i32(  
   intptr_t handle,  
   struct _finddata64i32_t *fileinfo   
);  
int _wfindnext(  
   intptr_t handle,  
   struct _wfinddata_t *fileinfo   
);  
int _wfindnext32(  
   intptr_t handle,  
   struct _wfinddata32_t *fileinfo   
);  
int _wfindnext64(  
   intptr_t handle,  
   struct _wfinddata64_t *fileinfo   
);  
int _wfindnexti64(  
   intptr_t handle,  
   struct _wfinddatai64_t *fileinfo   
);  
int _wfindnext32i64(  
   intptr_t handle,  
   struct _wfinddatai64_t *fileinfo   
);  
int _wfindnext64i32(  
   intptr_t handle,  
   struct _wfinddata64i32_t *fileinfo   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `handle`  
 Önceki bir çağrı tarafından döndürülen arama tanıtıcısıyla `_findfirst`.  
  
 `fileinfo`  
 Dosya bilgileri arabelleği.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, 0 döndürür. Aksi takdirde, -1 döndürür ve ayarlar `errno` hatanın yapısını gösteren bir değer. Olası hata kodları, aşağıdaki tabloda gösterilmiştir.  
  
 `EINVAL`  
 Geçersiz parametre: `fileinfo` olan `NULL`. Veya, işletim sistemi beklenmeyen bir hata döndürdü.  
  
 `ENOENT`  
 Daha fazla eşleşen dosyaları bulunamadı.  
  
 `ENOMEM`  
 Yeterli bellek yok veya dosya adı uzunluğu aşıldı `MAX_PATH`.  
  
 Geçersiz bir parametre geçtiyse, bu işlevler geçersiz parametre işleyicisi açıklandığı gibi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız [_findclose](../../c-runtime-library/reference/findclose.md) kullanarak tamamladıktan sonra `_findfirst` veya `_findnext` işlevi (veya tüm çeşitleri). Bu, uygulamanızda bu işlevler tarafından kullanılan kaynakları serbest bırakır.  
  
 Bu işlevleri varyasyonları `w` öneki joker karakter sürümleri; Aksi halde, karşılık gelen tek baytlı işlevleri aynı olur.  
  
 Bu işlevler varyasyonları 32 bit veya 64-bit saat türleri ve 32 bit veya 64-bit dosya boyutunu destekler. İlk sayısal son ekten (`32` veya `64`) zaman boyutu gösteren türü; kullanılan ikinci soneki ya da `i32` veya `i64`, belirten olup dosya boyutu 32 bit veya 64 bit tamsayı olarak temsil edilir. Sürümler 32 bit ve 64-bit saat türleri ve dosya boyutları destekleyen hakkında bilgi için aşağıdaki tabloya bakın. Bir 64-bit süre türünü kullanan değişimlerine 23:59:59, 31 Aralık 3000 UTC yukarı ifade için dosya oluşturma tarihleri izin; Bu yalnızca 32-bit zaman türleri kullanma ile 23:59:59 18 Ocak 2038, UTC tarihleri gösteren ise. Gece yarısından, 1 Ocak 1970'ten, bu işlevler için tarih aralığını alt sınırdır.  
  
 Zaman boyutu açıkça belirtmek, kullanın sürümlerini kullanmak üzere özel bir nedeniniz yoksa `_findnext` veya `_wfindnext` veya 3 GB'den büyük dosya boyutlarına desteklemeniz gerekiyorsa, kullanın `_findnexti64` veya `_wfindnexti64`. Bu işlevler 64-bit süre türünü kullanın. Önceki sürümlerde, bu işlevlerin bir 32 bit time türü kullanılır. Bir uygulama için önemli bir değişiklik olursa tanımlayabilir `_USE_32BIT_TIME_T` eski davranışı elde etmek üzere. Varsa `_USE_32BIT_TIME_T` tanımlanan `_findnext`, `_finnexti64` ve karşılık gelen Unicode sürümlerine 32-bit saatini kullanın.  
  
### <a name="time-type-and-file-length-type-variations-of-findnext"></a>Saat türü ve dosya uzunluğu türü _findnext varyasyonları  
  
|İşlevler|`_USE_32BIT_TIME_T`tanımlanan?|Zaman türü|Dosya uzunluğu türü|  
|---------------|----------------------------------|---------------|----------------------|  
|`_findnext`, `_wfindnext`|Tanımlı değil|64 bit|32 bit:|  
|`_findnext`, `_wfindnext`|Tanımlı|32 bit:|32 bit:|  
|`_findnext32`, `_wfindnext32`|Makro tanımı tarafından etkilenen değil|32 bit:|32 bit:|  
|`_findnext64`, `_wfindnext64`|Makro tanımı tarafından etkilenen değil|64 bit|64 bit|  
|`_findnexti64`, `_wfindnexti64`|Tanımlı değil|64 bit|64 bit|  
|`_findnexti64`, `_wfindnexti64`|Tanımlı|32 bit:|64 bit|  
|`_findnext32i64`, `_wfindnext32i64`|Makro tanımı tarafından etkilenen değil|32 bit:|64 bit|  
|`_findnext64i32`, `_wfindnext64i32`|Makro tanımı tarafından etkilenen değil|64 bit|32 bit:|  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tfindnext`|`_findnext`|`_findnext`|`_wfindnext`|  
|`_tfindnext32`|`_findnext32`|`_findnext32`|`_wfindnext32`|  
|`_tfindnext64`|`_findnext64`|`_findnext64`|`_wfindnext64`|  
|`_tfindnexti64`|`_findnexti64`|`_findnexti64`|`_wfindnexti64`|  
|`_tfindnext32i64`|`_findnext32i64`|`_findnext32i64`|`_wfindnext32i64`|  
|`_tfindnext64i32`|`_findnext64i32`|`_findnext64i32`|`_wfindnext64i32`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`_findnext`|\<io.h >|  
|`_findnext32`|\<io.h >|  
|`_findnext64`|\<io.h >|  
|`_findnexti64`|\<io.h >|  
|`_findnext32i64`|\<io.h >|  
|`_findnext64i32`|\<io.h >|  
|`_wfindnext`|\<io.h > veya \<wchar.h >|  
|`_wfindnext32`|\<io.h > veya \<wchar.h >|  
|`_wfindnext64`|\<io.h > veya \<wchar.h >|  
|`_wfindnexti64`|\<io.h > veya \<wchar.h >|  
|`_wfindnext32i64`|\<io.h > veya \<wchar.h >|  
|`_wfindnext64i32`|\<io.h > veya \<wchar.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sistem çağrıları](../../c-runtime-library/system-calls.md)   
 [Dosya arama işlevleri](../../c-runtime-library/filename-search-functions.md)