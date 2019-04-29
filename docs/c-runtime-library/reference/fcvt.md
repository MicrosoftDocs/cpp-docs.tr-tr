---
title: _fcvt
ms.date: 04/05/2018
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
helpviewer_keywords:
- converting floating point, to strings
- _fcvt function
- floating-point functions, converting number to string
- fcvt function
- floating-point functions
ms.assetid: 74584c88-f0dd-4907-8fca-52da5df583f5
ms.openlocfilehash: ae9323e3bb629fd61b35a8c844b00bfcc73235bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334846"
---
# <a name="fcvt"></a>_fcvt

Bir kayan noktalı sayı, bir dizeye dönüştürür. Bu işlevin daha güvenli bir sürümü kullanılabilir; bkz: [_fcvt_s](fcvt-s.md).

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
Saklı ondalık noktasının konumunu işaretçisi.

*sign*<br/>
Depolanan oturum gösterge işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

**_fcvt** basamak dizeye bir işaretçi döndürür **NULL** hata.

## <a name="remarks"></a>Açıklamalar

**_Fcvt** işlevi, null ile sonlandırılmış dizeye bir kayan noktalı sayıya dönüştürür. *Değer* parametredir dönüştürülecek kayan noktalı sayı. **_fcvt** rakamı depolar *değer* dize olarak ve null karakteri ('\0') ekler. *Sayısı* parametresi, ondalık ayırıcıdan sonra depolanacak basamak sayısını belirtir. Fazlalık basamaklar yuvarlanır için *sayısı* yerleştirir. Değerinden daha az *sayısı* basamak duyarlılığındadır dize sıfır sıfır.

Tarafından döndürülen basamakların toplam sayısı **_fcvt** değil aşacak **_CVTBUFSIZE**.

Yalnızca rakam, dizede depolanır. Ondalık ve işaretini konumunu *değer* örneğinden alınabilen *Ara* ve çağrısından sonra oturum açın. *Ara* tamsayı değerine; parametresinin işaret bu tamsayı değeri ondalık dizenin başlangıcına göre konumunu sağlar. Sıfır veya negatif tamsayı değeri, Ondalık ayırıcının sol tarafında ilk basamak yer gösterir. Parametre *oturum* işaret işaretini belirten bir tamsayı *değer*. Bir tamsayı ise 0 olarak ayarlanırsa *değer* pozitif ve sıfır olmayan bir sayı if ayarlanır *değer* negatiftir.

Arasındaki fark **_ecvt** ve **_fcvt** öğesinin yorumlamasıdır içinde *sayısı* parametresi. **_ecvt** yorumlar *sayısı* çıkış dizesindeki basamak sayısı olarak ise **_fcvt** yorumlar *sayısı* basamak sayısı ondalık noktası.

**_ecvt** ve **_fcvt** dönüştürme için tek bir statik olarak ayrılan arabelleğin kullanın. Bu yordamların her çağrısına, önceki çağrının sonuçlarını yok eder.

Bu işlev, parametrelerini doğrular. Varsa *Ara* veya *oturum* olduğu **NULL**, veya *sayısı* 0 ise, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [parametresi Doğrulama](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve **NULL** döndürülür.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fcvt**|\<stdlib.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
