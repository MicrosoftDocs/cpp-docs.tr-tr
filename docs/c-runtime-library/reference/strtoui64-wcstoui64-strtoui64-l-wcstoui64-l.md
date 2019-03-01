---
title: _strtoui64, _wcstoui64, _strtoui64_l, _wcstoui64_l
ms.date: 11/04/2016
apiname:
- _strtoui64
- _strtoui64_l
- _wcstoui64
- _wcstoui64_l
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _wcstoui64_l
- strtoui64_l
- wcstoui64
- _wcstoui64
- _strtoui64_l
- strtoui64
- _strtoui64
- wcstoui64_l
helpviewer_keywords:
- _strtoui64_l function
- _wcstoui64_l function
- string conversion, to integers
- wcstoui64_l function
- _strtoui64 function
- _wcstoui64 function
- wcstoui64 function
- strtoui64_l function
- strtoui64 function
ms.assetid: 7fcb537e-4554-4ceb-a5b6-bc09244e72ef
ms.openlocfilehash: dec7debff809f8b3d61856f9be77bc590d845c12
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57210763"
---
# <a name="strtoui64-wcstoui64-strtoui64l-wcstoui64l"></a>_strtoui64, _wcstoui64, _strtoui64_l, _wcstoui64_l

Bir dizeyi işaretsiz bir dönüştürme **__int64** değeri.

## <a name="syntax"></a>Sözdizimi

```C
unsigned __int64 _strtoui64(
   const char *strSource,
   char **endptr,
   int base
);
unsigned __int64 _wcstoui64(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
unsigned __int64 _strtoui64_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
unsigned __int64 _wcstoui64(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*strSource*<br/>
Dönüştürülecek null ile sonlandırılmış dize.

*endptr*<br/>
Taramayı durduran karakter işaretçisi.

*base*<br/>
Kullanılacak sayı tabanı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_strtoui64** dizesinde temsil edilen değeri döndürür *strSource*gösterimin bir taşma neden olduğu zaman, o verir durumda dışında **_UI64_MAX**. **_strtoui64** dönüştürme gerçekleştirilemiyorsa 0 döndürür.

**_UI64_MAX** SINIRLARI tanımlanır. H

Varsa *strSource* olduğu **NULL** veya *temel* sıfır dışında olan ve 2'den küçük veya 36'dan büyük ya da daha az **errno** ayarlanır **EINVAL** .

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hakkında daha fazla bilgi için dönüş kodları.

## <a name="remarks"></a>Açıklamalar

**_Strtoui64** işlev dönüştürür *strSource* için bir **işaretsiz** **__int64**. **_wcstoui64** geniş karakterli sürümüdür **_strtoui64**; *strSource* geniş karakterli bir dizedir. Aksi takdirde bu işlevleri aynı şekilde davranır.

Her iki işlev dizesini okumayı durdurur *strSource* bir sayının parçası olarak tanıyamadığı ilk karakterde. Bu sondaki boş karakter olabilir veya daha büyük veya eşit ilk sayısal karakter olabilir *temel*.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoui64**|**_strtoui64**|**_strtoui64**|**_wstrtoui64**|
|**_tcstoui64_l**|**_strtoui64_l**|**_strtoui64_l**|**_wstrtoui64_l**|

Geçerli yerel ayarın **lc_numerıc** kategori ayarı belirler taban karakterin tanınmasını yerel ayarların *strSource*; daha fazla bilgi için bkz: [setlocale](setlocale-wsetlocale.md). The_l soneki olmadan işlevler geçerli yerel ayarı kullanın. **_strtoui64_l** ve **_wcstoui64_l** olmayan ilgili işlevlerle aynıdır **_l** bunun yerine iletilmiş yerel ayarı kullanmaları dışında soneki. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

Varsa *endptr* değil **NULL**, taramayı durduran karaktere bir işaretçi tarafından işaret edilen konumda depolanır *endptr*. Dönüştürme gerçekleştirilemezse (geçerli hiç basamak bulunamamış veya geçersiz bir taban belirtilmişse), değeri *strSource* tarafından işaret edilen konumda depolanır *endptr*.

**_strtoui64** bekliyor *strSource* aşağıdaki biçimde bir dizeye işaret edecek şekilde:

> [*boşluk*] [{**+** &#124; **-**}] [**0** [{ **x** &#124; **X** }]] [*basamak* &#124; *harf*]  

A *boşluk* yoksayılan boşluk ve sekme karakterlerinden oluşabilir. *basamak* bir veya daha fazla ondalık basamaktır. *harf* 'a' ila 'z' (veya 'A'-'Z') bir veya daha fazla harf olan. Bu forma uymayan ilk karakter taramayı durdurur. Varsa *temel* 2 ile 36 arasındaysa sayının tabanı kullanılır olduğu. Varsa *temel* tarafından işaret edilen dizenin ilk karakterleri 0'dır *strSource* tabanı belirlemek için kullanılır. İlk karakter 0 ise ve ikinci karakter 'x' veya 'X' değilse, dize sekizlik bir tamsayı olarak yorumlanır. İlk karakter '0' ise ve ikinci karakter 'x' veya 'X' dize onaltılık bir tamsayı olarak yorumlanır. İlk karakter ' 1'-' 9' ise, dize ondalık bir tamsayı olarak yorumlanır. Harfler 'bir'-'z' (ya da 'A'-'Z'), 10-35 arasında değerler atanır; yalnızca atanan değerleri olan harf küçüktür *temel* izin verilir. Tabanın aralığının dışındaki ilk karakter taramayı durdurur. Örneğin, varsa *temel* 0 ise ve taranan ilk karakter '0' ise, sekizlik bir tamsayı olduğu varsayılır ve bir '8' veya '9' karakteri taramayı durduracaktır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strtoui64**|\<stdlib.h >|
|**_wcstoui64**|\<stdlib.h > veya \<wchar.h >|
|**_strtoui64_l**|\<stdlib.h >|
|**_wcstoui64_l**|\<stdlib.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_strtoui64.c
#include <stdio.h>

unsigned __int64 atoui64(const char *szUnsignedInt) {
   return _strtoui64(szUnsignedInt, NULL, 10);
}

int main() {
   unsigned __int64 u = atoui64("18446744073709551615");
   printf( "u = %I64u\n", u );
}
```

```Output
u = 18446744073709551615
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[Sayısal Değer İşlevleri Dizesi](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
