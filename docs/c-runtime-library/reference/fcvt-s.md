---
title: _fcvt_s
ms.date: 04/05/2018
apiname:
- _fcvt_s
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
- fcvt_s
- _fcvt_s
helpviewer_keywords:
- fcvt_s function
- converting floating point, to strings
- floating-point functions, converting number to string
- _fcvt_s function
ms.assetid: 48671197-1d29-4c2b-a5d8-d2368f5f68a1
ms.openlocfilehash: 51ff3c675f1f53aee9beab629b17193164a2e7eb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334872"
---
# <a name="fcvts"></a>_fcvt_s

Bir kayan noktalı sayı, bir dizeye dönüştürür. Bu bir sürümüdür [_fcvt](fcvt.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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

*Arabellek*<br/>
Dönüştürme sonucunu tutacak sağlanan arabellek.

*sizeInBytes*<br/>
Arabelleğin bayt cinsinden boyutu.

*value*<br/>
Dönüştürülecek sayı.

*Sayısı*<br/>
Ondalık basamak sayısı.

*Ara*<br/>
Saklı ondalık noktasının konumunu işaretçisi.

*sign*<br/>
Depolanan oturum gösterge işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır. Bir hata varsa dönüş değeri bir hata kodudur. Hata kodları Errno.h içinde tanımlanır. Bu hataların bir listesi için bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Geçersiz bir parametre söz konusu olduğunda aşağıdaki tabloda listelendiği gibi bu işlev geçersiz parametre işleyicisi açıklandığı gibi çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse, bu işlev ayarlar **errno** için **EINVAL** ve döndürür **EINVAL**.

### <a name="error-conditions"></a>Hata koşulları

|*Arabellek*|*sizeInBytes*|value|count|dec|sign|döndürülecek|Değerini *arabelleği*|
|--------------|-------------------|-----------|-----------|---------|----------|------------|-----------------------|
|**NULL**|Tüm|Tüm|Tüm|Tüm|Tüm|**EINVAL**|Değiştirilmedi.|
|Değil **NULL** (geçerli bellek noktaları)|<=0|Tüm|Tüm|Tüm|Tüm|**EINVAL**|Değiştirilmedi.|
|Tüm|Tüm|Tüm|Tüm|**NULL**|Tüm|**EINVAL**|Değiştirilmedi.|
|Tüm|Tüm|Tüm|Tüm|Tüm|**NULL**|**EINVAL**|Değiştirilmedi.|

## <a name="security-issues"></a>Güvenlik Sorunları

**_fcvt_s** bir erişim ihlali durumunda üretebilir *arabellek* değil ve geçerli bellek işaret etmiyor **NULL**.

## <a name="remarks"></a>Açıklamalar

**_Fcvt_s** işlevi, null ile sonlandırılmış dizeye bir kayan noktalı sayıya dönüştürür. *Değer* parametredir dönüştürülecek kayan noktalı sayı. **_fcvt_s** rakamı depolar *değer* dize olarak ve null karakteri ('\0') ekler. *Sayısı* parametresi, ondalık ayırıcıdan sonra depolanacak basamak sayısını belirtir. Fazlalık basamaklar yuvarlanır için *sayısı* yerleştirir. Değerinden daha az *sayısı* basamak duyarlılığındadır dize sıfır sıfır.

Yalnızca rakam, dizede depolanır. Ondalık ve işaretini konumunu *değer* örneğinden alınabilen *Ara* ve *oturum* çağrısından sonra. *Ara* tamsayı değerine; parametresinin işaret bu tamsayı değeri ondalık dizenin başlangıcına göre konumunu sağlar. Sıfır veya negatif tamsayı değeri, Ondalık ayırıcının sol tarafında ilk basamak yer gösterir. Parametre *oturum* işaret işaretini belirten bir tamsayı *değer*. Bir tamsayı ise 0 olarak ayarlanırsa *değer* pozitif ve sıfır olmayan bir sayı if ayarlanır *değer* negatiftir.

Arabellek uzunluğu **_CVTBUFSIZE** herhangi bir değişken için yeterliyse noktası değeri.

Arasındaki fark **_ecvt_s** ve **_fcvt_s** öğesinin yorumlamasıdır içinde *sayısı* parametresi. **_ecvt_s** yorumlar *sayısı* toplam çıkış dizesindeki basamak sayısı arttıkça ve **_fcvt_s** yorumlar *sayısı* basamak sayısı ondalık noktası.

C++'da, bu işlevi kullanarak bir şablon aşırı yük tarafından basitleştirilmiştir; aşırı yükleme arabellek uzunluğunu otomatik olarak, bir boyut bağımsız değişkeni belirtme gereksinimi ortadan çıkarabilir. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Hata ayıklama sürümü, bu işlevin ilk arabellek 0xFD ile doldurur. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı başlık|
|--------------|---------------------|---------------------|
|**_fcvt_s**|\<stdlib.h >|\<errno.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kitaplıklar:** Tüm sürümleri [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md).

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

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt_s](ecvt-s.md)<br/>
[_gcvt_s](gcvt-s.md)<br/>
[_fcvt](fcvt.md)<br/>
