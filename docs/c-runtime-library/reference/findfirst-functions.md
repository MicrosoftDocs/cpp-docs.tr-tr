---
title: _findfirst, _findfirst32, _findfirst32i64, _findfirst64, _findfirst64i32, _findfirsti64, _wfindfirst, _wfindfirst32, _wfindfirst32i64, _wfindfirst64, _wfindfirst64i32, _wfindfirsti64 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _findfirst
- _wfindfirst
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
- findfirst32i64
- wfindfirst32i64
- tfindfirst64
- _findfirst64i32
- _wfindfirst32i64
- _wfindfirsti64
- wfindfirst
- _tfindfirsti64
- findfirst32
- _tfindfirst32
- _findfirsti64
- findfirst
- wfindfirst64
- wfindfirst32
- tfindfirst32
- _wfindfirst64i32
- findfirst64i32
- tfindfirst64i32
- _wfindfirst
- findfirsti64
- _findfirst32i64
- wfindfirst64i32
- _wfindfirst32
- _findfirst32
- _tfindfirst32i64
- tfindfirst
- _tfindfirst64i32
- findfirst64
- _tfindfirst
- _findfirst64
- _tfindfirst64
- tfindfirst32i64
- _findfirst
- _wfindfirst64
dev_langs:
- C++
helpviewer_keywords:
- _tfindfirst64 function
- _wfindfirst64i32 function
- _wfindfirst32i64 function
- wfindfirst32 function
- _findfirst function
- wfindfirst64 function
- _wfindfirst function
- _findfirst64i32 function
- wfindfirst function
- _findfirst64 function
- tfindfirst32 function
- _tfindfirst64i32 function
- findfirst function
- findfirst32i64 function
- tfindfirst64 function
- _tfindfirst32 function
- tfindfirst32i64 function
- tfindfirst64i32 function
- _wfindfirsti64 function
- _findfirst32i64 function
- findfirst32 function
- findfirsti64 function
- findfirst64i32 function
- tfindfirsti64 function
- tfindfirst function
- _wfindfirst32 function
- wfindfirsti64 function
- _tfindfirsti64 function
- _tfindfirst function
- _tfindfirst32i64 function
- findfirst64 function
- _findfirst32 function
- _findfirsti64 function
- wfindfirst32i64 function
- wfindfirst64i32 function
- _wfindfirst64 function
ms.assetid: 9bb46d1a-b946-47de-845a-a0b109a33ead
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2c57577208e9c2e8306f2c1c30f352e62c068c88
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="findfirst-findfirst32-findfirst32i64-findfirst64-findfirst64i32-findfirsti64-wfindfirst-wfindfirst32-wfindfirst32i64-wfindfirst64-wfindfirst64i32-wfindfirsti64"></a>_findfirst, _findfirst32, _findfirst32i64, _findfirst64, _findfirst64i32, _findfirsti64, _wfindfirst, _wfindfirst32, _wfindfirst32i64, _wfindfirst64, _wfindfirst64i32, _wfindfirsti64

Belirtilen dosya ile eşleşen bir dosya adı ilk örneği hakkında bilgi sağlayan *dosya* bağımsız değişkeni.

## <a name="syntax"></a>Sözdizimi

```C
intptr_t _findfirst(
   const char *filespec,
   struct _finddata_t *fileinfo
);
intptr_t _findfirst32(
   const char *filespec,
   struct _finddata32_t *fileinfo
);
intptr_t _findfirst64(
   const char *filespec,
   struct _finddata64_t *fileinfo
);
intptr_t _findfirsti64(
   const char *filespec,
   struct _finddatai64_t *fileinfo
);
intptr_t _findfirst32i64(
   const char *filespec,
   struct _finddata32i64_t *fileinfo
);
intptr_t _findfirst64i32(
   const char *filespec,
   struct _finddata64i32_t *fileinfo
);
intptr_t _wfindfirst(
   const wchar_t *filespec,
   struct _wfinddata_t *fileinfo
);
intptr_t _wfindfirst32(
   const wchar_t *filespec,
   struct _wfinddata32_t *fileinfo
);
intptr_t _wfindfirst64(
   const wchar_t *filespec,
   struct _wfinddata64_t *fileinfo
);
intptr_t _wfindfirsti64(
   const wchar_t *filespec,
   struct _wfinddatai64_t *fileinfo
);
intptr_t _wfindfirst32i64(
   const wchar_t *filespec,
   struct _wfinddata32i64_t *fileinfo
);
intptr_t _wfindfirst64i32(
   const wchar_t *filespec,
   struct _wfinddata64i32_t *fileinfo
);
```

### <a name="parameters"></a>Parametreler

*Dosya*<br/>
Hedef dosya belirtimi (joker karakterleri dahil edebilirsiniz).

*FileInfo*<br/>
Dosya bilgileri arabelleği.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **_findfirst** dosya veya eşleşen bir dosya grubu tanımlayan bir benzersiz arama işleyici döner *dosya* sonraki çağrıda kullanılan belirtimi [_ FindNext](findnext-functions.md) veya [_findclose](findclose.md). Aksi takdirde, **_findfirst** -1 döndürür ve ayarlar **errno** aşağıdaki değerlerden birine.

|errno değeri|Koşul|
|-|-|
**EINVAL**|Geçersiz parametre: *dosya* veya *FileInfo* olan **NULL**. Veya, işletim sistemi beklenmeyen bir hata döndürdü.
**ENOENT**|Eşlenemiyor dosya belirtimi.
**ENOMEM**|Bellek yetersiz.
**EINVAL**|Geçersiz dosya adı belirtimine veya verilen dosya adı büyük **MAX_PATH**.

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Geçersiz bir parametre geçtiyse, bu işlevler geçersiz parametre işleyicisi açıklandığı gibi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md).

