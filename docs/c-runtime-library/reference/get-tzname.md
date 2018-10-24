---
title: _get_tzname | Microsoft Docs
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _get_tzname
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
- _get_tzname
- get_tzname
dev_langs:
- C++
helpviewer_keywords:
- _get_tzname function
- time zones
- get_tzname function
ms.assetid: df0065ff-095f-4237-832c-2fe9ab913875
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d773d5d98466963ef621cc3fa7bc5ab8b4acc40a
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2018
ms.locfileid: "49990314"
---
# <a name="gettzname"></a>_get_tzname

Saat dilimi adını veya gün ışığından yararlanma standart saat dilimi adının (DST) karakter dize gösterimini alır.

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
Dize uzunluğu *saatdilimi adı* null sonlandırıcıyı da dahil olmak üzere.

*saatdilimi adı*<br/>
Ayarlara bağlı olarak bir karakter dizesi için saat dilimi adını veya gün ışığından yararlanma standart saat dilimi adının (DST) gösterimi adresini *dizin*.

*sizeInBytes*<br/>
Boyutu *saatdilimi adı* karakter dizesi bayt.

*Dizin*<br/>
Dizini almak için iki saat dilimi adlarından biri.

|*Dizin*|İçeriğini *saatdilimi adı*|*saatdilimi adı* varsayılan değer|
|-|-|-|
|0|Saat dilimi adı|"PST"|
|1.|Gün ışığından yararlanma standart saat dilimi adının|"PASİFİK YAZ SAATİ'NE"|
|1 > veya < 0|**errno** kümesine **EINVAL**|değiştirilmedi|

Değerleri açıkça çalışma zamanı sırasında değiştirilen sürece, varsayılan "PST" ve "Pasifik Yaz SAATİ'ne" sırasıyla değerlerdir.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır Aksi halde bir **errno** değeri yazın.

Ya da *saatdilimi adı* olduğu **NULL**, veya *sizeInBytes* sıfır veya daha azını sıfır (ancak ikisi birden değil), geçersiz parametre işleyicisini, açıklanan şekilde çağrılır [ Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse, bu işlev ayarlar **errno** için **EINVAL** ve döndürür **EINVAL**.

### <a name="error-conditions"></a>Hata koşulları

|*pReturnValue*|*saatdilimi adı*|*sizeInBytes*|*Dizin*|Dönüş değeri|İçeriğini *saatdilimi adı*|
|--------------------|--------------------|-------------------|-------------|------------------|--------------------------------|
|TZ adının boyutu|**NULL**|0|0 veya 1|0|değiştirilmedi|
|TZ adının boyutu|Tüm|> 0|0 veya 1|0|TZ adı|
|değiştirilmedi|**NULL**|> 0|Tüm|**EINVAL**|değiştirilmedi|
|değiştirilmedi|Tüm|sıfır|Tüm|**EINVAL**|değiştirilmedi|
|değiştirilmedi|Tüm|> 0|> 1|**EINVAL**|değiştirilmedi|

## <a name="remarks"></a>Açıklamalar

**_Get_tzname** işlevi karakter dize gösterimine Yaz standart saat dilimi adının (DST) geçerli saat dilimi adını veya adresini alır *saatdilimi adı* bağlı olarak Dizin değeri dize boyutunu birlikte *pReturnValue*. Varsa *saatdilimi adı* olduğu **NULL** ve *sizeInBytes* sıfır, belirtilen saat dilimi barındırmak için gereken dize boyutu ve bir sonlandırıcı null bayt döndürülür*pReturnValue*. Dizin değerlerinin standart saat dilimi için 0 veya 1 gün ışığından yararlanma standart saat diliminde olmalıdır; diğer tüm değerleri *dizin* sahip belirlenmemiş sonuçları.

## <a name="example"></a>Örnek

Bu örneği çağırır **_get_tzname** geçerli gün ışığından yararlanma standart saat dilimi adının görüntülemek için gerekli arabellek boyutunu almak için çağrıları bu boyuttaki bir arabelleği ayırır **_get_tzname** adı yeniden yüklemek için Arabellek ve konsola yazdırır.

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

### <a name="output"></a>Çıkış

```Output
The current Daylight standard time zone name is PDT.
```

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_tzname**|\<TIME.h >|

Daha fazla bilgi için [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_timezone](get-timezone.md)<br/>
