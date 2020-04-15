---
title: _findnext, _findnext32, _findnext32i64, _findnext64, _findnext64i32, _findnexti64, _wfindnext, _wfindnext32, _wfindnext32i64, _wfindnext64, _wfindnext64i32, _wfindnexti64
ms.date: 4/2/2020
api_name:
- _findnext
- _findnext32
- _findnext32i64
- _findnext64
- _findnext64i32
- _findnexti64
- _wfindnext
- _wfindnext32
- _wfindnext32i64
- _wfindnext64
- _wfindnext64i32
- _wfindnexti64
- _o__findnext32
- _o__findnext32i64
- _o__findnext64
- _o__findnext64i32
- _o__wfindnext32
- _o__wfindnext32i64
- _o__wfindnext64
- _o__wfindnext64i32
api_location:
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 38243b48a97c038f36ada85e3ca2cda814f43fa8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346734"
---
# <a name="_findnext-_findnext32-_findnext32i64-_findnext64-_findnext64i32-_findnexti64-_wfindnext-_wfindnext32-_wfindnext32i64-_wfindnext64-_wfindnext64i32-_wfindnexti64"></a>_findnext, _findnext32, _findnext32i64, _findnext64, _findnext64i32, _findnexti64, _wfindnext, _wfindnext32, _wfindnext32i64, _wfindnext64, _wfindnext64i32, _wfindnexti64

[_findfirst](findfirst-functions.md)için önceki bir çağrıda *filespec* bağımsız değişkeni eşleşen bir sonraki adı, varsa bulun ve sonra buna göre *fileinfo* yapı içeriğini değiştirin.

## <a name="syntax"></a>Sözdizimi

```C
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

### <a name="parameters"></a>Parametreler

*Işlemek*<br/>
**_findfirst**için önceki bir arama tarafından döndürülen arama tanıtıcısı.

*Fileınfo*<br/>
Dosya bilgi arabelleği.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, 0 döndürür. Aksi takdirde, -1 döndürür ve hatanın doğasını gösteren bir **değere errno** ayarlar. Olası hata kodları aşağıdaki tabloda gösterilmiştir.

|errno değeri|Koşul|
|-|-|
| **Eınval** | Geçersiz parametre: *fileinfo* **NULL**oldu. Veya, işletim sistemi beklenmeyen bir hata döndürür. |
| **Enoent** | Daha fazla eşleşen dosya bulunamadı. |
| **ENOMEM** | Yeterli bellek veya dosya adının uzunluğu **MAX_PATH**aşıldı. |

Geçersiz bir parametre geçirilirse, bu işlevler [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır.

## <a name="remarks"></a>Açıklamalar

**_findfirst** veya **_findnext** işlevini (veya herhangi bir türevlerini) kullanmayı bitirdikten sonra [_findclose](findclose.md) aramalısınız. Bu, uygulamanızda bu işlevler tarafından kullanılan kaynakları boşaltıyor.

W **öneki** ile bu işlevlerin varyasyonları geniş karaktersürümleri; aksi takdirde, bunlar karşılık gelen tek bayt işlevleri ile aynıdır.

Bu işlevlerin varyasyonları 32-bit veya 64-bit zaman türlerini ve 32-bit veya 64-bit dosya boyutlarını destekler. İlk sayısal sonek (**32** veya **64**) kullanılan zaman türünün boyutunu gösterir; ikinci sonek, dosya boyutunun 32 bit veya 64 bit tamsayı olarak temsil edilip edilmediğini belirten **i32** veya **i64'tür.** Hangi sürümlerin 32 bit ve 64 bit zaman türlerini ve dosya boyutlarını desteklediği hakkında bilgi için aşağıdaki tabloya bakın. 64 bit zaman türü kullanan varyasyonlar, dosya oluşturma tarihlerinin 23:59:59, 31 Aralık 3000, UTC' ye kadar ifade edilmesine olanak sağlar; 32 bit zaman türlerini kullananlar sadece 23:59:59 18 Ocak 2038, UTC tarihleri temsil ederken. Midnight, 1 Ocak 1970, tüm bu işlevler için tarih aralığının alt sınırıdır.

Zaman boyutunu açıkça belirten sürümleri kullanmak için belirli bir nedeniniz yoksa, **_findnext** veya **_wfindnext** kullanın veya 3 GB'dan büyük dosya boyutlarını desteklemeniz **gerekiyorsa, _findnexti64** veya **_wfindnexti64**kullanın. Tüm bu işlevler 64 bit zaman türünü kullanır. Önceki sürümlerde, bu işlevler 32 bitlik bir zaman türü kullanmİş. Bu, bir uygulama için bir kesme değişikliğiyse, eski davranışı almak için **_USE_32BIT_TIME_T** tanımlayabilirsiniz. **_USE_32BIT_TIME_T** **tanımlanırsa,** **_findnext,**_finnexti64 ve bunların karşılık gelen Unicode sürümleri 32 bit lik bir süre kullanır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="time-type-and-file-length-type-variations-of-_findnext"></a>_findnext Zaman Türü ve Dosya Uzunluğu Tür Varyasyonları

|İşlevler|**tanımlanmış _USE_32BIT_TIME_T?**|Zaman türü|Dosya uzunluğu türü|
|---------------|----------------------------------|---------------|----------------------|
|**_findnext**, **_wfindnext**|Tanımlı değil|64 bit|32 bit|
|**_findnext**, **_wfindnext**|Tanımlanan|32 bit|32 bit|
|**_findnext32**, **_wfindnext32**|Makro tanımından etkilenmez|32 bit|32 bit|
|**_findnext64**, **_wfindnext64**|Makro tanımından etkilenmez|64 bit|64 bit|
|**_findnexti64**, **_wfindnexti64**|Tanımlı değil|64 bit|64 bit|
|**_findnexti64**, **_wfindnexti64**|Tanımlanan|32 bit|64 bit|
|**_findnext32i64**, **_wfindnext32i64**|Makro tanımından etkilenmez|32 bit|64 bit|
|**_findnext64i32**, **_wfindnext64i32**|Makro tanımından etkilenmez|64 bit|32 bit|

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfindnext**|**_findnext**|**_findnext**|**_wfindnext**|
|**_tfindnext32**|**_findnext32**|**_findnext32**|**_wfindnext32**|
|**_tfindnext64**|**_findnext64**|**_findnext64**|**_wfindnext64**|
|**_tfindnexti64**|**_findnexti64**|**_findnexti64**|**_wfindnexti64**|
|**_tfindnext32i64**|**_findnext32i64**|**_findnext32i64**|**_wfindnext32i64**|
|**_tfindnext64i32**|**_findnext64i32**|**_findnext64i32**|**_wfindnext64i32**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_findnext**|\<io.h>|
|**_findnext32**|\<io.h>|
|**_findnext64**|\<io.h>|
|**_findnexti64**|\<io.h>|
|**_findnext32i64**|\<io.h>|
|**_findnext64i32**|\<io.h>|
|**_wfindnext**|\<io.h> \<veya wchar.h>|
|**_wfindnext32**|\<io.h> \<veya wchar.h>|
|**_wfindnext64**|\<io.h> \<veya wchar.h>|
|**_wfindnexti64**|\<io.h> \<veya wchar.h>|
|**_wfindnext32i64**|\<io.h> \<veya wchar.h>|
|**_wfindnext64i32**|\<io.h> \<veya wchar.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Sistem Aramaları](../../c-runtime-library/system-calls.md)<br/>
[Dosya Adı Arama Fonksiyonları](../../c-runtime-library/filename-search-functions.md)<br/>
