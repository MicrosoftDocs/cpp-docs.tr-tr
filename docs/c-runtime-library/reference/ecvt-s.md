---
description: 'Hakkında daha fazla bilgi edinin: _ecvt_s'
title: _ecvt_s
ms.date: 4/2/2020
api_name:
- _ecvt_s
- _o__ecvt_s
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
- ecvt_s
- _ecvt_s
helpviewer_keywords:
- _ecvt_s function
- ecvt_s function
- numbers, converting
- converting double numbers
ms.assetid: d52fb0a6-cb91-423f-80b3-952a8955d914
ms.openlocfilehash: abda39ce5c33a5f6b6cca0757411e16c4171cd97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206948"
---
# <a name="_ecvt_s"></a>_ecvt_s

Bir **`double`** sayıyı dizeye dönüştürür. Bu, [CRT 'Deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleriyle [_ecvt](ecvt.md) bir sürümüdür.

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
Basamak dizesinin işaretçisi, dönüştürmenin sonucu ile doldurulmuştur.

*_SizeInBytes*<br/>
Arabelleğin bayt cinsinden boyutu.

*_Value*<br/>
Dönüştürülecek sayı.

*_Count*<br/>
Depolanan basamak sayısı.

*_Dec*<br/>
Saklı ondalık noktası konumu.

*_Sign*<br/>
Dönüştürülen sayının işareti.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır. Hata varsa dönüş değeri bir hata kodudur. Hata kodları errno. h içinde tanımlanır. Daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Aşağıdaki tabloda listelendiği gibi geçersiz bir parametre söz konusu olduğunda, bu işlev [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **errno** ' ı **EINVAL** olarak ayarlar ve **EINVAL** döndürür.

### <a name="error-conditions"></a>Hata koşulları

|*_Buffer*|*_SizeInBytes*|_Value|_Count|_Dec|_Sign|Döndürülen değer|*Arabellekteki* değer|
|---------------|--------------------|-------------|-------------|-----------|------------|------------------|-----------------------|
|**DEĞER**|herhangi biri|herhangi biri|herhangi biri|herhangi biri|herhangi biri|**EıNVAL**|Değiştirilmedi.|
|**Null** değil (geçerli belleğe işaret eder)|<= 0|herhangi biri|herhangi biri|herhangi biri|herhangi biri|**EıNVAL**|Değiştirilmedi.|
|herhangi biri|herhangi biri|herhangi biri|herhangi biri|**DEĞER**|herhangi biri|**EıNVAL**|Değiştirilmedi.|
|herhangi biri|herhangi biri|herhangi biri|herhangi biri|herhangi biri|**DEĞER**|**EıNVAL**|Değiştirilmedi.|

## <a name="security-issues"></a>Güvenlik Sorunları

*arabellek* geçerli belleğe işaret etmezse ve **null** değilse **_ecvt_s** bir erişim ihlali oluşturabilir.

## <a name="remarks"></a>Açıklamalar

**_Ecvt_s** işlevi bir kayan nokta numarasını bir karakter dizesine dönüştürür. *_Value* parametresi dönüştürülecek kayan noktalı sayıdır. Bu işlev, *_Value* *sayı* rakamlarını bir dize olarak depolar ve null karakteri (' \ 0 ') ekler. *_Value* basamak sayısı *_Count* aşarsa, düşük sıra basamağı yuvarlanır. *Count* basamaktan daha azı varsa, dize sıfırlar ile doldurulur.

Yalnızca rakamlar dizede depolanır. Ondalık noktanın konumu ve *_Value* işareti, çağrıdan sonra *_Dec* ve *_Sign* elde edilebilir. *_Dec* parametresi, dizenin başlangıcına göre ondalık noktanın konumunu sağlayan bir tamsayı değerine işaret eder. 0 veya negatif bir tamsayı değeri, ondalık noktanın ilk basamağın solunda olduğunu gösterir. *_Sign* parametresi, dönüştürülmüş sayının işaretini gösteren bir tamsayıyı işaret eder. Tamsayı değeri 0 ise, sayı pozitif olur. Aksi takdirde, sayı negatif olur.

Bir arabellek uzunluğu **_CVTBUFSIZE** herhangi bir kayan nokta değeri için yeterlidir.

**_Ecvt_s** ve **_fcvt_s** arasındaki fark *_Count* parametresinin yorumlamasıdır. **_ecvt_s** , çıkış dizesindeki basamakların toplam sayısı olarak *_Count* yorumlarken **_fcvt_s** *_Count* ondalık ayırıcıdan sonraki basamak sayısı olarak yorumlar.

C++ ' da, bu işlevin kullanılması bir şablon aşırı yüklemesiyle basitleştirilmiştir; aşırı yükleme, arabellek uzunluğunu otomatik olarak çıkarabilir ve bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Bu işlevin hata ayıklama sürümü ilk olarak arabelleği 0xFE ile doldurur. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı başlık|
|--------------|---------------------|---------------------|
|**_ecvt_s**|\<stdlib.h>|\<errno.h>|

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

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt](ecvt.md)<br/>
[_fcvt_s](fcvt-s.md)<br/>
[_gcvt_s](gcvt-s.md)<br/>
