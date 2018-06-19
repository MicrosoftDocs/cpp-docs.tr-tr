---
title: _fcvt | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _fcvt
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
- _fcvt
dev_langs:
- C++
helpviewer_keywords:
- converting floating point, to strings
- _fcvt function
- floating-point functions, converting number to string
- fcvt function
- floating-point functions
ms.assetid: 74584c88-f0dd-4907-8fca-52da5df583f5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 272b8e4ba5e57d71b4b785bceef7e5ea2f0ac7c2
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
ms.locfileid: "34450426"
---
# <a name="fcvt"></a>_fcvt

Kayan noktalı sayı bir dizeye dönüştürür. Bu işlev daha güvenli bir sürümü kullanılabilir; bkz: [_fcvt_s](fcvt-s.md).

## <a name="syntax"></a>Sözdizimi

```C
char *_fcvt(
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
Ondalık basamak sayısı.

*Ara*<br/>
Saklanan Ondalık ayırıcının konum işaretçi.

*sign*<br/>
Depolanan oturum göstergesi işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**_fcvt** basamak, dize için bir işaretçi döndürür **NULL** hata.

## <a name="remarks"></a>Açıklamalar

**_Fcvt** işlevi kayan noktalı sayı null olarak sonlandırılan bir karakter dizeye dönüştürür. *Değeri* dönüştürülecek kayan noktalı sayı parametresidir. **_fcvt** rakamı depolar *değeri* dize olarak ve bir null karakter ('\0') ekler. *Sayısı* parametresi, ondalık ayırıcıdan sonra depolanması için basamak sayısını belirtir. Aşırı basamak yuvarlanır için *sayısı* yerleştirir. Varsa daha az *sayısı* basamaklı duyarlık, dize sıfırlarla doldurulan.

Toplam tarafından döndürülen basamak sayısı **_fcvt** değil aşacak **_CVTBUFSIZE**.

Yalnızca rakamlar dizesinde depolanır. Ondalık ayırıcının ve işaretini konumunu *değeri* yükseltebilmeniz *Ara* ve çağrısından sonra oturum açın. *Ara* parametresi tamsayı değerine; işaret bu tamsayı değeri ondalık dizenin başlangıcını göre konumunu sağlar. Sıfır veya negatif tamsayı değeri belirten Ondalık ayırıcının sol tarafında ilk rakam arasındadır. Parametre *oturum* işaret işaretini gösteren tamsayı *değeri*. Tamsayı varsa 0 olarak ayarlanırsa *değeri* pozitif ve sıfır olmayan bir sayı ise ayarlanır *değeri* negatiftir.

Arasındaki farkı **_ecvt** ve **_fcvt** yorumu içinde olduğu *sayısı* parametresi. **_ecvt** yorumlar *sayısı* toplam çıkış dizesinde basamak sayısı olarak ancak **_fcvt** yorumlar *sayısı* basamak sayısı Ondalık ayırıcının.

**_ecvt** ve **_fcvt** dönüştürme için tek bir statik olarak ayrılan arabellek kullanın. Bu yordamlar her çağrısına önceki çağrısının sonuçlarını bozar.

Bu işlev parametrelerini doğrular. Varsa *Ara* veya *oturum* olan **NULL**, veya *sayısı* 0'dır, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametresi Doğrulama](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **errno** ayarlanır **EINVAL** ve **NULL** döndürülür.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fcvt**|\<stdlib.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_fcvt.c
// compile with: /W3
// This program converts the constant
// 3.1415926535 to a string and sets the pointer
// buffer to point to that string.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   int  decimal, sign;
   char *buffer;
   double source = 3.1415926535;

   buffer = _fcvt( source, 7, &decimal, &sign ); // C4996
   // Note: _fcvt is deprecated; consider using _fcvt_s instead
   printf( "source: %2.10f   buffer: '%s'   decimal: %d   sign: %d\n",
            source, buffer, decimal, sign );
}
```

```Output
source: 3.1415926535   buffer: '31415927'   decimal: 1   sign: 0
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt](ecvt.md)<br/>
[_gcvt](gcvt.md)<br/>
