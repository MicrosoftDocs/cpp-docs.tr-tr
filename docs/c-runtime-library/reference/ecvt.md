---
title: _ecvt | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _ecvt function
- numbers, converting
- converting double numbers
- ecvt function
ms.assetid: a916eb05-92d1-4b5c-8563-093acdb49dc8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 63514db5abe0a7cd531590dd419aa4b5931e7729
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
ms.locfileid: "34450969"
---
# <a name="ecvt"></a>_ecvt

Dönüştüren bir **çift** dizeye sayı. Bu işlev daha güvenli bir sürümü kullanılabilir; bkz: [_ecvt_s](ecvt-s.md).

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
Dönüştürülen sayısının işareti.

## <a name="return-value"></a>Dönüş Değeri

**_ecvt** basamak; dize için bir işaretçi döndürür **NULL** durumunda bir hata oluştu.

## <a name="remarks"></a>Açıklamalar

**_Ecvt** işlevi bir karakter dizesi kayan noktalı sayı dönüştürür. *Değeri* dönüştürülecek kayan noktalı sayı parametresidir. Bu işlev kadar saklar *sayısı* rakamı *değeri* dize olarak ve bir null karakter ('\0') ekler. Varsa basamak sayısı *değeri* aşıyor *sayısı*, düşük düzey basamaklı yuvarlanır. Varsa daha az *sayısı* basamak, dize sıfırlarla doldurulan.

Toplam tarafından döndürülen basamak sayısı **_ecvt** değil aşacak **_CVTBUFSIZE**.

Yalnızca rakamlar dizesinde depolanır. Ondalık ayırıcının ve işaretini konumunu *değeri* yükseltebilmeniz *Ara* ve *oturum* çağrısından sonra. *Ara* parametresi dizenin başlangıcını göre Ondalık ayırıcının konumunu vermiş bir tamsayı değeri işaret eder. 0 veya eksi tamsayı değeri, Ondalık ayırıcının ilk rakam solunda kalan gösterir. *Oturum* parametresi işaret dönüştürülen sayının işaretini gösteren bir tamsayı. Tamsayı değer 0 ise, pozitif bir sayıdır. Aksi takdirde, negatif sayısıdır.

Arasındaki farkı **_ecvt** ve **_fcvt** yorumu içinde olduğu *sayısı* parametresi. **_ecvt** yorumlar *sayısı* toplam çıkış dizesinde basamak sayısı olarak ancak **_fcvt** yorumlar *sayısı* basamak sayısı Ondalık ayırıcının.

**_ecvt** ve **_fcvt** dönüştürme için tek bir statik olarak ayrılan arabellek kullanın. Bu yordamlar her çağrısına önceki çağrının sonucu bozar.

Bu işlev parametrelerini doğrular. Varsa *Ara* veya *oturum* olan **NULL**, veya *sayısı* 0'dır, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametresi Doğrulama](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **errno** ayarlanır **EINVAL** ve **NULL** döndürülür.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_ecvt**|\<stdlib.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
