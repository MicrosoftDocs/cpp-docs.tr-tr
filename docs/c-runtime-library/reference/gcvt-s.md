---
title: _gcvt_s
ms.date: 04/05/2018
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
ms.openlocfilehash: 168e0657150d072bbe41cd0ad6e914ca1f53e512
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50554974"
---
# <a name="gcvts"></a>_gcvt_s

Bir kayan nokta değeri, bir dizeye dönüştürür. Bu bir sürümüdür [_gcvt](gcvt.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
Dönüştürme sonucu olarak depolayan arabellek.

*sizeInBytes*<br/>
Arabellek boyutu.

*value*<br/>
Dönüştürülecek değer.

*basamak*<br/>
Depolanan anlamlı basamak sayısı.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır. Geçersiz bir parametre nedeniyle bir hata oluşursa (geçersiz değerler için aşağıdaki tabloya bakın), açıklandığı gibi geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin, bir hata kodu döndürülür. Hata kodları Errno.h içinde tanımlanır. Bu hataların bir listesi için bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Hata koşulları

|*Arabellek*|*sizeInBytes*|*value*|*basamak*|döndürülecek|Değerini *arabelleği*|
|--------------|-------------------|-------------|--------------|------------|-----------------------|
|**NULL**|Tüm|Tüm|Tüm|**EINVAL**|Değiştirilmedi.|
|Değil **NULL** (geçerli bellek noktaları)|sıfır|Tüm|Tüm|**EINVAL**|Değiştirilmedi.|
|Değil **NULL** (geçerli bellek noktaları)|Tüm|Tüm|>= *sizeInBytes*|**EINVAL**|Değiştirilmedi.|

**Güvenlik Sorunları**

**_gcvt_s** bir erişim ihlali durumunda oluşturabilirsiniz *arabellek* değil ve geçerli bellek işaret etmiyor **NULL**.

## <a name="remarks"></a>Açıklamalar

**_Gcvt_s** işlevi dönüştürür bir kayan nokta *değer* (kod bir ondalık noktası ve olası oturum bayt içerir) bir karakter dizesine ve dizesini depolar *arabellek* . *Arabellek* dönüştürülen değeri ayrıca otomatik olarak eklenir, sonlandırıcı null karakterini, tutabilecek kadar büyük olmalıdır. Arabellek uzunluğu **_CVTBUFSIZE** herhangi bir değişken için yeterliyse noktası değeri. Arabellek boyutu, *basamak* + 1 kullanılır, işlev sona üzerine yazmaz arabelleği, bu nedenle bu işlem için yeterli arabellek sağladığınızdan emin olun. **_gcvt_s** üretir *basamak* onlu basamak. Erişilemiyorsa ürettiği *basamak* üstel biçimde basamak. Sondaki sıfırları dönüştürme gizlenebilir.

C++'da, bu işlevi kullanarak bir şablon aşırı yük tarafından basitleştirilmiştir; aşırı yükleme arabellek uzunluğunu otomatik olarak, bir boyut bağımsız değişkeni belirtme gereksinimi ortadan çıkarabilir. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Hata ayıklama sürümü, bu işlevin ilk arabellek 0xFD ile doldurur. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_gcvt_s**|\<stdlib.h >|\<Error.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
