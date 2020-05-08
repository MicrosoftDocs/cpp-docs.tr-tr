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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 9e02be690b257842c49166e18cf551c540190388
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82915089"
---
# <a name="_ecvt"></a>_ecvt

**Çift** sayıyı dizeye dönüştürür. Bu işlevin daha güvenli bir sürümü kullanılabilir; bkz. [_ecvt_s](ecvt-s.md).

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

*deeri*<br/>
Dönüştürülecek sayı.

*biriktirme*<br/>
Depolanan basamak sayısı.

*dec*<br/>
Saklı ondalık noktası konumu.

*imzalayabilirsiniz*<br/>
Dönüştürülen sayının işareti.

## <a name="return-value"></a>Dönüş Değeri

**_ecvt** , basamak dizesine bir işaretçi döndürür; Bir hata oluştuysa **null** .

## <a name="remarks"></a>Açıklamalar

**_Ecvt** işlevi bir kayan nokta numarasını bir karakter dizesine dönüştürür. *Değer* parametresi dönüştürülecek kayan noktalı sayıdır. Bu işlev, *değerin* *sayı rakamlarını sayı* olarak bir dize olarak depolar ve null karakteri (' \ 0 ') ekler. *Değer* içindeki *basamak sayısı sayıyı aşarsa,* düşük sıra basamağı yuvarlanır. *Count* basamaktan daha azı varsa, dize sıfırlar ile doldurulur.

**_Ecvt** tarafından döndürülen toplam basamak sayısı **_CVTBUFSIZE**aşamaz.

Yalnızca rakamlar dizede depolanır. Ondalık noktanın konumu ve *değer* işareti, çağrıdan sonra *Ara* ve *imzala* öğesinden elde edilebilir. *Ara* parametresi, dizenin başlangıcına göre ondalık noktanın konumunu sağlayan bir tamsayı değerine işaret eder. 0 veya negatif bir tamsayı değeri, ondalık noktanın ilk basamağın solunda olduğunu gösterir. *Sign* parametresi, dönüştürülmüş sayının işaretini gösteren bir tamsayıyı işaret eder. Tamsayı değeri 0 ise, sayı pozitif olur. Aksi takdirde, sayı negatif olur.

**_Ecvt** ve **_fcvt** arasındaki fark *Count* parametresinin yorumlamasıdır. **_ecvt** sayıyı, çıkış dizesindeki toplam basamak sayısı *olarak yorumlarken* , **_fcvt** *sayıyı* ondalık ayırıcıdan sonraki basamak sayısı olarak yorumlar.

**_ecvt** ve **_fcvt** dönüştürme için tek bir statik olarak ayrılmış arabellek kullanır. Bu yordamların birine yapılan her bir çağrı, önceki çağrının sonucunu yok eder.

Bu işlev, parametrelerini doğrular. *Ara* veya *işaret* **null**veya *sayı* 0 ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve **null** döndürülür.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_ecvt**|\<Stdlib. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_fcvt](fcvt.md)<br/>
[_gcvt](gcvt.md)<br/>
