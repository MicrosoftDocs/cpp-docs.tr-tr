---
title: _ecvt
ms.date: 04/05/2018
apiname:
- _ecvt
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
- _ecvt
helpviewer_keywords:
- _ecvt function
- numbers, converting
- converting double numbers
- ecvt function
ms.assetid: a916eb05-92d1-4b5c-8563-093acdb49dc8
ms.openlocfilehash: 36c9cb2e8cd9eb4dd67bb91e9e4dbd36d8d1fc8e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605738"
---
# <a name="ecvt"></a>_ecvt

Dönüştürür bir **çift** bir dizeye sayı. Bu işlevin daha güvenli bir sürümü kullanılabilir; bkz: [_ecvt_s](ecvt-s.md).

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

*value*<br/>
Dönüştürülecek sayı.

*Sayısı*<br/>
Depolanan basamak sayısı.

*Ara*<br/>
Ondalık noktasının konumunu depolanır.

*sign*<br/>
Dönüştürülen sayının işaretini.

## <a name="return-value"></a>Dönüş Değeri

**_ecvt** basamaktır; dizeye bir işaretçi döndürür **NULL** varsa bir hata oluştu.

## <a name="remarks"></a>Açıklamalar

**_Ecvt** işlevi, bir karakter dizesindeki bir kayan noktalı sayıya dönüştürür. *Değer* parametredir dönüştürülecek kayan noktalı sayı. Bu işlev kadar depolar *sayısı* rakamı *değer* dize olarak ve null karakteri ('\0') ekler. Varsa basamak sayısı *değer* aşıyor *sayısı*, düşük düzey basamak yuvarlanır. Değerinden daha az *sayısı* basamak, dize sıfır sıfır.

Tarafından döndürülen basamakların toplam sayısı **_ecvt** değil aşacak **_CVTBUFSIZE**.

Yalnızca rakam, dizede depolanır. Ondalık ve işaretini konumunu *değer* örneğinden alınabilen *Ara* ve *oturum* çağrısından sonra. *Ara* parametresi dizenin başlangıcına göre ondalık noktasının konumunu vermiş bir tamsayı değeri işaret eder. 0 veya negatif bir tamsayı değeri, Ondalık ayırıcının sol tarafında ilk basamak yer gösterir. *Oturum* parametresi işaret dönüştürülmüş sayının işaretini belirten bir tamsayı. Tamsayı değeri 0 ise, pozitif bir sayıdır. Aksi takdirde, negatif sayıdır.

Arasındaki fark **_ecvt** ve **_fcvt** öğesinin yorumlamasıdır içinde *sayısı* parametresi. **_ecvt** yorumlar *sayısı* çıkış dizesindeki basamak sayısı olarak ise **_fcvt** yorumlar *sayısı* basamak sayısı ondalık noktası.

**_ecvt** ve **_fcvt** dönüştürme için tek bir statik olarak ayrılan arabelleğin kullanın. Bu yordamların her çağrısına, önceki çağrının sonucu yok eder.

Bu işlev, parametrelerini doğrular. Varsa *Ara* veya *oturum* olduğu **NULL**, veya *sayısı* 0 ise, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [parametresi Doğrulama](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve **NULL** döndürülür.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_ecvt**|\<stdlib.h >|

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

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_fcvt](fcvt.md)<br/>
[_gcvt](gcvt.md)<br/>
