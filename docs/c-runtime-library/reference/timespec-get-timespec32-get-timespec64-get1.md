---
title: timespec_get, _timespec32_get, _timespec64_get1
ms.date: 11/04/2016
apiname:
- timespec_get
- _timespec32_get
- _timespec64_get
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: c1d0cbaf194060d816e31d397a9319ef47f75371
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638457"
---
# <a name="timespecget-timespec32get-timespec64get"></a>timespec_get, _timespec32_get, _timespec64_get

Temel belirtilen tarihte temel aralığı geçerli Takvim zaman için ilk bağımsız değişken işaret ettiği ayarlar.

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
Dönem başlangıcından ayarlanır ve saniye nanosaniye cinsinden süre bir yapı işaretçisi.

*base*<br/>
Süresi Temeli belirten sıfır olmayan uygulamaya özel değeri.

## <a name="return-value"></a>Dönüş Değeri

Değerini *temel* başarılı, aksi halde sıfır döndürür.

## <a name="remarks"></a>Açıklamalar

**Timespec_get** işlevleri işaret ettiği struct geçerli saati kümesinde *time_spec* bağımsız değişken. Bu struct'ın tüm sürümleri iki üyesi olan **tv_sec** ve **tv_nsec**. **Tv_sec** değeri saniye tam sayıya ayarlanır ve **tv_nsec** nanosaniye integral sayıya yuvarlanır sistem saatinin çözümü tarafından belirtildiepochbaşladığındanbuyana*temel*.

**Microsoft'a özgü**

Bu işlevler yalnızca Destek **TIME_UTC** olarak *temel* değeri. Bu ayarlar *time_spec* değeri ve dönem başlangıcından itibaren gece yarısı, 1 Ocak 1970, Eşgüdümlü Evrensel Saat (UTC) nanosaniye saniye sayısı. İçinde bir **yapı** **_timespec32**, **tv_sec** olduğu bir **__time32_t** değeri. İçinde bir **yapı** **_timespec64**, **tv_sec** olduğu bir **__time64_t** değeri. İçinde bir **yapı** **timespec**, **tv_sec** olduğu bir **time_t** 32 bit veya 64 bit uzunluğunda bağlı olarak tür, önişlemci Makro _use_32bıt_tıme_t tanımlanır. **Timespec_get** işlev, satır içi işlev çağıran **_timespec32_get** _use_32bıt_tıme_t tanımlıysa; Aksi takdirde çağrı **_timespec64_get**.

**End Microsoft özgü**

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**timespec_get**, **_timespec32_get**, **_timespec64_get**|C: \<TIME.h >, C++: \<ctime > veya \<TIME.h >|

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