## <a name="remarks"></a>Açıklamalar

Çağırmalısınız [_findclose](findclose.md) biriyle tamamladıktan sonra **_findfirst** veya [_findnext](findnext-functions.md) işlevi (veya tüm çeşitleri). Bu, uygulamanızda bu işlevler tarafından kullanılan kaynakları serbest bırakır.

Bu işlevleri varyasyonları **w** öneki joker karakter sürümleri; Aksi halde, karşılık gelen tek baytlı işlevleri aynı olur.

Bu işlevler varyasyonları 32 bit veya 64-bit saat türleri ve 32 bit veya 64-bit dosya boyutunu destekler. İlk sayı sonekine (**32** veya **64**) zamanı tür; boyutunu gösterir ikinci ya da sonekidir **i32** veya **I64**ve gösterir olup dosya boyutu 32 bit veya 64 bit tamsayı olarak temsil edilir. Sürümler 32 bit ve 64-bit saat türleri ve dosya boyutları destekleyen hakkında bilgi için aşağıdaki tabloya bakın. **İ32** veya **I64** soneki, bu nedenle zamanı tür boyutu ile aynı olması durumunda atlanırsa **_findfirst64** 64-bit dosya uzunlukları de destekler ve **_findfirst32**  yalnızca 32-bit dosya uzunlukları destekler.

Bu işlevler çeşitli tür kullanmanıza **_finddata_t** için yapı *FileInfo* parametresi. Yapısı hakkında daha fazla bilgi için bkz: [Filename arama işlevleri](../../c-runtime-library/filename-search-functions.md).

Bir 64-bit süre türünü kullanan çeşitlemeleri 23:59:59, 31 Aralık 3000 UTC yukarı ifade için dosya oluşturma tarihleri etkinleştirin. 32-bit saat türleri kullananlar yalnızca 23:59:59 18 Ocak 2038, UTC aracılığıyla tarihleri temsil eder. Gece yarısından, 1 Ocak 1970'ten, bu işlevler için tarih aralığını alt sınırdır.

Zaman boyutu açıkça belirtmek, kullanın sürümlerini kullanmak üzere özel bir nedeniniz yoksa **_findfirst** veya **_wfindfirst** veya 3 GB'den büyük dosya boyutlarına desteklemeniz gerekiyorsa, kullanın **_ findfirsti64** veya **_wfindfirsti64**. Bu işlevler 64-bit süre türünü kullanın. Önceki sürümlerde, bu işlevlerin bir 32 bit time türü kullanılır. Bir uygulama için önemli bir değişiklik olursa tanımlayabilir **_USE_32BIT_TIME_T** eski davranışa geri dönmek için. Varsa **_USE_32BIT_TIME_T** tanımlanan **_findfirst**, **_finfirsti64**, ve karşılık gelen Unicode sürümlerine 32-bit saatini kullanın.

### <a name="time-type-and-file-length-type-variations-of-findfirst"></a>Saat türü ve dosya uzunluğu türü _findfirst varyasyonları

|İşlevler|**_USE_32BIT_TIME_T** tanımlanan?|Zaman türü|Dosya uzunluğu türü|
|---------------|----------------------------------|---------------|----------------------|
|**_findfirst**, **_wfindfirst**|Tanımlı değil|64 bit|32 bit:|
|**_findfirst**, **_wfindfirst**|Tanımlı|32 bit:|32 bit:|
|**_findfirst32**, **_wfindfirst32**|Makro tanımı tarafından etkilenen değil|32 bit:|32 bit:|
|**_findfirst64**, **_wfindfirst64**|Makro tanımı tarafından etkilenen değil|64 bit|64 bit|
|**_findfirsti64**, **_wfindfirsti64**|Tanımlı değil|64 bit|64 bit|
|**_findfirsti64**, **_wfindfirsti64**|Tanımlı|32 bit:|64 bit|
|**_findfirst32i64**, **_wfindfirst32i64**|Makro tanımı tarafından etkilenen değil|32 bit:|64 bit|
|**_findfirst64i32**, **_wfindfirst64i32**|Makro tanımı tarafından etkilenen değil|64 bit|32 bit:|

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfindfirst**|**_findfirst**|**_findfirst**|**_wfindfirst**|
|**_tfindfirst32**|**_findfirst32**|**_findfirst32**|**_wfindfirst32**|
|**_tfindfirst64**|**_findfirst64**|**_findfirst64**|**_wfindfirst64**|
|**_tfindfirsti64**|**_findfirsti64**|**_findfirsti64**|**_wfindfirsti64**|
|**_tfindfirst32i64**|**_findfirst32i64**|**_findfirst32i64**|**_wfindfirst32i64**|
|**_tfindfirst64i32**|**_findfirst64i32**|**_findfirst64i32**|**_wfindfirst64i32**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_findfirst**|\<io.h >|
|**_findfirst32**|\<io.h >|
|**_findfirst64**|\<io.h >|
|**_findfirsti64**|\<io.h >|
|**_findfirst32i64**|\<io.h >|
|**_findfirst64i32**|\<io.h >|
|**_wfindfirst**|\<io.h > veya \<wchar.h >|
|**_wfindfirst32**|\<io.h > veya \<wchar.h >|
|**_wfindfirst64**|\<io.h > veya \<wchar.h >|
|**_wfindfirsti64**|\<io.h > veya \<wchar.h >|
|**_wfindfirst32i64**|\<io.h > veya \<wchar.h >|
|**_wfindfirst64i32**|\<io.h > veya \<wchar.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Sistem Çağrıları](../../c-runtime-library/system-calls.md)<br/>
[fileName İşlevleri Ara](../../c-runtime-library/filename-search-functions.md)<br/>
