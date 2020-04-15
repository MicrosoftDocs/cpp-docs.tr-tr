---
title: _strtoui64, _wcstoui64, _strtoui64_l, _wcstoui64_l
ms.date: 4/2/2020
api_name:
- _strtoui64
- _strtoui64_l
- _wcstoui64
- _wcstoui64_l
- _o__strtoui64
- _o__strtoui64_l
- _o__wcstoui64
- _o__wcstoui64_l
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: f3c5631a34c35ed5f5b74e15dfc4225224215b89
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365473"
---
# <a name="_strtoui64-_wcstoui64-_strtoui64_l-_wcstoui64_l"></a>_strtoui64, _wcstoui64, _strtoui64_l, _wcstoui64_l

Dizeyi imzalanmamış **__int64** değerine dönüştürün.

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
Dönüştürme için null-sonlandırılan dize.

*endptr*<br/>
Tçalışmayı durduran karakter işaretçisi.

*base*<br/>
Kullanılacak sayı tabanı.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

**_strtoui64,** gösterimin bir taşmaya neden olacağı ve bu durumda **_UI64_MAX**döndüreceği durumlar dışında, *dize strSource'da*temsil edilen değeri döndürür. **_strtoui64** dönüşüm yapılamazsa 0 döndürür.

**_UI64_MAX** LIMITS olarak tanımlanır. H.

*strSource* **NULL** ise veya *taban* sıfırsız ve 2'den az veya 36'dan büyükse, **errno** **EINVAL**olarak ayarlanır.

Bunlar ve diğer iade kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bakın.

## <a name="remarks"></a>Açıklamalar

**_strtoui64** işlevi *strSource'u* **imzasız** bir **__int64**dönüştürür. **_wcstoui64** **_strtoui64**geniş karakterli bir versiyonudur; *strSource* bağımsız değişkeni geniş karakterli bir dizedir. Aksi takdirde bu işlevler aynı şekilde çalışır.

Her iki işlev de bir sayının parçası olarak tanıyamayacakları ilk karakterdeki *string strSource'u* okumayı durdurur. Bu sonlandırıcı null karakter olabilir veya ilk sayısal karakter daha büyük veya *baz*eşit olabilir.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoui64**|**_strtoui64**|**_strtoui64**|**_wstrtoui64**|
|**_tcstoui64_l**|**_strtoui64_l**|**_strtoui64_l**|**_wstrtoui64_l**|

Geçerli yerel LC_NUMERIC **kategori** ayarı *strSource*radix karakterinin tanınmasını belirler; daha fazla bilgi için [setlocale'ye](setlocale-wsetlocale.md)bakın. _l sonek olmayan işlevler geçerli yerel durumu kullanır; **_strtoui64_l** ve **_wcstoui64_l,** bunun yerine geçirilen yerelliği kullanmaları dışında **_l** soneki olmadan karşılık gelen işlevlerle aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

*Endptr* **NULL**değilse, saramayı durduran karaktere işaretçi *endptr*tarafından işaret edilen konumda depolanır. Dönüşüm gerçekleştirilemezse (geçerli basamak bulunamadı veya geçersiz bir taban belirtilmişse), *strSource* değeri *endptr*tarafından işaret edilen konumda depolanır.

**_strtoui64** *strSource* aşağıdaki formu bir dize işaret bekliyor:

> [*beyazuzay*] [{**+** **-**&#124; }] [**0** [{ **x** &#124; **X** }]] [ *&#124; harflerin**basamakları* ]

Bir *boşluk,* yoksayılan boşluk ve sekme karakterlerinden oluşabilir. *basamaklar* bir veya daha fazla ondalık basamakvardır. *harfler* 'a' ile 'z' (veya 'A' ile 'Z' harfleri) harfleridir. Bu forma uymayan ilk karakter tazyimi durdurur. *Taban* 2 ile 36 arasındaysa, sayının temeli olarak kullanılır. *Taban* 0 ise, temeli belirlemek için *strSource* tarafından işaret edilen dizeilk karakterleri kullanılır. İlk karakter 0 ise ve ikinci karakter 'x' veya 'X' değilse, dize sekizli bir sonda olarak yorumlanır. İlk karakter '0' ve ikinci karakter 'x' veya 'X' ise, dize hexadecimal tamsayı olarak yorumlanır. İlk karakter '1' ile '9' arasındaysa, dize ondalık tamsayı olarak yorumlanır. 'a' ile 'z' (veya 'A' ile 'Z' arasında) harfleri 10 ile 35 arasında atanır; yalnızca atanan değerleri *tabandan* daha az olan harflere izin verilir. Taban aralığının dışındaki ilk karakter tazyimeyi durdurur. Örneğin, *taban* 0 ise ve taranan ilk karakter '0' ise, bir sekizli sonda varsayar ve '8' veya '9' karakteri taranmasını durdurur.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strtoui64**|\<stdlib.h>|
|**_wcstoui64**|\<stdlib.h> \<veya wchar.h>|
|**_strtoui64_l**|\<stdlib.h>|
|**_wcstoui64_l**|\<stdlib.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[Dizeden Sayısal Değer Fonksiyonlarına](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
