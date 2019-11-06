---
title: _gcvt_s
ms.date: 04/05/2018
api_name:
- _gcvt_s
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
- api-ms-win-crt-convert-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: da36641f6a3ba8dc1da0894aedbfa390d2e796ae
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73625043"
---
# <a name="_gcvt_s"></a>_gcvt_s

Kayan nokta değerini bir dizeye dönüştürür. Bu, [CRT 'Deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklanan güvenlik geliştirmeleriyle [_gcvt](gcvt.md) 'in bir sürümüdür.

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

*arabelleğin*<br/>
Dönüştürmenin sonucunu depolayan arabellek.

*sizeInBytes*<br/>
Arabelleğin boyutu.

*value*<br/>
Dönüştürülecek değer.

*54*<br/>
Depolanan önemli basamak sayısı.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır. Geçersiz bir parametre nedeniyle hata oluşursa (geçersiz değerler için aşağıdaki tabloya bakın), geçersiz parametre işleyicisi [parametre doğrulamada](../../c-runtime-library/parameter-validation.md)açıklandığı şekilde çağrılır. Yürütmenin devam etmesine izin veriliyorsa bir hata kodu döndürülür. Hata kodları errno. h içinde tanımlanır. Bu hataların listesi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

### <a name="error-conditions"></a>Hata koşulları

|*arabelleğin*|*sizeInBytes*|*value*|*54*|döndürülmesini|*Arabellekteki* değer|
|--------------|-------------------|-------------|--------------|------------|-----------------------|
|**DEĞER**|Kaydedilmemiş|Kaydedilmemiş|Kaydedilmemiş|**EıNVAL**|Değiştirilmedi.|
|**Null** değil (geçerli belleğe işaret eder)|sıfır|Kaydedilmemiş|Kaydedilmemiş|**EıNVAL**|Değiştirilmedi.|
|**Null** değil (geçerli belleğe işaret eder)|Kaydedilmemiş|Kaydedilmemiş|>= *sizeInBytes*|**EıNVAL**|Değiştirilmedi.|

**Güvenlik Sorunları**

*arabellek* geçerli belleğe işaret etmezse ve **null**değilse, **_gcvt_s** bir erişim ihlali oluşturabilir.

## <a name="remarks"></a>Açıklamalar

**_Gcvt_s** işlevi, bir kayan nokta *değerini* bir karakter dizesine (bir ondalık işaret ve olası bir işaret baytı içerir) dönüştürür ve dizeyi *arabelleğe*depolar. *arabellek* , dönüştürülmüş değere ve otomatik olarak eklenen bir Sonlandırıcı null karaktere yetecek kadar büyük olmalıdır. Her kayan nokta değeri için **_Cvtbufsize** uzunluğunda bir arabellek yeterlidir. Bir arabellek *boyutu + 1* kullanılırsa, işlev arabelleğin sonunun üzerine yazmaz, bu nedenle bu işlem için yeterli bir arabellek girdiğinizden emin olun. **_gcvt_s** ondalık biçimde *basamak* rakamları üretmeye çalışır. Yapamazsa, *sayı* rakamlarını üstel biçimde üretir. Sondaki sıfırlar dönüşümde gizlenebilir.

' C++De, bu işlevin kullanılması şablon aşırı yüklemesiyle basitleştirilmiştir; aşırı yükleme, arabellek uzunluğunu otomatik olarak çıkarabilir ve bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Bu işlevin hata ayıklama sürümü ilk olarak arabelleği 0xFE ile doldurur. Bu davranışı devre dışı bırakmak için [_Crtsetdebugfillthreshold](crtsetdebugfillthreshold.md)kullanın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_gcvt_s**|\<Stdlib. h >|\<hatası. h >|

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
