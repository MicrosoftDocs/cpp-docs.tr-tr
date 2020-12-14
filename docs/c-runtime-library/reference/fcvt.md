---
description: 'Hakkında daha fazla bilgi edinin: _fcvt'
title: _fcvt
ms.date: 4/2/2020
api_name:
- _fcvt
- _o__fcvt
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
- _fcvt
helpviewer_keywords:
- converting floating point, to strings
- _fcvt function
- floating-point functions, converting number to string
- fcvt function
- floating-point functions
ms.assetid: 74584c88-f0dd-4907-8fca-52da5df583f5
ms.openlocfilehash: 4d2439c586ec28526849e956b1302c444cafa3a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235768"
---
# <a name="_fcvt"></a>_fcvt

Kayan noktalı sayıyı dizeye dönüştürür. Bu işlevin daha güvenli bir sürümü kullanılabilir; bkz. [_fcvt_s](fcvt-s.md).

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

*değer*<br/>
Dönüştürülecek sayı.

*biriktirme*<br/>
Ondalık ayırıcıdan sonraki basamak sayısı.

*dec*<br/>
Depolanan ondalık noktası konumu işaretçisi.

*sign*<br/>
Saklı işaret göstergesinin işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

**_fcvt** , sayı dizesi için bir işaretçi döndürür, hatada **null** .

## <a name="remarks"></a>Açıklamalar

**_Fcvt** işlevi, kayan noktalı bir sayıyı null ile sonlandırılmış bir karakter dizesine dönüştürür. *Değer* parametresi dönüştürülecek kayan noktalı sayıdır. **_fcvt** *değer* rakamlarını bir dize olarak depolar ve null karakteri (' \ 0 ') ekler. *Count* parametresi, ondalık ayırıcıdan sonra depolanacak basamak sayısını belirtir. Fazla basamak *sayısı basamak sayısına* yuvarlanır. *Daha az duyarlık basamağı basamak* varsa, dize sıfırlar ile doldurulur.

**_Fcvt** tarafından döndürülen toplam basamak sayısı **_CVTBUFSIZE** aşamaz.

Yalnızca rakamlar dizede depolanır. Ondalık noktanın konumu ve *değer* işareti, çağrıdan sonra *Ara* ve imzala öğesinden elde edilebilir. *Dec* parametresi bir tamsayı değerine işaret eder; Bu tamsayı değeri, dizenin başlangıcına göre ondalık noktanın konumunu verir. Sıfır veya negatif tamsayı değeri, ondalık noktanın ilk basamağın solunda olduğunu gösterir. Parametre *işareti* , *değer* işaretini gösteren bir tamsayıya işaret eder. *Değer* pozitifse, tamsayı 0 olarak ayarlanır ve *değer* negatifse sıfır dışında bir sayı olarak ayarlanır.

**_Ecvt** ve **_fcvt** arasındaki fark *Count* parametresinin yorumlamasıdır. **_ecvt** sayıyı, çıkış dizesindeki toplam basamak sayısı *olarak yorumlarken* , **_fcvt** *sayıyı* ondalık ayırıcıdan sonraki basamak sayısı olarak yorumlar.

**_ecvt** ve **_fcvt** dönüştürme için tek bir statik olarak ayrılmış arabellek kullanır. Bu yordamların birine yapılan her bir çağrı, önceki çağrının sonuçlarını yok eder.

Bu işlev, parametrelerini doğrular. *Ara* veya *işaret* **null** veya *sayı* 0 ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve **null** döndürülür.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fcvt**|\<stdlib.h>|

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

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt](ecvt.md)<br/>
[_gcvt](gcvt.md)<br/>
