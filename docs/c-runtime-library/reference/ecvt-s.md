---
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: e33840e772de770e0f05ae45d2c2d4bec7e09939
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348055"
---
# <a name="_ecvt_s"></a>_ecvt_s

**Çift** sayıyı dize dönüştürür. Bu, [CRT'deki Güvenlik Özellikleri'nde](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı gibi güvenlik geliştirmelerine sahip [_ecvt](ecvt.md) bir sürümüdür.

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
Sayışla doldu, dönüştürme sonucu, basamak lar dizesine işaretçiyle doldurulur.

*_SizeInBytes*<br/>
Arabellek bayt boyutu.

*_value*<br/>
Dönüştürülecek numara.

*_count*<br/>
Depolanan basamak sayısı.

*_Dec*<br/>
Depolanan ondalık nokta konumu.

*_Sign*<br/>
Dönüştürülen sayının işareti.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır. İade değeri, bir hata varsa bir hata kodudur. Hata kodları Errno.h'de tanımlanır. Daha fazla bilgi için [bkz: errno, _doserrno, _sys_errlist ve _sys_nerr.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)

Aşağıdaki tabloda listelenen geçersiz bir parametre durumunda, bu işlev [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmedevam etmesine izin verilirse, bu işlev **EINVAL için errno** ayarlar ve **EINVAL** döndürür. **EINVAL**

### <a name="error-conditions"></a>Hata Koşulları

|*_Buffer*|*_SizeInBytes*|_value|_count|_Dec|_Sign|Döndürülen değer|*Arabellekteki* değer|
|---------------|--------------------|-------------|-------------|-----------|------------|------------------|-----------------------|
|**Null**|herhangi bir|herhangi bir|herhangi bir|herhangi bir|herhangi bir|**Eınval**|Değiştirilmedi.|
|**NULL** değil (geçerli belleğe işaret)|<=0|herhangi bir|herhangi bir|herhangi bir|herhangi bir|**Eınval**|Değiştirilmedi.|
|herhangi bir|herhangi bir|herhangi bir|herhangi bir|**Null**|herhangi bir|**Eınval**|Değiştirilmedi.|
|herhangi bir|herhangi bir|herhangi bir|herhangi bir|herhangi bir|**Null**|**Eınval**|Değiştirilmedi.|

## <a name="security-issues"></a>Güvenlik Sorunları

**arabellek** geçerli belleğe işaret *etmiyorsa* ve **NULL**değilse _ecvt_s bir erişim ihlali oluşturabilir.

## <a name="remarks"></a>Açıklamalar

**_ecvt_s** işlevi kayan nokta sayısını bir karakter dizesine dönüştürür. *_Value* parametresi dönüştürülecek kayan nokta sayısıdır. Bu *işlev, _Value* basamaklarını bir dize olarak *saymak* için depolar ve null karakterini ('\0') ekler. *_Value'daki* basamak sayısı *_Count*aşıyorsa, düşük sıralı basamak yuvarlanır. *Sayı* basamaklarından daha az sayı varsa, dize sıfırlarla tamamlanır.

Dizede yalnızca basamaklar depolanır. Ondalık noktanın konumu ve *_Value* işareti *_Dec* ve *çağrıdan* sonra _Sign elde edilebilir. *_Dec* parametresi, dize başına göre ondalık noktakonumunu veren bir tamsayı değerine işaret verir. 0 veya negatif tamsayı değeri, ondalık noktanın ilk basamaktan solunda olduğunu gösterir. *_Sign* parametresi dönüştürülen sayının işaretini gösteren bir tamsayıya işaret edin. Tamsayı değeri 0 ise, sayı pozitiftir. Aksi takdirde, sayı negatiftir.

Herhangi bir kayan nokta değeri için uzunluk **_CVTBUFSIZE** arabelleği yeterlidir.

**_ecvt_s** ve **_fcvt_s** arasındaki fark *_Count* parametrenin yorumlanmasındadır. **_ecvt_s** *_Count* çıkış dizesinde toplam basamak sayısı olarak yorumlarken, **_fcvt_s** *_Count* ondalık basamaktan sonraki basamak sayısı olarak yorumlar.

C++'da, bu işlevi kullanmak şablon aşırı yüklemi ile basitleştirilir; aşırı yükleme arabellek uzunluğunu otomatik olarak çıkararak boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırabilir. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Bu işlevin hata ayıklama sürümü önce arabelleği 0xFE ile doldurur. Bu davranışı devre dışı kullanabilirsiniz, [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı üstbilgi|
|--------------|---------------------|---------------------|
|**_ecvt_s**|\<stdlib.h>|\<errno.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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
