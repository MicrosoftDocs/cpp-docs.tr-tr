---
title: strtold, _strtold_l, wcstold, _wcstold_l
ms.date: 4/2/2020
api_name:
- wcstold
- strtold
- _strtold_l
- _wcstold_l
- _o__strtold_l
- _o__wcstold_l
- _o_strtold
- _o_wcstold
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
- _tcstold_l
- _wcstold_l
- _tcstold
- strtold
- _strtold_l
- wcstold
ms.assetid: 928c0c9a-bc49-445b-8822-100eb5954115
ms.openlocfilehash: 9acc98296651f549ceffb1e1deab350a71747ea5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365358"
---
# <a name="strtold-_strtold_l-wcstold-_wcstold_l"></a>strtold, _strtold_l, wcstold, _wcstold_l

Dizeleri uzun çift duyarlıklı kayan nokta değerine dönüştürür.

## <a name="syntax"></a>Sözdizimi

```C
long double strtold(
   const char *strSource,
   char **endptr
);
long double _strtold_l(
   const char *strSource,
   char **endptr,
   _locale_t locale
);
long double wcstold(
   const wchar_t *strSource,
   wchar_t **endptr
);
long double wcstold_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*strSource*<br/>
Dönüştürme için null-sonlandırılan dize.

*endptr*<br/>
Tazyimi durduran karaktere işaretçi.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**strtold,** kayan nokta sayısının değerini **uzun** bir **çift**olarak döndürür, ancak gösterim bir taşmaya neden olur-bu durumda işlev +/-**HUGE_VALL**döndürür. **HUGE_VALL** işareti, temsil edilemeyen değerin işaretiyle eşleşir. dönüşüm gerçekleştirileme yapılamazsa veya bir akış oluşursa **strtold** 0 döndürür.

**wcstold** benzer strtold değerleri **döndürür.** Her iki işlev için de, aktı veya alt akış oluşursa ve geçersiz parametre işleyicisi çağrıldıysa, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı **gibi, errno** **ERANGE** olarak ayarlanır.

İade kodları hakkında daha fazla bilgi için [bkz: errno, _doserrno, _sys_errlist ve _sys_nerr.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)

## <a name="remarks"></a>Açıklamalar

Her işlev giriş *dizestrSource* **uzun** bir **çift**dönüştürür. **Strtold** işlevi, bir sayının parçası olarak tanıyamadığı ilk karakterde dize *strSource'u* okumayı durdurur. Bu sonlandırıcı null karakter olabilir. **Strtold** geniş karakterli versiyonu **wcstold**olduğunu; *strSource* bağımsız değişkeni geniş karakterli bir dizedir. Aksi takdirde, bu işlevler aynı şekilde çalışır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstold**|**strtold**|**strtold**|**wcstold**|
|**_tcstold_l**|**_strtold_l**|**_strtold_l**|**_wcstold_l**|

Geçerli **LC_NUMERIC** yerel LC_NUMERIC kategori ayarı *strSource*radix karakterinin tanınmasını belirler. Daha fazla bilgi için [setlocale, _wsetlocale](setlocale-wsetlocale.md)bakın. **_l** sonek olmayan işlevler geçerli yerel durumu kullanır; **_strtold_l** ve **_wcstold_l,** bunun yerine geçirilen yerel liği kullanmaları dışında **_strtold** ve **_wcstold** aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

*Endptr* **NULL**değilse, saramayı durduran karaktere işaretçi *endptr*tarafından işaret edilen konumda depolanır. Dönüşüm gerçekleştirilemezse (geçerli basamak bulunamadı veya geçersiz bir taban belirtilmişse), *strSource* değeri *endptr*tarafından işaret edilen konumda depolanır.

**strtold** *strSource* aşağıdaki formu bir dize işaret bekliyor:

[*beyazuzay*] [*işaret*] [*rakamlar*] [. *rakamlar*] [ {**d** &#124; **D** &#124; **e** &#124; **E**}[*işaret*]*rakamları*]

Bir *boşluk,* yoksayılan boşluk ve sekme karakterlerinden oluşabilir; *işareti* ya artı**+**( )**-** ya da eksi ( ); ve *basamaklar* bir veya daha fazla ondalık basamakvardır. Radix karakterinden önce basamak görünmüyorsa, radix karakterinden sonra en az bir basamak görünmelidir. Ondalık basamaklar, giriş harfi **(d**, **D**, **e**, **veya E**) ve isteğe bağlı olarak imzalanmış bir dosyondan oluşan bir üs tarafından izlenebilir. Ne üslü bir parça ne de bir radix karakteri görünürse, bir radix karakterinin dizedeki son basamağı takip etmesi varsayılır. Bu forma uymayan ilk karakter tazyimi durdurur.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtold**, **_strtold_l**|\<stdlib.h>|
|**wcstold**, **_wcstold_l**|\<stdlib.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_strtold.c
// Build with: cl /W4 /Tc crt_strtold.c
// This program uses strtold to convert a
// string to a long double-precision value.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char *string;
   char *stopstring;
   long double x;

   string = "3.1415926535898This stopped it";
   x = strtold(string, &stopstring);
   printf("string = %s\n", string);
   printf("   strtold = %.13Lf\n", x);
   printf("   Stopped scan at: %s\n\n", stopstring);
}
```

```Output
string = 3.1415926535898This stopped it
   strtold = 3.1415926535898
   Stopped scan at: This stopped it
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Dizeden Sayısal Değer Fonksiyonlarına](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[localeconv](localeconv.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
[_free_locale](free-locale.md)<br/>
