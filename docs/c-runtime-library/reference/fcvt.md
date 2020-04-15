---
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: a017ed58b962520793d5b10b088793dbc9b8a83d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347422"
---
# <a name="_fcvt"></a>_fcvt

Kayan nokta sayısını bir dize dönüştürür. Bu işlevin daha güvenli bir sürümü mevcuttur; [bkz. _fcvt_s](fcvt-s.md).

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

*Değer*<br/>
Dönüştürülecek numara.

*Sayısı*<br/>
Ondalık noktadan sonraki basamak sayısı.

*dec*<br/>
Depolanan ondalık nokta konumunu işaretçi.

*Işareti*<br/>
Depolanan işaret göstergesini işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**_fcvt** bir işaretçiyi hata üzerine **NULL** olan basamak lar dizesine döndürür.

## <a name="remarks"></a>Açıklamalar

**_fcvt** işlevi kayan nokta numarasını null-sonlandırılan karakter dizesine dönüştürür. *Değer* parametresi dönüştürülecek kayan nokta sayısıdır. **_fcvt** *değeri* bir dize olarak depolar ve null bir karakter ('\0') ekler. *Sayı* parametresi ondalık noktadan sonra depolanacak basamak sayısını belirtir. Fazla basamaklar yerleri *saymak* için yuvarlanır. *Kesinlik sayısı* basamaklarından daha az varsa, dize sıfırlarla tamamlanır.

**_fcvt** tarafından döndürülen toplam basamak sayısı **_CVTBUFSIZE**geçmeyecek.

Dizede yalnızca basamaklar depolanır. Ondalık noktanın konumu ve *değer* işareti *dec* ve çağrıdan sonra işareti elde edilebilir. *Dec* parametresi bir onsdeğerine işaret ediyor; bu tamsayı değeri, dize başına göre ondalık noktanın konumunu verir. Sıfır veya negatif tamsayı değeri, ondalık noktanın ilk basamaktan solunda olduğunu gösterir. Parametre *işareti,* *değer*işaretini gösteren bir bir yaslamayı işaret ediyor. *Değer* pozitifse tamsayı 0 olarak ayarlanır ve *değer* negatifse sıfır olmayan bir sayıya ayarlanır.

**_ecvt** ve **_fcvt** arasındaki *fark, sayım* parametresinin yorumlanmasındadır. **_ecvt,** çıkış dizesinde toplam basamak sayısı *olarak,* **_fcvt** yorumlamaise ondalık noktadan sonraki basamak sayısı olarak *sayılır.*

**_ecvt** ve **_fcvt** dönüştürme için statik olarak ayrılmış tek bir arabellek kullanır. Bu yordamlardan birine yapılan her arama, önceki aramanın sonuçlarını yok eder.

Bu işlev parametrelerini doğrular. *Dec* veya *sign* **NULL**ise veya *sayı* 0 ise, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, **errno** **EINVAL** olarak ayarlanır ve **NULL** döndürülür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fcvt**|\<stdlib.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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
