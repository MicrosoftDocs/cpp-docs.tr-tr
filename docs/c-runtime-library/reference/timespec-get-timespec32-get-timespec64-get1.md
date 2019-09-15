---
title: timespec_get, _times, 32_get, _timesbir 64_get1
ms.date: 11/04/2016
api_name:
- timespec_get
- _timespec32_get
- _timespec64_get
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
ms.openlocfilehash: c0517c974bf58d502133ccd9868149bd178790d6
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957629"
---
# <a name="timespec_get-_timespec32_get-_timespec64_get"></a>timespec_get, _timespec32_get, _timespec64_get

Belirtilen zaman tabanına göre, ilk bağımsız değişken tarafından işaret edilen aralığı geçerli takvim zamanına göre belirler.

## <a name="syntax"></a>Sözdizimi

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

**Timespec_get** işlevleri, *time_spec* bağımsız değişkeni tarafından işaret edilen yapıda geçerli zamanı ayarlar. Bu yapının tüm sürümlerinde, **tv_sec** ve **tv_nsec**iki üyesi vardır. **Tv_sec** değeri, *taban*olarak belirtilen dönem başlangıcından bu yana, sistem saatinin çözümlenmesinden önce, tüm saniye sayısına ve **tv_nsec** ' nin tamsayı sayısına yuvarlanır.

**Microsoft 'a özgü**

Bu işlevler yalnızca *temel* değer olarak **TIME_UTC** destekler. Bu, *time_spec* değerini dönem başı, gece yarısı, 1 Ocak 1970, Eşgüdümlü Evrensel Saat (UTC) için saniye ve nanosaniye sayısına ayarlar. Bir **struct** **_timesbir 32**içinde, **tv_sec** bir **__time32_t** değeridir. Bir **struct** **_times, 64**, **tv_sec** bir **__time64_t** değeridir. Bir **struct** **timespec**içinde, **tv_sec** , Önişlemci makrosunun _USE_32BIT_TIME_T 'ın tanımlanıp tanımlandığına bağlı olarak 32 bit veya 64 bit olan **time_t** türüdür. **Timespec_get** işlevi, _USE_32BIT_TIME_T tanımlanmışsa **_times, 32_get** yöntemini çağıran bir satır içi işlevdir; Aksi takdirde, **_timesbir 64_get**çağrısı yapın.

**Son Microsoft 'a özgü**

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**timespec_get**, **_times, 32_get**, **_timesbir 64_get**|C: \<Time. h >, C++: \<CTime > veya \<Time. h >|

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
