---
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 80f02467e160e3196982c10576ad55f5487e5fc1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347452"
---
# <a name="_fcvt_s"></a>_fcvt_s

Kayan nokta sayısını bir dize dönüştürür. Bu, [CRT'deki Güvenlik Özellikleri'nde](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı gibi güvenlik geliştirmelerine sahip [_fcvt](fcvt.md) bir sürümüdür.

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

*sizeBytes*<br/>
Baytlarda arabelleğen boyutu.

*Değer*<br/>
Dönüştürülecek numara.

*Sayısı*<br/>
Ondalık noktadan sonraki basamak sayısı.

*dec*<br/>
Depolanan ondalık nokta konumunu işaretçi.

*Işareti*<br/>
Depolanan işaret göstergesini işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır. İade değeri, bir hata varsa bir hata kodudur. Hata kodları Errno.h'de tanımlanır. Bu hataların listesi için [bkz: errno, _doserrno, _sys_errlist ve _sys_nerr.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)

Aşağıdaki tabloda listelenen geçersiz bir parametre durumunda, bu işlev [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmedevam etmesine izin verilirse, bu işlev **EINVAL için errno** ayarlar ve **EINVAL** döndürür. **EINVAL**

### <a name="error-conditions"></a>Hata Koşulları

|*Arabellek*|*sizeBytes*|value|count|dec|sign|Dönüş|*Arabellekteki* değer|
|--------------|-------------------|-----------|-----------|---------|----------|------------|-----------------------|
|**Null**|herhangi bir|herhangi bir|herhangi bir|herhangi bir|herhangi bir|**Eınval**|Değiştirilmedi.|
|**NULL** değil (geçerli belleğe işaret)|<=0|herhangi bir|herhangi bir|herhangi bir|herhangi bir|**Eınval**|Değiştirilmedi.|
|herhangi bir|herhangi bir|herhangi bir|herhangi bir|**Null**|herhangi bir|**Eınval**|Değiştirilmedi.|
|herhangi bir|herhangi bir|herhangi bir|herhangi bir|herhangi bir|**Null**|**Eınval**|Değiştirilmedi.|

## <a name="security-issues"></a>Güvenlik Sorunları

**_fcvt_s,** *arabellek* geçerli belleğe işaret etmiyorsa ve **NULL**değilse bir erişim ihlali oluşturabilir.

## <a name="remarks"></a>Açıklamalar

**_fcvt_s** işlevi kayan nokta numarasını null-sonlandırılan karakter dizesine dönüştürür. *Değer* parametresi dönüştürülecek kayan nokta sayısıdır. **_fcvt_s** *değeri* bir dize olarak depolar ve null bir karakter ('\0') ekler. *Sayı* parametresi ondalık noktadan sonra depolanacak basamak sayısını belirtir. Fazla basamaklar yerleri *saymak* için yuvarlanır. *Kesinlik sayısı* basamaklarından daha az varsa, dize sıfırlarla tamamlanır.

Dizede yalnızca basamaklar depolanır. Ondalık noktanın konumu ve *değer* işareti *dec* ve çağrıdan sonra *işareti* elde edilebilir. *Dec* parametresi bir onsdeğerine işaret ediyor; bu tamsayı değeri, dize başına göre ondalık noktanın konumunu verir. Sıfır veya negatif tamsayı değeri, ondalık noktanın ilk basamaktan solunda olduğunu gösterir. Parametre *işareti,* *değer*işaretini gösteren bir bir yaslamayı işaret ediyor. *Değer* pozitifse tamsayı 0 olarak ayarlanır ve *değer* negatifse sıfır olmayan bir sayıya ayarlanır.

Herhangi bir kayan nokta değeri için uzunluk **_CVTBUFSIZE** arabelleği yeterlidir.

**_ecvt_s** ve **_fcvt_s** arasındaki *fark, sayım* parametresinin yorumlanmasındadır. **_ecvt_s,** çıkış dizesindeki toplam basamak sayısı olarak *sayılır* ve **_fcvt_s** ondalık noktadan sonraki basamak sayısı olarak *sayılır.*

C++'da, bu işlevi kullanmak şablon aşırı yüklemi ile basitleştirilir; aşırı yükleme arabellek uzunluğunu otomatik olarak çıkararak boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırabilir. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Bu işlevin hata ayıklama sürümü önce arabelleği 0xFE ile doldurur. Bu davranışı devre dışı kullanabilirsiniz, [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı üstbilgi|
|--------------|---------------------|---------------------|
|**_fcvt_s**|\<stdlib.h>|\<errno.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

**Kütüphaneler:** [CRT Kitaplık Özellikleri'nin](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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
