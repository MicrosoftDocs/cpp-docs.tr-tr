---
description: 'Hakkında daha fazla bilgi edinin: _fcvt_s'
title: _fcvt_s
ms.date: 4/2/2020
api_name:
- _fcvt_s
- _o__fcvt_s
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fcvt_s
- _fcvt_s
helpviewer_keywords:
- fcvt_s function
- converting floating point, to strings
- floating-point functions, converting number to string
- _fcvt_s function
ms.assetid: 48671197-1d29-4c2b-a5d8-d2368f5f68a1
ms.openlocfilehash: 62b72a9f71f967077169086371ebf36542b154ed
ms.sourcegitcommit: 90c300b74f6556cb5d989802d2e80d79542f55e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2021
ms.locfileid: "102514453"
---
# <a name="_fcvt_s"></a>_fcvt_s

Kayan noktalı sayıyı dizeye dönüştürür. Bu, [CRT 'Deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleriyle [_fcvt](fcvt.md) bir sürümüdür.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _fcvt_s(
   char* buffer,
   size_t sizeInBytes,
   double value,
   int count,
   int *dec,
   int *sign
);
template <size_t size>
errno_t _fcvt_s(
   char (&buffer)[size],
   double value,
   int count,
   int *dec,
   int *sign
); // C++ only
```

### <a name="parameters"></a>Parametreler

*arabelleğin*<br/>
Dönüştürme sonucunu tutacak olan sağlanan arabellek.

*sizeInBytes*<br/>
Arabelleğin bayt cinsinden boyutu.

*değer*<br/>
Dönüştürülecek sayı.

*biriktirme*<br/>
Ondalık ayırıcıdan sonraki basamak sayısı.

*dec*<br/>
Depolanan ondalık noktası konumu işaretçisi.

*sign*<br/>
Saklı işaret göstergesinin işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır. Hata varsa dönüş değeri bir hata kodudur. Hata kodları errno. h içinde tanımlanır. Bu hataların listesi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Aşağıdaki tabloda listelendiği gibi geçersiz bir parametre söz konusu olduğunda, bu işlev [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **errno** ' ı **EINVAL** olarak ayarlar ve **EINVAL** döndürür.

### <a name="error-conditions"></a>Hata koşulları

|*arabelleğin*|*sizeInBytes*|değer|count|dec|sign|Döndürülmesini|*Arabellekteki* değer|
|--------------|-------------------|-----------|-----------|---------|----------|------------|-----------------------|
|**DEĞER**|herhangi biri|herhangi biri|herhangi biri|herhangi biri|herhangi biri|**EıNVAL**|Değiştirilmedi.|
|**Null** değil (geçerli belleğe işaret eder)|<= 0|herhangi biri|herhangi biri|herhangi biri|herhangi biri|**EıNVAL**|Değiştirilmedi.|
|herhangi biri|herhangi biri|herhangi biri|herhangi biri|**DEĞER**|herhangi biri|**EıNVAL**|Değiştirilmedi.|
|herhangi biri|herhangi biri|herhangi biri|herhangi biri|herhangi biri|**DEĞER**|**EıNVAL**|Değiştirilmedi.|

## <a name="security-issues"></a>Güvenlik Sorunları

*arabellek* geçerli belleğe işaret etmezse ve **null** değilse **_fcvt_s** bir erişim ihlali oluşturabilir.

## <a name="remarks"></a>Açıklamalar

**_Fcvt_s** işlevi, kayan noktalı bir sayıyı null ile sonlandırılmış bir karakter dizesine dönüştürür. *Değer* parametresi dönüştürülecek kayan noktalı sayıdır. **_fcvt_s** *değer* rakamlarını bir dize olarak depolar ve null karakteri (' \ 0 ') ekler. *Count* parametresi, ondalık ayırıcıdan sonra depolanacak basamak sayısını belirtir. Fazla basamak *sayısı basamak sayısına* yuvarlanır. *Daha az duyarlık basamağı basamak* varsa, dize sıfırlar ile doldurulur.

Yalnızca rakamlar dizede depolanır. Ondalık noktanın konumu ve *değer* işareti, çağrıdan sonra *Ara* ve *imzala* öğesinden elde edilebilir. *Dec* parametresi bir tamsayı değerine işaret eder; Bu tamsayı değeri, dizenin başlangıcına göre ondalık noktanın konumunu verir. Sıfır veya negatif tamsayı değeri, ondalık noktanın ilk basamağın solunda olduğunu gösterir. Parametre *işareti* , *değer* işaretini gösteren bir tamsayıya işaret eder. *Değer* pozitifse, tamsayı 0 olarak ayarlanır ve *değer* negatifse sıfır dışında bir sayı olarak ayarlanır.

Bir arabellek uzunluğu **_CVTBUFSIZE** herhangi bir kayan nokta değeri için yeterlidir.

**_Ecvt_s** ve **_fcvt_s** arasındaki fark *Count* parametresinin yorumlamasıdır. **_ecvt_s** *sayıyı* çıkış dizesindeki toplam basamak sayısı olarak yorumlar ve **_fcvt_s** *sayıyı* ondalık ayırıcıdan sonraki basamak sayısı olarak yorumlar.

C++ ' da, bu işlevin kullanılması bir şablon aşırı yüklemesiyle basitleştirilmiştir; aşırı yükleme, arabellek uzunluğunu otomatik olarak çıkarabilir ve bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Bu işlevin hata ayıklama sürümü ilk olarak arabelleği 0xFE ile doldurur. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı başlık|
|--------------|---------------------|---------------------|
|**_fcvt_s**|\<stdlib.h>|\<errno.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kitaplıklar:** [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="example"></a>Örnek

```C
// fcvt_s.c
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

int main()
{
    char * buf = 0;
    int decimal;
    int sign;
    int err;

    buf = (char*) malloc(_CVTBUFSIZE);
    err = _fcvt_s(buf, _CVTBUFSIZE, 1.2, 5, &decimal, &sign);

    if (err != 0)
    {
        printf("_fcvt_s failed with error code %d\n", err);
        exit(1);
    }

    printf("Converted value: %s\n", buf);
}
```

```Output
Converted value: 120000
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt_s](ecvt-s.md)<br/>
[_gcvt_s](gcvt-s.md)<br/>
[_fcvt](fcvt.md)<br/>
