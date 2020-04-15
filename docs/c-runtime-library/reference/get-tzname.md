---
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 50f1f6e4320e3ef905b4eda67ba1d458a5b1df08
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344883"
---
# <a name="_get_tzname"></a>_get_tzname

Saat dilimi adının veya gün ışığı standart saat dilimi adının (DST) karakter dizesini alır.

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

*pReturnValue*<br/>
Null terminator dahil *zamanZoneName* dize uzunluğu.

*timeZoneName*<br/>
Dizin bağlı olarak saat dilimi adı veya gün ışığı standart saat dilimi adı (DST) gösterimi için bir karakter dize *adresi.*

*sizeBytes*<br/>
Baytlar'daki *zamanZoneName* karakter dizesinin boyutu.

*Dizin*<br/>
Alınacak iki saat dilimi adıarasından birinin dizini.

|*Dizin*|*zamanZoneName* içeriği|*timeZoneName* varsayılan değer|
|-|-|-|
|0|Saat dilimi adı|"PST"|
|1|Gün ışığı standart saat dilimi adı|"PDT"|
|> 1 veya < 0|**errno** **EINVAL** için ayarlayın|değiştirilmemiş|

Çalışma süresi sırasında değerler açıkça değiştirilmediği sürece, varsayılan değerler sırasıyla "PST" ve "PDT" olur.

## <a name="return-value"></a>Dönüş Değeri

Sıfır başarılı, aksi takdirde bir **errno** türü değeri.

*ZamanZoneName* **NULL**ise veya *sizeInBytes* sıfır veya sıfırdan az (ama her ikisi değil), geçersiz bir parametre işleyicisi çağrılır, [Parametre Doğrulama](../../c-runtime-library/parameter-validation.md)açıklandığı gibi . Yürütmedevam etmesine izin verilirse, bu işlev **EINVAL için errno** ayarlar ve **EINVAL** döndürür. **EINVAL**

### <a name="error-conditions"></a>Hata Koşulları

|*pReturnValue*|*timeZoneName*|*sizeBytes*|*Dizin*|Döndürülen değer|*zamanZoneName* içeriği|
|--------------------|--------------------|-------------------|-------------|------------------|--------------------------------|
|TZ adının boyutu|**Null**|0|0 veya 1|0|değiştirilmemiş|
|TZ adının boyutu|herhangi bir|> 0|0 veya 1|0|TZ adı|
|değiştirilmemiş|**Null**|> 0|herhangi bir|**Eınval**|değiştirilmemiş|
|değiştirilmemiş|herhangi bir|sıfır|herhangi bir|**Eınval**|değiştirilmemiş|
|değiştirilmemiş|herhangi bir|> 0|> 1|**Eınval**|değiştirilmemiş|

## <a name="remarks"></a>Açıklamalar

**_get_tzname** işlevi, dizin değerine bağlı olarak geçerli saat dilimi adının veya gün ışığı standart saat dilimi adının (DST) karakter dizesini ve *pReturnValue'daki*dize boyutuyla birlikte *zaman Dilimi Adı'nın* adresine alır. *timeZoneName* **NULL** ve *sizeInBytes* sıfır ise, belirtilen saat dilimini tutmak için gerekli dize boyutu ve bayt bir sonlandırıcı null *pReturnValue*döndürülür. Dizin değerleri standart saat dilimi için 0 veya gün ışığı standart saat dilimi için 1 olmalıdır; *dizin* diğer değerleri belirsiz sonuçlar var.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="example"></a>Örnek

Bu örnek, geçerli Gün Işığı standart saat dilimi adını görüntülemek için gerekli arabellek boyutunu almak için **_get_tzname** çağırır, bu boyutta bir arabellek ayırır, arabellek adını yüklemek için **_get_tzname** tekrar çağırır ve konsola yazdırır.

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

Daha fazla bilgi için [Uyumluluk'a](../../c-runtime-library/compatibility.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_timezone](get-timezone.md)<br/>
