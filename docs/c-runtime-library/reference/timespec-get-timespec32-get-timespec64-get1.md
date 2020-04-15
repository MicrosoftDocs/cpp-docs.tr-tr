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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: fc6d91b076f2dd2e25c55d9cf7062e81c3fab11a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362485"
---
# <a name="timespec_get-_timespec32_get-_timespec64_get"></a>timespec_get, _timespec32_get, _timespec64_get

Belirtilen zaman tabanını temel alarak, ilk bağımsız değişkentarafından işaret edilen aralığı geçerli takvim saatine ayarlar.

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
Çağın başlangıcından bu yana saniye ve nanosaniye cinsinden zamana ayarlanan bir yapıyı işaretle.

*base*<br/>
Zaman tabanını belirten sıfır olmayan uygulamaya özgü bir değer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa *tabanın* değeri, aksi takdirde sıfır döndürür.

## <a name="remarks"></a>Açıklamalar

**timespec_get** *işlevleri, time_spec* bağımsız değişkenin işaret ettiği yapıdaki geçerli saati ayarlar. Bu yapının tüm **sürümleriiki** üye, tv_sec ve **tv_nsec**var. **tv_sec** değeri saniye tam sayısına ayarlanır ve *nanosaniye*integral **sayısına tv_nsec,** sistem saatinin çözünürlüğüne yuvarlanır, temel tarafından belirtilen çağın başlangıcından bu yana.

**Microsoft'a Özgü**

Bu işlevler yalnızca *temel* değer olarak **TIME_UTC** destekler. Bu, çağın başlangıcından bu yana saniye ve nanosaniye sayısı, Midnight, 1 Ocak 1970, Eşgüdümlü Evrensel Zaman (UTC) *time_spec* değerini ayarlar. Bir **yapı** **_timespec32,** **tv_sec** **__time32_t** bir değerdir. Bir **yapı** **_timespec64,** **tv_sec** **__time64_t** bir değerdir. Bir **yapı** **zaman spec,** **tv_sec** preprocessor makro _USE_32BIT_TIME_T tanımlı olup olmadığına bağlı olarak uzunluğu 32 bit veya 64 bit olan **time_t** türüdür. **timespec_get** işlevi, _USE_32BIT_TIME_T tanımlanırsa **_timespec32_get** çağıran bir satır dışı işlevdir; aksi takdirde **_timespec64_get**çağırır.

**Microsoft'a Özel Son**

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**timespec_get**, **_timespec32_get**, **_timespec64_get**|C: \<time.h>, \<C++: \<ctime> veya time.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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
