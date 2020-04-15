---
title: strtoul, _strtoul_l, wcstoul, _wcstoul_l
ms.date: 4/2/2020
api_name:
- _wcstoul_l
- _strtoul_l
- strtoul
- wcstoul
- _o__strtoul_l
- _o__wcstoul_l
- _o_strtoul
- _o_wcstoul
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
- strtoul
- _tcstoul
- wcstoul
helpviewer_keywords:
- _wcstoul_l function
- _tcstoul function
- _strtoul_l function
- string conversion, to integers
- wcstoul function
- strtoul function
- wcstoul_l function
- strtoul_l function
- tcstoul function
ms.assetid: 38f2afe8-8178-4e0b-8bbe-d5c6ad66e3ab
ms.openlocfilehash: 60ae432fb11c5a29da2c4830c2a85305c6eaa46c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365622"
---
# <a name="strtoul-_strtoul_l-wcstoul-_wcstoul_l"></a>strtoul, _strtoul_l, wcstoul, _wcstoul_l

Dizeleri imzasız uzun tümseci değerine dönüştürün.

## <a name="syntax"></a>Sözdizimi

```C
unsigned long strtoul(
   const char *strSource,
   char **endptr,
   int base
);
unsigned long _strtoul_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
unsigned long wcstoul(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
unsigned long _wcstoul_l(
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

**strtoul** dönüştürülen değeri döndürür, varsa veya taşması **ULONG_MAX.** **strtoul** dönüşüm yapılamazsa 0 döndürür. **wcstoul** benzer şekilde **strtoul**değerleri döndürür. Her iki işlev için de taşma veya taşma oluşursa **errno** **ERANGE** olarak ayarlanır.

Bu ve diğer iade kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bakın.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri giriş *dizestrSource* **imzasız** uzun **dönüştürür.**

**strtoul** bir sayının bir parçası olarak tanıyamaz ilk karakter de dize *strSource* okuma durur. Bu sonlandırıcı null karakter olabilir veya ilk sayısal karakter daha büyük veya *baz*eşit olabilir. Yerel **LC_NUMERIC** LC_NUMERIC kategori ayarı *strSource*radix karakterinin tanınmasını belirler; daha fazla bilgi için [setlocale'ye](setlocale-wsetlocale.md)bakın. **strtoul** ve **wcstoul** geçerli yerel kullanın; **_strtoul_l** ve **_wcstoul_l,** bunun yerine geçirilen yerel liği kullanmaları dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

*Endptr* **NULL**değilse, saramayı durduran karaktere işaretçi *endptr*tarafından işaret edilen konumda depolanır. Dönüşüm gerçekleştirilemezse (geçerli basamak bulunamadı veya geçersiz bir taban belirtilmişse), *strSource* değeri *endptr*tarafından işaret edilen konumda depolanır.

**wcstoul** **strtoul**geniş karakterli bir sürümüdür; *strSource* bağımsız değişkeni geniş karakterli bir dizedir. Aksi takdirde bu işlevler aynı şekilde çalışır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoul**|**strtoul**|**strtoul**|**wcstoul**|
|**_tcstoul_l**|**strtoul_l**|**_strtoul_l**|**_wcstoul_l**|

**strtoul** *strSource* aşağıdaki formu bir dize işaret bekliyor:

> [*beyazuzay*] [{**+** **-**&#124; }] [**0** [{ **x** &#124; **X** }]] [ *&#124; harflerin**basamakları* ]

Bir *boşluk,* yoksayılan boşluk ve sekme karakterlerinden oluşabilir. *basamaklar* bir veya daha fazla ondalık basamakvardır. *harfler* 'a' ile 'z' (veya 'A' ile 'Z' harfleri) harfleridir. Bu forma uymayan ilk karakter tazyimi durdurur. *Taban* 2 ile 36 arasındaysa, sayının temeli olarak kullanılır. *Taban* 0 ise, temeli belirlemek için *strSource* tarafından işaret edilen dizeilk karakterleri kullanılır. İlk karakter 0 ise ve ikinci karakter 'x' veya 'X' değilse, dize sekizli bir sonda olarak yorumlanır. İlk karakter '0' ve ikinci karakter 'x' veya 'X' ise, dize hexadecimal tamsayı olarak yorumlanır. İlk karakter '1' ile '9' arasındaysa, dize ondalık tamsayı olarak yorumlanır. 'a' ile 'z' (veya 'A' ile 'Z' arasında) harfleri 10 ile 35 arasında atanır; yalnızca atanan değerleri *tabandan* daha az olan harflere izin verilir. Taban aralığının dışındaki ilk karakter tazyimeyi durdurur. Örneğin, *taban* 0 ise ve taranan ilk karakter '0' ise, bir sekizli sonda varsayar ve '8' veya '9' karakteri taranmasını durdurur. **strtoul** bir artı**+**( )**-** veya eksi ( ) işareti öneki sağlar; önde gelen eksi işareti, geri dönüş değerinin inkar olduğunu gösterir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtoul**|\<stdlib.h>|
|**wcstoul**|\<stdlib.h> \<veya wchar.h>|
|**_strtoul_l**|\<stdlib.h>|
|**_wcstoul_l**|\<stdlib.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

[Strtod](strtod-strtod-l-wcstod-wcstod-l.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[Dizeden Sayısal Değer Fonksiyonlarına](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtol, wcstol, _strtol_l, _wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
