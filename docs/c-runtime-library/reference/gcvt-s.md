---
title: _gcvt_s
ms.date: 4/2/2020
api_name:
- _gcvt_s
- _o__gcvt_s
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 10d2b9af45b78a3f5ed673bde3d37894ccb00168
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345372"
---
# <a name="_gcvt_s"></a>_gcvt_s

Kayan nokta değerini bir dize dönüştürür. Bu, [CRT'deki Güvenlik Özellikleri'nde](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı gibi güvenlik geliştirmelerine sahip [_gcvt](gcvt.md) bir sürümüdür.

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
Dönüştürme sonucunu depolamak için arabellek.

*sizeBytes*<br/>
Arabelleğe boyutu.

*Değer*<br/>
Dönüştürülecek değer.

*rakamlar*<br/>
Depolanan önemli basamak sayısı.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır. Geçersiz bir parametre nedeniyle bir hata oluşursa (geçersiz değerler için aşağıdaki tabloya bakın), geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmenin devam etmesine izin verilirse, bir hata kodu döndürülür. Hata kodları Errno.h'de tanımlanır. Bu hataların listesi için [bkz: errno, _doserrno, _sys_errlist ve _sys_nerr.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)

### <a name="error-conditions"></a>Hata Koşulları

|*Arabellek*|*sizeBytes*|*Değer*|*rakamlar*|Dönüş|*Arabellekteki* değer|
|--------------|-------------------|-------------|--------------|------------|-----------------------|
|**Null**|herhangi bir|herhangi bir|herhangi bir|**Eınval**|Değiştirilmedi.|
|**NULL** değil (geçerli belleğe işaret)|sıfır|herhangi bir|herhangi bir|**Eınval**|Değiştirilmedi.|
|**NULL** değil (geçerli belleğe işaret)|herhangi bir|herhangi bir|>= *sizeBytes*|**Eınval**|Değiştirilmedi.|

**Güvenlik Sorunları**

**arabellek** geçerli belleğe işaret *etmiyorsa* ve **NULL**değilse _gcvt_s bir erişim ihlali oluşturabilir.

## <a name="remarks"></a>Açıklamalar

**_gcvt_s** işlevi kayan nokta *değerini* bir karakter dizesine dönüştürür (ondalık sayı ve olası bir işaret baytını içerir) ve dizeyi *arabellekte*depolar. *arabellek* dönüştürülen değeri artı otomatik olarak eklenen bir sonlandırıcı null karakter, karşılamak için yeterince büyük olmalıdır. Herhangi bir kayan nokta değeri için uzunluk **_CVTBUFSIZE** arabelleği yeterlidir. *Basamak* + 1 arabellek boyutu kullanılırsa, işlev arabelleğenin sonuna üzerine yazmaz, bu nedenle bu işlem için yeterli arabellek sağladığından emin olun. **_gcvt_s** ondalık biçimde *basamak* ları oluşturmaya çalışır. Yapamıyorsa, üstel biçimde *basamak basamakları* üretir. Sondaki sıfırlar dönüştürmede bastırılabilir.

C++'da, bu işlevi kullanmak şablon aşırı yüklemi ile basitleştirilir; aşırı yükleme arabellek uzunluğunu otomatik olarak çıkararak boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırabilir. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Bu işlevin hata ayıklama sürümü önce arabelleği 0xFE ile doldurur. Bu davranışı devre dışı kullanabilirsiniz, [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_gcvt_s**|\<stdlib.h>|\<error.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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
