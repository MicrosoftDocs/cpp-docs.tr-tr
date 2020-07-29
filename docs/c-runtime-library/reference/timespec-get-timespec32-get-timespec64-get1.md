---
title: timespec_get, _timespec32_get, _timespec64_get1
ms.date: 4/2/2020
api_name:
- timespec_get
- _timespec32_get
- _timespec64_get
- _o__timespec32_get
- _o__timespec64_get
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
- api-ms-win-crt-time-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- timespec_get
- _timespec32_get
- _timespec64_get
- time/timespec_get
- time/_timespec32_get
- time/_timespec64_get
- timespec
- _timespec32
- _timespec64
helpviewer_keywords:
- timespec_get function
- _timespec32_get function
- _timespec64_get function
ms.assetid: ed757258-b4f2-4c1d-a91b-22ea6ffce4ab
ms.openlocfilehash: 7e3c56805b3af9bb5e739bd74d03bce015c65895
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233931"
---
# <a name="timespec_get-_timespec32_get-_timespec64_get"></a>timespec_get, _timespec32_get, _timespec64_get

Belirtilen zaman tabanına göre, ilk bağımsız değişken tarafından işaret edilen aralığı geçerli takvim zamanına göre belirler.

## <a name="syntax"></a>Söz dizimi

```C
int timespec_get(
    struct timespec* const time_spec,
    int const base
);
int _timespec32_get(
    struct _timespec32* const time_spec,
    int const base
);
int _timespec64_get(
    struct _timespec64* const time_spec,
    int const base
);
```

### <a name="parameters"></a>Parametreler

*time_spec*<br/>
Dönem başlangıcından bu yana saniye cinsinden süre ve nanosaniye olarak ayarlanan bir yapı işaretçisi.

*base*<br/>
Zaman temelini belirten, sıfır olmayan uygulamaya özgü bir değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa *taban* değeri 0 döndürür.

## <a name="remarks"></a>Açıklamalar

**Timespec_get** işlevleri, *time_spec* bağımsız değişkeni tarafından işaret edilen yapıda geçerli zamanı ayarlar. Bu yapının tüm sürümlerinde, **tv_sec** ve **tv_nsec**iki üye vardır. **Tv_sec** değeri, *taban*olarak belirtilen dönem başlangıcından bu yana, sistem saatinin çözümüne yuvarlanarak, tüm saniye sayısına ve **tv_nsec** tam sayı olarak ayarlanır.

**Microsoft'a Özgü**

Bu işlevler yalnızca *temel* değer olarak **TIME_UTC** destekler. Bu, *time_spec* değerini dönem başı, gece yarısı, 1 Ocak 1970, Eşgüdümlü Evrensel Saat (UTC) için saniye ve nanosaniye sayısına ayarlar. **`struct`** **_Timespec32**, **tv_sec** bir **__time32_t** değeridir. **`struct`** **_Timespec64**, **tv_sec** bir **__time64_t** değeridir. Bir **`struct`** **timespec**içinde **tv_sec** , önişlemci makrosu _USE_32BIT_TIME_T tanımlanmış olup olmadığına bağlı olarak 32 bit veya 64 bit olan bir **time_t** türüdür. **Timespec_get** işlevi _USE_32BIT_TIME_T tanımlanmışsa **_timespec32_get** çağıran bir satır içi işlevdir; Aksi takdirde **_timespec64_get**çağırır.

**Son Microsoft 'a özgü**

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**timespec_get**, **_timespec32_get**, **_timespec64_get**|C: \<time.h> , C++: \<ctime> veya\<time.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[asctime, _wasctime](asctime-wasctime.md)<br/>
[asctime_s, _wasctime_s](asctime-s-wasctime-s.md)<br/>
[_ftime, _ftime32, _ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime, _gmtime32, _gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime, _localtime32, _localtime64](localtime-localtime32-localtime64.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[time, _time32, _time64](time-time32-time64.md)<br/>
[_utime, _utime32, _utime64, _wutime, _wutime32, _wutime64](utime-utime32-utime64-wutime-wutime32-wutime64.md)<br/>
