---
title: timespec_get, _timespec32_get, _timespec64_get1 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- timespec_get function
- _timespec32_get function
- _timespec64_get function
ms.assetid: ed757258-b4f2-4c1d-a91b-22ea6ffce4ab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f00a59f8b5813398b47562b106f3ec0eff3363b1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="timespecget-timespec32get-timespec64get"></a>timespec_get, _timespec32_get, _timespec64_get

Aralığı geçerli Takvim zaman için ilk bağımsız değişken gösterdiği kümeleri temel belirtilen süreye dayalı.

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
Dönem başladığından bu yana saniye ve nanosaniye zamana ayarlanan yapı işaretçi.

*base*<br/>
Süresi Temeli belirten sıfır uygulamaya özel değer.

## <a name="return-value"></a>Dönüş Değeri

Değeri *temel* başarılı, aksi takdirde, sıfır durumunda döndürür.

## <a name="remarks"></a>Açıklamalar

**Timespec_get** işlevleri gösterdiği yapısı geçerli saati kümesinde *time_spec* bağımsız değişkeni. Bu yapı'nin tüm sürümleri iki üyelere sahip **tv_sec** ve **tv_nsec**. **Tv_sec** değeri saniye tam sayıya ayarlanır ve **tv_nsec** nanosaniye tam sayı sayıya yuvarlanan sistem saati, çözümleme için tarafındanbelirtilendönembaşladığındanbuyana*temel*.

**Microsoft özel**

Bu işlevler yalnızca Destek **TIME_UTC** olarak *temel* değeri. Bu ayarlar *time_spec* değerine ve Dönem başlangıç olduğundan, gece yarısı, 1 Ocak 1970 Eşgüdümlü Evrensel Saat (UTC) nanosaniye saniye sayısı. İçinde bir **yapısı** **_timespec32**, **tv_sec** olan bir **__time32_t** değeri. İçinde bir **yapısı** **_timespec64**, **tv_sec** olan bir **__time64_t** değeri. İçinde bir **yapısı** **timespec**, **tv_sec** olan bir **time_t** 32 bit veya 64 bit uzunluğunda mı bağlı olarak türü ön işlemci Makro _USE_32BIT_TIME_T tanımlanır. **Timespec_get** işlevidir çağıran bir satır içi işlev **_timespec32_get** _USE_32BIT_TIME_T tanımlanmışsa; Aksi takdirde çağırır **_timespec64_get**.

**Son Microsoft özel**

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**timespec_get**, **_timespec32_get**, **_timespec64_get**|C: \<time.h >, C++: \<ctime > veya \<time.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
