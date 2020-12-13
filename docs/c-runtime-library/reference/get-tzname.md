---
description: 'Hakkında daha fazla bilgi edinin: _get_tzname'
title: _get_tzname
ms.date: 4/2/2020
api_name:
- _get_tzname
- _o__get_tzname
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
- _get_tzname
- get_tzname
helpviewer_keywords:
- _get_tzname function
- time zones
- get_tzname function
ms.assetid: df0065ff-095f-4237-832c-2fe9ab913875
ms.openlocfilehash: b98a068d6f2d2643df43078c5a274fd761ac8e95
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338958"
---
# <a name="_get_tzname"></a>_get_tzname

Saat dilimi adının veya yaz standart saat dilimi adının (DST) karakter dizesi gösterimini alır.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _get_tzname(
    size_t* pReturnValue,
    char* timeZoneName,
    size_t sizeInBytes,
    int index
);
```

### <a name="parameters"></a>Parametreler

*Ön kapatma değeri*<br/>
Null Sonlandırıcı dahil olmak üzere *timeZoneName* dize uzunluğu.

*timeZoneName*<br/>
*Dizine* bağlı olarak, saat dilimi adının temsili için bir karakter dizesinin adresi veya yaz standart saat dilimi adı (DST).

*sizeInBytes*<br/>
Bayt cinsinden *timeZoneName* karakter dizesinin boyutu.

*indeks*<br/>
Alınacak iki saat dilimi adından birinin dizini.

|*indeks*|*TimeZoneName* içeriği|*timeZoneName* varsayılan değeri|
|-|-|-|
|0|Saat dilimi adı|PASIFIK|
|1|Günışığı standart saat dilimi adı|SAATI|
|> 1 veya < 0|**errno** , **EINVAL** olarak ayarlandı|değiştirilmedi|

Çalışma zamanında değerler açıkça değiştirilmediği takdirde, varsayılan değerler sırasıyla "PST" ve "pasıfık" dir.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır, aksi durumda bir **errno** türü değeri.

Her iki *timeZoneName* de **null** veya *sizeInBytes* sıfır veya sıfırdan küçükse (her Ikisi birden değilse), [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **errno** ' ı **EINVAL** olarak ayarlar ve **EINVAL** döndürür.

### <a name="error-conditions"></a>Hata koşulları

|*Ön kapatma değeri*|*timeZoneName*|*sizeInBytes*|*indeks*|Döndürülen değer|*TimeZoneName* içeriği|
|--------------------|--------------------|-------------------|-------------|------------------|--------------------------------|
|TZ adının boyutu|**DEĞER**|0|0 veya 1|0|değiştirilmedi|
|TZ adının boyutu|herhangi biri|> 0|0 veya 1|0|TZ adı|
|değiştirilmedi|**DEĞER**|> 0|herhangi biri|**EıNVAL**|değiştirilmedi|
|değiştirilmedi|herhangi biri|sıfır|herhangi biri|**EıNVAL**|değiştirilmedi|
|değiştirilmedi|herhangi biri|> 0|> 1|**EıNVAL**|değiştirilmedi|

## <a name="remarks"></a>Açıklamalar

**_Get_tzname** işlevi, geçerli saat dilimi adının karakter dizesi gösterimini veya gün standart saat dilimi adını (DST) dizin değerine bağlı olarak *TimeZoneName* adresine, *ön işlem değerindeki* dize boyutuyla birlikte alır. *TimeZoneName* **null** Ise ve *sizeInBytes* sıfırsa, belirtilen saat dilimini tutmak için gereken dize boyutu ve bayt cinsinden bir Sonlandırıcı null *değeri ön işlem değerinde* döndürülür. Dizin değerleri standart saat dilimi için 0 ya da Günışığı standart saat dilimi için 1 olmalıdır; Tüm diğer *Dizin* değerleri belirlenmeyen sonuçlara sahiptir.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="example"></a>Örnek

Bu örnek, geçerli yaz standart saat dilimi adını göstermek için gerekli arabellek boyutunu almak üzere **_get_tzname** çağırır, bu boyutta bir arabellek ayırır, adı arabelleğe yüklemek için yeniden **_get_tzname** çağırır ve bunu konsola yazdırır.

```C
// crt_get_tzname.c
// Compile by using: cl /W4 crt_get_tzname.c
#include <stdio.h>
#include <time.h>
#include <malloc.h>

enum TZINDEX {
    STD,
    DST
};

int main()
{
    size_t tznameSize = 0;
    char * tznameBuffer = NULL;

    // Get the size of buffer required to hold DST time zone name
    if (_get_tzname(&tznameSize, NULL, 0, DST))
        return 1;    // Return an error value if it failed

    // Allocate a buffer for the name
    if (NULL == (tznameBuffer = (char *)(malloc(tznameSize))))
        return 2;    // Return an error value if it failed

    // Load the name in the buffer
    if (_get_tzname(&tznameSize, tznameBuffer, tznameSize, DST))
        return 3;    // Return an error value if it failed

    printf_s("The current Daylight standard time zone name is %s.\n", tznameBuffer);
    return 0;
}
```

### <a name="output"></a>Çıktı

```Output
The current Daylight standard time zone name is PDT.
```

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_tzname**|\<time.h>|

Daha fazla bilgi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_timezone](get-timezone.md)<br/>
