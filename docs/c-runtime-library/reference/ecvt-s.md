---
title: _ecvt_s
ms.date: 04/05/2018
apiname:
- _ecvt_s
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
- ecvt_s
- _ecvt_s
helpviewer_keywords:
- _ecvt_s function
- ecvt_s function
- numbers, converting
- converting double numbers
ms.assetid: d52fb0a6-cb91-423f-80b3-952a8955d914
ms.openlocfilehash: 0123c618eb5ba614bd8e5b5b3f1f4b0aff539c4c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62288265"
---
# <a name="ecvts"></a>_ecvt_s

Dönüştürür bir **çift** bir dizeye sayı. Bu bir sürümüdür [_ecvt](ecvt.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t _ecvt_s(
   char * _Buffer,
   size_t _SizeInBytes,
   double _Value,
   int _Count,
   int *_Dec,
   int *_Sign
);
template <size_t size>
errno_t _ecvt_s(
   char (&_Buffer)[size],
   double _Value,
   int _Count,
   int *_Dec,
   int *_Sign
); // C++ only
```

### <a name="parameters"></a>Parametreler

*_Buffer*<br/>
Bir rakam dizesiyle, dönüştürmenin sonucu işaretçisi ile doldurulur.

*_SizeInBytes*<br/>
Arabelleğin bayt cinsinden boyutu.

*_Değeri*<br/>
Dönüştürülecek sayı.

*_Count*<br/>
Depolanan basamak sayısı.

*_Dec*<br/>
Ondalık noktasının konumunu depolanır.

*_Oturum*<br/>
Dönüştürülen sayının işaretini.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır. Bir hata varsa dönüş değeri bir hata kodudur. Hata kodları Errno.h içinde tanımlanır. Daha fazla bilgi için [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Geçersiz bir parametre söz konusu olduğunda aşağıdaki tabloda listelendiği gibi bu işlev geçersiz parametre işleyicisi açıklandığı gibi çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse, bu işlev ayarlar **errno** için **EINVAL** ve döndürür **EINVAL**.

### <a name="error-conditions"></a>Hata koşulları

|*_Buffer*|*_SizeInBytes*|_Değeri|_Count|_Dec|_Sign|Dönüş değeri|Değerini *arabelleği*|
|---------------|--------------------|-------------|-------------|-----------|------------|------------------|-----------------------|
|**NULL**|Tüm|Tüm|Tüm|Tüm|Tüm|**EINVAL**|Değiştirilmedi.|
|Değil **NULL** (geçerli bellek noktaları)|<=0|Tüm|Tüm|Tüm|Tüm|**EINVAL**|Değiştirilmedi.|
|Tüm|Tüm|Tüm|Tüm|**NULL**|Tüm|**EINVAL**|Değiştirilmedi.|
|Tüm|Tüm|Tüm|Tüm|Tüm|**NULL**|**EINVAL**|Değiştirilmedi.|

## <a name="security-issues"></a>Güvenlik Sorunları

**_ecvt_s** bir erişim ihlali durumunda üretebilir *arabellek* değil ve geçerli bellek işaret etmiyor **NULL**.

## <a name="remarks"></a>Açıklamalar

**_Ecvt_s** işlevi, bir karakter dizesindeki bir kayan noktalı sayıya dönüştürür. *_Değeri* parametredir dönüştürülecek kayan noktalı sayı. Bu işlev kadar depolar *sayısı* rakamı *_Değeri* dize olarak ve null karakteri ('\0') ekler. Varsa basamak sayısı *_Değeri* aşıyor *_Count*, düşük düzey basamak yuvarlanır. Değerinden daha az *sayısı* basamak, dize sıfır sıfır.

Yalnızca rakam, dizede depolanır. Ondalık ve işaretini konumunu *_Değeri* örneğinden alınabilen *_Dec* ve *_oturum* çağrısından sonra. *_Dec* parametresi dizenin başlangıcına göre ondalık noktasının konumunu vermiş bir tamsayı değeri işaret eder. 0 veya negatif bir tamsayı değeri, Ondalık ayırıcının sol tarafında ilk basamak yer gösterir. *_Oturum* parametresi işaret dönüştürülmüş sayının işaretini belirten bir tamsayı. Tamsayı değeri 0 ise, pozitif bir sayıdır. Aksi takdirde, negatif sayıdır.

Arabellek uzunluğu **_CVTBUFSIZE** için herhangi bir kayan nokta değer yeterlidir.

Arasındaki fark **_ecvt_s** ve **_fcvt_s** öğesinin yorumlamasıdır içinde *_Count* parametresi. **_ecvt_s** yorumlar *_Count* çıkış dizesindeki basamak sayısı olarak ise **_fcvt_s** yorumlar *_Count* basamak sayısı ondalık noktası.

C++'da, bu işlevi kullanarak bir şablon aşırı yük tarafından basitleştirilmiştir; aşırı yükleme arabellek uzunluğunu otomatik olarak, bir boyut bağımsız değişkeni belirtme gereksinimi ortadan çıkarabilir. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Hata ayıklama sürümü, bu işlevin ilk arabellek 0xFD ile doldurur. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı başlık|
|--------------|---------------------|---------------------|
|**_ecvt_s**|\<stdlib.h >|\<errno.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// ecvt_s.c
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

int main( )
{
    char * buf = 0;
    int decimal;
    int sign;
    int err;

    buf = (char*) malloc(_CVTBUFSIZE);
    err = _ecvt_s(buf, _CVTBUFSIZE, 1.2, 5, &decimal, &sign);

    if (err != 0)
    {
        printf("_ecvt_s failed with error code %d\n", err);
        exit(1);
    }

    printf("Converted value: %s\n", buf);
}
```

```Output
Converted value: 12000
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt](ecvt.md)<br/>
[_fcvt_s](fcvt-s.md)<br/>
[_gcvt_s](gcvt-s.md)<br/>
