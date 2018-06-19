---
title: _get_tzname | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: a4b49aa404dda6234382ae461459dece64e5996d
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
ms.locfileid: "34451699"
---
# <a name="gettzname"></a>_get_tzname

Saat dilimi adı veya gün ışığından yararlanma standart saat dilimi adının (DST) karakteri dize gösterimini alır.

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
Dize uzunluğu *saatdilimi adı* null Sonlandırıcı dahil olmak üzere.

*saatdilimi adı*<br/>
Bağlı olarak, saat dilimi adı veya gün ışığından yararlanma standart saat dilimi adının (DST) gösterimi için bir karakter dizesi adresini *dizin*.

*sizeInBytes*<br/>
Boyutunu *saatdilimi adı* karakter bayt dizesi.

*Dizin*<br/>
Dizini almak için iki saat dilimi adlarından biri.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, sıfır Aksi halde bir **errno** değeri yazın.

Her iki *saatdilimi adı* olan **NULL**, veya *sizeInBytes* sıfır veya sıfır (ancak ikisi birden değil),'dan küçük bir geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [ Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev devam etmek için yürütülmesine izin veriliyorsa, ayarlar **errno** için **EINVAL** ve döndürür **EINVAL**.

### <a name="error-conditions"></a>Hata koşulları

|*pReturnValue*|*saatdilimi adı*|*sizeInBytes*|*Dizin*|Dönüş değeri|İçeriği *saatdilimi adı*|
|--------------------|--------------------|-------------------|-------------|------------------|--------------------------------|
|TZ adının boyutu|**NULL**|0|0 veya 1|0|değiştirilmedi|
|TZ adının boyutu|tüm|> 0|0 veya 1|0|TZ adı|
|değiştirilmedi|**NULL**|> 0|tüm|**EINVAL**|değiştirilmedi|
|değiştirilmedi|tüm|sıfır|tüm|**EINVAL**|değiştirilmedi|
|değiştirilmedi|tüm|> 0|> 1|**EINVAL**|değiştirilmedi|

## <a name="remarks"></a>Açıklamalar

**_Get_tzname** işlevi alır karakteri dize gösterimini saat dilimi adı veya gün ışığından yararlanma standart saat dilimi adının (DST) adresini içine *saatdilimi adı* dizini bağlı olarak değer, dize boyutu birlikte *pReturnValue*. Varsa *saatdilimi adı* olan **NULL** ve *sizeInBytes* sıfır, yalnızca dize bayt bölgesinde döndürülür ya da zaman boyutu olduğu *pReturnValue*. Dizin değerleriyle standart saat dilimi için 0 veya 1 gün ışığından yararlanma standart saat dilimine yönelik olmalıdır; dizinin herhangi bir değere sahip belirlenmemiş sonuçları.

### <a name="index-values"></a>Dizini değerleri

|*Dizin*|İçeriği *saatdilimi adı*|*saatdilimi adı* varsayılan değer|
|-------------|--------------------------------|----------------------------------|
|0|Saat dilimi adı|"PST"|
|1.|Gün ışığından yararlanma standart saat dilimi adı|"SAATİ"|
|1 > veya < 0|**errno** kümesine **EINVAL**|değiştirilmedi|

Değerleri açıkça çalışma zamanı sırasında değiştirilen sürece, varsayılan "PST" ve "Saati" sırasıyla değerlerdir.  Bu karakter dizileri boyutlarını tarafından yönetilir **TZNAME_MAX** değeri.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_tzname**|\<time.h >|

Daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_timezone](get-timezone.md)<br/>
[TZNAME_MAX](../../c-runtime-library/tzname-max.md)<br/>
