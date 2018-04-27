---
title: _ecvt_s | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _ecvt_s function
- ecvt_s function
- numbers, converting
- converting double numbers
ms.assetid: d52fb0a6-cb91-423f-80b3-952a8955d914
caps.latest.revision: 25
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6f3cfd36a2a1466a66e4febfcbfc9e00b0b0e47a
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="ecvts"></a>_ecvt_s

Dönüştüren bir **çift** dizeye sayı. Bu bir sürümüdür [_ecvt](ecvt.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
İşaretçi dönüştürme işleminin sonucu olan basamak dizisi ile doldurulur.

*_SizeInBytes*<br/>
Arabelleğin bayt cinsinden boyutu.

*_Value*<br/>
Dönüştürülecek sayı.

*_Count*<br/>
Depolanan basamak sayısı.

*_Dec*<br/>
Ondalık noktasının konumunu depolanır.

*_Sign*<br/>
Dönüştürülen sayısının işareti.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır. Bir hata olduğunda dönüş değeri bir hata kodudur. Hata kodları Errno.h içinde tanımlanmıştır. Daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Geçersiz bir parametre söz konusu olduğunda aşağıdaki tabloda listelendiği gibi bu işlevi geçersiz parametre işleyicisi açıklandığı gibi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev devam etmek için yürütülmesine izin veriliyorsa, ayarlar **errno** için **EINVAL** ve döndürür **EINVAL**.

### <a name="error-conditions"></a>Hata koşulları

|*_Buffer*|*_SizeInBytes*|_Value|_Count|_Dec|_Sign|Dönüş değeri|Değer *arabellek*|
|---------------|--------------------|-------------|-------------|-----------|------------|------------------|-----------------------|
|**NULL**|tüm|tüm|tüm|tüm|tüm|**EINVAL**|Değiştirilmedi.|
|Değil **NULL** (noktaları için geçerli bellek)|<=0|tüm|tüm|tüm|tüm|**EINVAL**|Değiştirilmedi.|
|tüm|tüm|tüm|tüm|**NULL**|tüm|**EINVAL**|Değiştirilmedi.|
|tüm|tüm|tüm|tüm|tüm|**NULL**|**EINVAL**|Değiştirilmedi.|

## <a name="security-issues"></a>Güvenlik sorunları

**_ecvt_s** bir erişim ihlali durumunda oluşturabilir *arabellek* geçerli bellek göstermiyor ve değil **NULL**.

## <a name="remarks"></a>Açıklamalar

**_Ecvt_s** işlevi bir karakter dizesi kayan noktalı sayı dönüştürür. *_Value* dönüştürülecek kayan noktalı sayı parametresidir. Bu işlev kadar saklar *sayısı* rakamı *_Value* dize olarak ve bir null karakter ('\0') ekler. Varsa basamak sayısı *_Value* aşıyor *_Count*, düşük düzey basamaklı yuvarlanır. Varsa daha az *sayısı* basamak, dize sıfırlarla doldurulan.

Yalnızca rakamlar dizesinde depolanır. Ondalık ayırıcının ve işaretini konumunu *_Value* yükseltebilmeniz *_Dec* ve *_Sign* çağrısından sonra. *_Dec* parametresi dizenin başlangıcını göre Ondalık ayırıcının konumunu vermiş bir tamsayı değeri işaret eder. 0 veya eksi tamsayı değeri, Ondalık ayırıcının ilk rakam solunda kalan gösterir. *_Sign* parametresi işaret dönüştürülen sayının işaretini gösteren bir tamsayı. Tamsayı değer 0 ise, pozitif bir sayıdır. Aksi takdirde, negatif sayısıdır.

Arabellek uzunluğu **_CVTBUFSIZE** için herhangi bir kayan nokta değerini yeterlidir.

Arasındaki farkı **_ecvt_s** ve **_fcvt_s** yorumu içinde olduğu *_Count* parametresi. **_ecvt_s** yorumlar *_Count* toplam çıkış dizesinde basamak sayısı olarak ancak **_fcvt_s** yorumlar *_Count* basamak sayısı Ondalık ayırıcının.

C++'da, bu işlev tarafından bir şablon aşırı basitleştirilmiştir; aşırı yük, boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan arabellek uzunluğu bir otomatik olarak Infer. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).

Bu işlev hata ayıklama sürümü ilk arabellek 0xFD ile doldurur. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı üstbilgi|
|--------------|---------------------|---------------------|
|**_ecvt_s**|\<stdlib.h >|\<errno.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
