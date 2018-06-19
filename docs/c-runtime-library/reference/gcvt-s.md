---
title: _gcvt_s | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _gcvt_s
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _gcvt_s
- gcvt_s
dev_langs:
- C++
helpviewer_keywords:
- _gcvt_s function
- _CVTBUFSIZE
- floating-point functions, converting number to string
- gcvt_s function
- numbers, converting to strings
- conversions, floating point to strings
- strings [C++], converting from floating point
- CVTBUFSIZE
ms.assetid: 0a8d8a26-5940-4ae3-835e-0aa6ec1b0744
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a2bd12a63db064bca0c880484f99a2df9d210f8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403774"
---
# <a name="gcvts"></a>_gcvt_s

Kayan nokta değeri dizeye dönüştürür. Bu bir sürümüdür [_gcvt](gcvt.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t _gcvt_s(
   char *buffer,
   size_t sizeInBytes,
   double value,
   int digits
);
template <size_t cchStr>
errno_t _gcvt_s(
   char (&buffer)[cchStr],
   double value,
   int digits
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Dönüştürme işleminin sonucu depolamak için bir arabellek.

*sizeInBytes*<br/>
Arabellek boyutu.

*value*<br/>
Dönüştürülecek değer.

*basamak*<br/>
Depolanan basamak sayısı.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır. Bir hata nedeniyle geçersiz bir parametre oluşursa (geçersiz değerler için aşağıdaki tabloya bakın), geçersiz parametre işleyicisi açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bir hata kodu döndürdü. Hata kodları Errno.h içinde tanımlanmıştır. Bu hataların listesi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Hata koşulları

|*Arabellek*|*sizeInBytes*|*value*|*basamak*|Döndür|Değer *arabellek*|
|--------------|-------------------|-------------|--------------|------------|-----------------------|
|**NULL**|tüm|tüm|tüm|**EINVAL**|Değiştirilmedi.|
|Değil **NULL** (noktaları için geçerli bellek)|sıfır|tüm|tüm|**EINVAL**|Değiştirilmedi.|
|Değil **NULL** (noktaları için geçerli bellek)|tüm|tüm|>= *sizeInBytes*|**EINVAL**|Değiştirilmedi.|

**Güvenlik Sorunları**

**_gcvt_s** bir erişim ihlali durumunda oluşturabilir *arabellek* geçerli bellek göstermiyor ve değil **NULL**.

## <a name="remarks"></a>Açıklamalar

**_Gcvt_s** işlevin bir kayan nokta dönüştürür *değeri* (, ondalık ayırıcıdan ve olası oturum bayt içeren) bir karakter dizesine ve dizesinde depolar *arabellek* . *Arabellek* dönüştürülen değer artı bir sonlandırma null otomatik olarak eklenir karakteri uyabilecek kadar büyük olmalıdır. Arabellek uzunluğu **_CVTBUFSIZE** herhangi bir değişken için yeterliyse noktası değeri. Arabellek boyutu, *basamak* + 1 kullanılır, işlevi son üzerine yazmaz arabelleği, bu nedenle bu işlem için yeterli arabellek sağladığınızdan emin olun. **_gcvt_s** üretmek çalışır *basamak* onlu basamak. Başaramazsa üreten *basamak* üstel biçimdeki rakamları. Sondaki sıfırlar dönüştürmede gizlenebilir.

C++'da, bu işlev tarafından bir şablon aşırı basitleştirilmiştir; aşırı yük, boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan arabellek uzunluğu bir otomatik olarak Infer. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).

Bu işlev hata ayıklama sürümü ilk arabellek 0xFD ile doldurur. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_gcvt_s**|\<stdlib.h >|\<Error.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_gcvt_s.c
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

int main()
{
    char buf[_CVTBUFSIZE];
    int decimal;
    int sign;
    int err;

    err = _gcvt_s(buf, _CVTBUFSIZE, 1.2, 5);

    if (err != 0)
    {
        printf("_gcvt_s failed with error code %d\n", err);
        exit(1);
    }

    printf("Converted value: %s\n", buf);
}
```

```Output
Converted value: 1.2
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt_s](ecvt-s.md)<br/>
[_fcvt_s](fcvt-s.md)<br/>
[_gcvt](gcvt.md)<br/>
