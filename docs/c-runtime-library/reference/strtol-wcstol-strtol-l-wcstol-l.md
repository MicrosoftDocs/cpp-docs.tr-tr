---
title: strtol, wcstol, _strtol_l, _wcstol_l
ms.date: 4/2/2020
api_name:
- strtol
- wcstol
- _strtol_l
- _wcstol_l
- _o__strtol_l
- _o__wcstol_l
- _o_strtol
- _o_wcstol
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
- _wcstol_l
- strtol
- _tcstol
- wcstol
- _strtol_l
- _tcstol_l
helpviewer_keywords:
- wcstol function
- wcstol_l function
- _tcstol function
- string conversion, to integers
- tcstol function
- strtol_l function
- _wcstol_l function
- _strtol_l function
- strtol function
ms.assetid: 1787c96a-f283-4a83-9325-33cfc1c7e240
no-loc:
- strtol
- wcstol
- _strtol_l
- _wcstol_l
- LONG_MAX
- LONG_MIN
- errno
- ERANGE
- EINVAL
- LC_NUMERIC
- _tcstol
- _tcstol_l
- localeconv
- setlocale
- _wsetlocale
- strtod
- _strtod_l
- wcstod
- _wcstod_l
- strtoll
- _strtoll_l
- wcstoll
- _wcstoll_l
- strtoul
- _strtoul_l
- wcstoul
- _wcstoul_l
- atof
- _atof_l
- _wtof
- _wtof_l
ms.openlocfilehash: dbeaf04d34aa20e15de48e99082ed07edb6129ab
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320484"
---
# <a name="strtol-wcstol-_strtol_l-_wcstol_l"></a>strtol, wcstol, _strtol_l, _wcstol_l

Dizeleri **uzun** bir tamsayı değerine dönüştürün.

## <a name="syntax"></a>Sözdizimi

```C
long strtol(
   const char *string,
   char **end_ptr,
   int base
);
long wcstol(
   const wchar_t *string,
   wchar_t **end_ptr,
   int base
);
long _strtol_l(
   const char *string,
   char **end_ptr,
   int base,
   _locale_t locale
);
long _wcstol_l(
   const wchar_t *string,
   wchar_t **end_ptr,
   int base,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*Dize*\
Dönüştürme için null-sonlandırılan dize.

*end_ptr*\
Son yorumlanan karakterden sonra karakteri işaret etmek üzere ayarlanmış bir çıkış parametresi. Göz ardı edilirse, **NULL**.

*Temel*\
Kullanılacak sayı tabanı.

*Yerel ayar*\
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

**strtol**, **wcstol**, **_strtol_l**, ve **_wcstol_l** *dize*temsil edilen değeri döndürün. Dönüşüm mümkün değilse 0 döndürerler. Temsil bir taşma neden olur, onlar **LONG_MAX** veya **LONG_MIN.**

taşma veya taşma oluşursa **errno** **ERANGE** olarak ayarlanır. *Dize* **NULL**ise **EINVAL** olarak ayarlanır. Veya, *taban* sıfır değilse ve 2'den azveya 36'dan büyükse. **ERANGE,** **EINVAL**ve diğer iade kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

**Strtol**, **wcstol**, **_strtol_l**, ve **_wcstol_l** fonksiyonları **uzun**bir *dize* dönüştürmek . Bir sayının parçası olarak tanınmayan ilk karakterde *dize* okumayı durdururlar. Sonlandırıcı-null karakteri veya *tabandan*daha büyük veya tabandan eşit ilk alfanümerik karakter olabilir.

**wcstol** ve **_wcstol_l** **strtol** ve **_strtol_l**geniş karaktersürümlerivardır. Onların *dize* bağımsız değişkeni geniş karakterli bir dizedir. Bu işlevler **strtol** ve **aksi _strtol_l** aynı şekilde çalışır. Yerel LC_NUMERIC **kategori** ayarı *dizedeki*radix karakterinin (kesirli işaretçi veya ondalık nokta) tanınmasını belirler. **Strtol** ve **wcstol** işlevleri geçerli yerel kullanın. **_strtol_l** ve **_wcstol_l** yerine geçirilen yerel kullanın. Daha fazla bilgi için [setlocale] ve [Yerel'e](../../c-runtime-library/locale.md)bakın.

*end_ptr* **NULL**olduğunda, yok sayılır. Aksi takdirde, saramayı durduran karaktere işaretçi *end_ptr*işaret ettiği konumda depolanır. Geçerli basamak bulunmazsa veya geçersiz bir temel belirtilmezse dönüştürme mümkün değildir. *Dize* değeri daha sonra *end_ptr*tarafından işaret edilen konumda depolanır.

**strtol** *dize* aşağıdaki formu bir dize işaret bekliyor:

> [*beyazuzay*] [{**+** **-**&#124; }] [**0** [{ **x** &#124; **X** }]] [*alfanümerik*]

Kare parantezler`[ ]`( ) isteğe bağlı öğeleri çevreler. Kıvırcık ayraçlar ve`{ | }`dikey bir çubuk ( ) tek bir öğe için alternatifleri çevreler. *boşluk,* yoksayAn boşluk ve sekme karakterlerinden oluşabilir. *alfanümerik* ondalık basamaklar veya 'a' ile 'z' (veya 'A' ile 'Z' harfleri) harfleridir. Bu forma uymayan ilk karakter tazyimi durdurur. *Taban* 2 ile 36 arasındaysa, sayının temeli olarak kullanılır. *Taban* 0 ise, *dize* tarafından işaret edilen dize ilk karakterleri tabanı belirlemek için kullanılır. İlk karakter 0 ise ve ikinci karakter 'x' veya 'X' değilse, dize sekizli bir sonda olarak yorumlanır. İlk karakter '0' ve ikinci karakter 'x' veya 'X' ise, dize hexadecimal tamsayı olarak yorumlanır. İlk karakter '1' ile '9' arasındaysa, dize ondalık tamsayı olarak yorumlanır. 'a' ile 'z' (veya 'A' ile 'Z' arasında) harfleri 10 ile 35 arasında atanır. Tama yalnızca değerleri *tabandan*daha az olan harflere izin verir. Taban aralığının dışındaki ilk karakter tazyimeyi durdurur. Örneğin, *dize* "01" ile başlar varsayalım. *Taban* 0 ise, tarayıcı sekizli bir sayacı olduğunu varsayar. '8' veya '9' karakteri tçalışmayı durdurur.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstol**|**strtol**|**strtol**|**wcstol**|
|**_tcstol_l**|**_strtol_l**|**_strtol_l**|**_wcstol_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtol**|\<stdlib.h>|
|**wcstol**|\<stdlib.h> \<veya wchar.h>|
|**_strtol_l**|\<stdlib.h>|
|**_wcstol_l**|\<stdlib.h> \<veya wchar.h>|

**_strtol_l** Ve **_wcstol_l** işlevler Microsoft'a özgüdir, Standart C kitaplığınbir parçası değildir. Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../compatibility.md)

## <a name="example"></a>Örnek

Bkz. için [strtod](strtod-strtod-l-wcstod-wcstod-l.md)örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Veri dönüştürme](../data-conversion.md)\
[Yerel ayar](../locale.md)\
[localeconv](localeconv.md)\
[setlocale, _wsetlocale](setlocale-wsetlocale.md)\
[Dizeden sayısal değer fonksiyonlarına](../string-to-numeric-value-functions.md)\
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)\
[strtoll, _strtoll_l, wcstoll, _wcstoll_l](strtoll-strtoll-l-wcstoll-wcstoll-l.md)\
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)\
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)
