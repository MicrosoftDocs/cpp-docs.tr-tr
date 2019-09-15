---
title: _strtoui64, _wcstoui64, _strtoui64_l, _wcstoui64_l
ms.date: 11/04/2016
api_name:
- _strtoui64
- _strtoui64_l
- _wcstoui64
- _wcstoui64_l
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
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: be7d779bac50d332dde879c9d5b070fd2bf7e7e5
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70946436"
---
# <a name="_strtoui64-_wcstoui64-_strtoui64_l-_wcstoui64_l"></a>_strtoui64, _wcstoui64, _strtoui64_l, _wcstoui64_l

Bir dizeyi işaretsiz bir **__int64** değerine dönüştürür.

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
Kullanılacak sayı temeli.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_strtoui64** , *strSource*dizesinde temsil edilen değeri döndürür, bu, temsilin taşmaya neden olacağı, yani **_UI64_MAX**değerini döndürdüğü durumdur. **_strtoui64** , hiçbir dönüştürme gerçekleştirilemiyorsa 0 döndürür.

**_Uı64_max** , limitlerde tanımlanmıştır. Olsun.

*StrSource* **null** ise veya *taban* sıfır değilse ve 2 ' den küçük ya da 36 ' den büyükse **errno** , **EINVAL**olarak ayarlanır.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

## <a name="remarks"></a>Açıklamalar

**_Strtoui64** Işlevi, *strSource* 'u işaretsiz bir **__int64**olarak dönüştürür. **_wcstouı64** , **_strtoui64**öğesinin geniş karakterli bir sürümüdür. *strSource* bağımsız değişkeni geniş karakterli bir dizedir. Aksi takdirde bu işlevler aynı şekilde davranır.

Her iki işlev de bir sayının parçası olarak tanıyamadığı ilk karakterde *strSource* dize okumasını durdurur. Bu, Sonlandırıcı null karakteri olabilir veya *tabandan*büyük veya buna eşit ilk sayısal karakter olabilir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstouı64**|**_strtoui64**|**_strtoui64**|**_wstrtoui64**|
|**_tcstouı64_l**|**_strtoui64_l**|**_strtoui64_l**|**_wstrtoui64_l**|

Geçerli yerel ayarın **LC_NUMERIC** kategori ayarı, *strSource*; içindeki taban karakterinin tanınmasını belirler. daha fazla bilgi için bkz. [setlocale](setlocale-wsetlocale.md). _L soneki olmayan işlevler geçerli yerel ayarı kullanır; **_strtoui64_l** ve **_wcstouı64_l** , yerine geçirilen yerel ayarı kullanmaları dışında, **_l** soneki olmadan ilgili işlevlerle aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

*Endptr* **null**değilse, taramayı durduran karaktere yönelik bir işaretçi, *endptr*tarafından işaret edilen konumda depolanır. Hiçbir dönüştürme gerçekleştirilemiyorsa (geçerli basamak bulunamadı veya geçersiz bir taban belirtilmişse), *strSource* değeri *endptr*tarafından işaret edilen konumda depolanır.

**_strtoui64** , *strSource* 'un aşağıdaki biçimdeki bir dizeyi işaret etmek istiyor:

> [*boşluk*] [{ **+** &#124; &#124; &#124; }] [0 [{x x}]] [basamak harfleri] **-**

Boşluk ve sekme karakterlerinden oluşan bir *boşluk* , yok sayılır. *rakamlar* bir veya daha fazla ondalık basamaklıdır. *harfler* , ' a '-' z ' (veya ' a '-' z ') harflerinden biridir. Bu forma uymayan ilk karakter taramayı durduruyor. *Taban* 2 ile 36 arasındaysa, sayının temeli olarak kullanılır. *Base* 0 Ise, *strSource* tarafından işaret edilen dizenin ilk karakterleri, temeli belirlemede kullanılır. İlk karakter 0 ise ve ikinci karakter ' x ' veya ' X ' değilse, dize sekizlik bir tamsayı olarak yorumlanır. İlk karakter ' 0 ' ise ve ikinci karakter ' x ' veya ' X ' ise, dize onaltılık tamsayı olarak yorumlanır. İlk karakter ' 1 '-' 9 ' arasında ise, dize bir ondalık tamsayı olarak yorumlanır. ' A '-' z ' (veya ' A '-' Z ' arasındaki), 10 ile 35 arasında değerler atanır; yalnızca atanmış değerlerine *tabandan* küçük olan harflerine izin verilir. Taban aralığının dışındaki ilk karakter taramayı sonlandırır. Örneğin, *Base* 0 ise ve taranan ilk karakter ' 0 ' ise, sekizlik bir tamsayı varsayılır ve ' 8 ' veya ' 9 ' karakteri taramayı durduracaktır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strtoui64**|\<Stdlib. h >|
|**_wcstoui64**|\<Stdlib. h > veya \<wchar. h >|
|**_strtoui64_l**|\<Stdlib. h >|
|**_wcstoui64_l**|\<Stdlib. h > veya \<wchar. h >|

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
