---
title: strtof, _strtof_l, wcstof, _wcstof_l
ms.date: 4/2/2020
api_name:
- _strtof_l
- wcstof
- strtof
- _wcstof_l
- _o__strtof_l
- _o__wcstof_l
- _o_strtof
- _o_wcstof
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
- _tcstof
- _tcstof_l
- stdlib/strtof
- strtof
- stdlib/_strtof_l
- _strtof_l
- corecrt_wstdlib/wcstof
- wcstof
- corecrt_wstdlib/_wcstof_l
- _wcstof_l
helpviewer_keywords:
- _strtof_l function
- _tcstof function
- _wcstof_l function
- wcstof function
- _tcstof_l function
- strtof function
ms.assetid: 52221b46-876d-4fcc-afb1-97512c17a43b
ms.openlocfilehash: f61aa0edeadd74a254f906dd745e18b059da7f24
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365143"
---
# <a name="strtof-_strtof_l-wcstof-_wcstof_l"></a>strtof, _strtof_l, wcstof, _wcstof_l

Dizeleri tek bir hassas kayan nokta değerine dönüştürür.

## <a name="syntax"></a>Sözdizimi

```C
float strtof(
   const char *strSource,
   char **endptr
);
float _strtof_l(
   const char *strSource,
   char **endptr,
   _locale_t locale
);
float wcstof(
   const wchar_t *strSource,
   wchar_t **endptr
);
float wcstof_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   _locale_t locale
);
```

## <a name="parameters"></a>Parametreler

*strSource*<br/>
Dönüştürme için null-sonlandırılan dize.

*endptr*<br/>
Tazyimi durduran karaktere işaretçi.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**strtof,** temsilin taşmaya neden olacağı durumlar dışında kayan nokta sayısının değerini verir ve bu durumda işlev +/-**HUGE_VALF**döndürür. **HUGE_VALF** işareti, temsil edilemeyen değerin işaretiyle eşleşir. **strtof** dönüşüm gerçekleştirileme yapılamazsa veya bir akış oluşursa 0 döndürür.

**wcstof** **strtof**benzer değerleri döndürür . Her iki işlev için de, aktı veya alt akış oluşursa ve geçersiz parametre işleyicisi çağrıldıysa, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı **gibi, errno** **ERANGE** olarak ayarlanır.

İade kodları hakkında daha fazla bilgi için [bkz: errno, _doserrno, _sys_errlist ve _sys_nerr.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)

## <a name="remarks"></a>Açıklamalar

Her işlev giriş *dizestrkaynağını bir* **float'a**dönüştürür. **Strtof** işlevi *strSource'u* tek bir duyarlık değerine dönüştürür. **strtof** bir sayının bir parçası olarak tanıyamaz ilk karakter de dize *strSource* okuma durur. Bu sonlandırıcı null karakter olabilir. **wcstof** **strtof**bir geniş karakter versiyonudur ; *strSource* bağımsız değişkeni geniş karakterli bir dizedir. Aksi takdirde, bu işlevler aynı şekilde çalışır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstof**|**strtof**|**strtof**|**wcstof**|
|**_tcstof_l**|**_strtof_l**|**_strtof_l**|**_wcstof_l**|

Geçerli **LC_NUMERIC** yerel LC_NUMERIC kategori ayarı *strSource*radix karakterinin tanınmasını belirler; daha fazla bilgi için [setlocale, _wsetlocale](setlocale-wsetlocale.md)bakın. **_l** sonek olmayan işlevler geçerli yerel durumu kullanır; sonek olanlar, bunun yerine geçirilen yerel liği kullanmaları dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

*Endptr* **NULL**değilse, saramayı durduran karaktere işaretçi *endptr*tarafından işaret edilen konumda depolanır. Dönüşüm gerçekleştirilemezse (geçerli basamak bulunamadı veya geçersiz bir taban belirtilmişse), *strSource* değeri *endptr*tarafından işaret edilen konumda depolanır.

**strtof** *strSource* aşağıdaki formu bir dize işaret bekliyor:

[*beyazuzay*] [*işaret*] [*rakamlar*] [__.__ *rakamlar*] [{**e** &#124; **E**} [*işaret*] *basamakları*]

Bir *boşluk,* yoksayılan boşluk ve sekme karakterlerinden oluşabilir; *işareti* ya artı**+**( )**-** ya da eksi ( ); ve *basamaklar* bir veya daha fazla ondalık basamakvardır. Radix karakterinden önce basamak görünmüyorsa, radix karakterinden sonra en az bir basamak görünmelidir. Ondalık basamakları, giriş mektubu **(e** veya **E)** ve isteğe bağlı olarak imzalanmış bir dosdoğrudan oluşan bir üs izlenebilir. Ne üslü bir parça ne de bir radix karakteri görünürse, bir radix karakterinin dizedeki son basamağı takip etmesi varsayılır. Bu forma uymayan ilk karakter tazyimi durdurur.

Bu işlevlerin UCRT sürümleri Fortran stili **(d** veya **D)** üs harflerinin dönüştürülmesini desteklemez. Bu standart dışı uzantı CRT'nin önceki sürümleri tarafından desteklenmiştir ve kodunuz için bir son değişiklik olabilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtof**, **_strtof_l**|C: \<stdlib.h> &lt;C++: cstdlib> veya \<stdlib.h>|
|**wcstof**, **_wcstof_l**|C: \<stdlib.h \<> veya wchar.h &lt;> C++: \<cstdlib>, stdlib.h> veya \<wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_strtof.c
// This program uses strtof to convert a
// string to a single-precision value.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char *string;
   char *stopstring;
   float x;

   string = "3.14159This stopped it";
   x = strtof(string, &stopstring);
   printf("string = %s\n", string);
   printf("   strtof = %f\n", x);
   printf("   Stopped scan at: %s\n\n", stopstring);
}
```

```Output
string = 3.14159This stopped it
   strtof = 3.141590
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
