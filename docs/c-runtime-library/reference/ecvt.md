---
title: _ecvt
ms.date: 4/2/2020
api_name:
- _ecvt
- _o__ecvt
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
- _ecvt
helpviewer_keywords:
- _ecvt function
- numbers, converting
- converting double numbers
- ecvt function
ms.assetid: a916eb05-92d1-4b5c-8563-093acdb49dc8
ms.openlocfilehash: 5e1760d5c68e650f6fbf44866d4e368b9d6233b6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348021"
---
# <a name="_ecvt"></a>_ecvt

**Çift** sayıyı dize dönüştürür. Bu işlevin daha güvenli bir sürümü mevcuttur; [bkz. _ecvt_s](ecvt-s.md).

## <a name="syntax"></a>Sözdizimi

```C
char *_ecvt(
   double value,
   int count,
   int *dec,
   int *sign
);
```

### <a name="parameters"></a>Parametreler

*Değer*<br/>
Dönüştürülecek numara.

*Sayısı*<br/>
Depolanan basamak sayısı.

*dec*<br/>
Depolanan ondalık nokta konumu.

*Işareti*<br/>
Dönüştürülen sayının işareti.

## <a name="return-value"></a>Dönüş Değeri

**_ecvt** bir işaretçiyi basamak dizesine döndürür; Bir hata oluştuysa **NULL.**

## <a name="remarks"></a>Açıklamalar

**_ecvt** işlevi kayan nokta sayısını bir karakter dizesine dönüştürür. *Değer* parametresi dönüştürülecek kayan nokta sayısıdır. Bu *işlev, değer* basamaklarını bir dize olarak *saymak* için depolar ve null karakterini ('\0') ekler. *Değerdeki* basamak sayısı *sayıyı*aşıyorsa, düşük sıralı basamak yuvarlanır. *Sayı* basamaklarından daha az sayı varsa, dize sıfırlarla tamamlanır.

**_ecvt** tarafından döndürülen toplam basamak sayısı **_CVTBUFSIZE**geçmeyecek.

Dizede yalnızca basamaklar depolanır. Ondalık noktanın konumu ve *değer* işareti *dec* ve çağrıdan sonra *işareti* elde edilebilir. *Dec* parametresi, dize başına göre ondalık noktanın konumunu veren bir bir sonda değerine işaret ediyor. 0 veya negatif tamsayı değeri, ondalık noktanın ilk basamaktan solunda olduğunu gösterir. *İşaret* parametresi, dönüştürülen sayının işaretini gösteren bir alıcıya işaret lenir. Tamsayı değeri 0 ise, sayı pozitiftir. Aksi takdirde, sayı negatiftir.

**_ecvt** ve **_fcvt** arasındaki *fark, sayım* parametresinin yorumlanmasındadır. **_ecvt,** çıkış dizesinde toplam basamak sayısı *olarak,* **_fcvt** yorumlamaise ondalık noktadan sonraki basamak sayısı olarak *sayılır.*

**_ecvt** ve **_fcvt** dönüştürme için statik olarak ayrılmış tek bir arabellek kullanır. Bu yordamlardan birine yapılan her arama, önceki aramanın sonucunu yok eder.

Bu işlev parametrelerini doğrular. *Dec* veya *sign* **NULL**ise veya *sayı* 0 ise, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, **errno** **EINVAL** olarak ayarlanır ve **NULL** döndürülür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_ecvt**|\<stdlib.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_ecvt.c
// compile with: /W3
// This program uses _ecvt to convert a
// floating-point number to a character string.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   int     decimal,   sign;
   char    *buffer;
   int     precision = 10;
   double  source = 3.1415926535;

   buffer = _ecvt( source, precision, &decimal, &sign ); // C4996
   // Note: _ecvt is deprecated; consider using _ecvt_s instead
   printf( "source: %2.10f   buffer: '%s'  decimal: %d  sign: %d\n",
           source, buffer, decimal, sign );
}
```

```Output
source: 3.1415926535   buffer: '3141592654'  decimal: 1  sign: 0
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_fcvt](fcvt.md)<br/>
[_gcvt](gcvt.md)<br/>
