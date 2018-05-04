---
title: _strtoui64, _wcstoui64, _strtoui64_l, _wcstoui64_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ab70c1d74c0db837ba3d8e453988ca441f6fc06d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="strtoui64-wcstoui64-strtoui64l-wcstoui64l"></a>_strtoui64, _wcstoui64, _strtoui64_l, _wcstoui64_l

Bir dizeyi bir imzasız dönüştürme **__int64** değeri.

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
Tarama durdurur karakter işaretçi.

*base*<br/>
Kullanılacak sayı temel.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_strtoui64** dizesinde gösterilen değerini verir *strSource*, temsili taşma neden olacağından, içinde bu döndürür durumda dışında **_UI64_MAX**. **_strtoui64** dönüştürme gerçekleştirilebiliyorsa 0 döndürür.

**_UI64_MAX** SINIRLARI tanımlanır. H.

Varsa *strSource* olan **NULL** veya *temel* sıfır dışında olan ve 2 veya 36, büyüktür ya da daha az **errno** ayarlanır **EINVAL** .

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hakkında daha fazla bilgi için dönüş kodları.

## <a name="remarks"></a>Açıklamalar

**_Strtoui64** işlev dönüştürür *strSource* için bir **imzasız** **__int64**. **_wcstoui64** bir joker karakter sürümü **_strtoui64**; kendi *strSource* bağımsız değişkeni olan bir joker karakter dizesi. Aksi takdirde bu işlevler aynı şekilde davranır.

Her iki işlevleri Durdur dize okuma *strSource* ilk karakterinde bunlar bir sayı bir parçası olarak tanımak olamaz. Bu sonlandırma null karakter olabilir ya da sıfırdan büyük veya eşit ilk sayısal karakter olabilir *temel*.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoui64**|**_strtoui64**|**_strtoui64**|**_wstrtoui64**|
|**_tcstoui64_l**|**_strtoui64_l**|**_strtoui64_l**|**_wstrtoui64_l**|

Geçerli yerel **lc_numerıc** kategori ayarı belirler tanıma taban karakterinin *strSource*; daha fazla bilgi için bkz: [setlocale](setlocale-wsetlocale.md). Geçerli yerel _l soneki olmayan işlevler kullanın; **_strtoui64_l** ve **_wcstoui64_l** ilgili işlevleri aynıdır **_l** yerine geçirilen yerel ayar kullanmasını dışında soneki. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

Varsa *endptr* değil **NULL**, tarama durduruldu karakteri gösteren bir işaretçi işaret konumunda depolanan *endptr*. Hiçbir dönüştürme gerçekleştirilebiliyorsa (hiç geçerli basamak bulunamadı veya geçersiz taban belirtildi), değeri *strSource* gösterdiği konumunda depolanan *endptr*.

**_strtoui64** bekliyor *strSource* aşağıdaki biçimde bir dizeye işaret etmek için:

> [*boşluk*] [{**+** &#124; **-**}] [**0** [{ **x** &#124; **X** }]] [*basamak* &#124; *harf*]  

A *boşluk* yoksayılan boşluk ve sekme karakterlerden oluşabilir. *basamak* bir veya daha fazla ondalık basamakların. *harf* 'a' ile 'z' (veya 'A'-'Z') bir veya daha fazla harf şunlardır. Bu form sığmayan ilk karakter tarama durdurur. Varsa *temel* sayısı temel olarak kullanılan sonra 2 ile 36, arasındadır. Varsa *temel* gösterdiği dizenin ilk karakter 0'dır ve *strSource* temel belirlemek için kullanılır. İlk karakter 0 ve ikinci karakter 'x' veya 'X' değil, dize sekizlik tamsayı olarak yorumlanır. İlk karakter '0' dir ve ikinci karakteri 'x' veya 'X', dize onaltılık bir tamsayı olarak yorumlanır. İlk karakteri ' 1' üzerinden ' 9'. dize ondalık bir tamsayı olarak yorumlanır. 'A' ile 'z' harf (veya 'A'-'Z') 35 10 değerler atanır; yalnızca atanan değerleri olan harf değerinden *temel* izin verilir. İlk karakter taban izin verilen aralığın dışında tarama durdurur. Örneğin, varsa *temel* 0'dır ve taranan ilk karakter '0', tamsayı sekizli kabul edilir ve bir '8' veya '9' karakter tarama durdurur.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strtoui64**|\<stdlib.h >|
|**_wcstoui64**|\<stdlib.h > veya \<wchar.h >|
|**_strtoui64_l**|\<stdlib.h >|
|**_wcstoui64_l**|\<stdlib.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
