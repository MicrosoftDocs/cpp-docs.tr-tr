---
description: Hakkında daha fazla bilgi edinin:,, strtol wcstol _strtol_l , _wcstol_l
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 8dd175929335533f8ade91450608db7f39bc0cc3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288678"
---
# <a name="no-locstrtol-no-locwcstol-no-loc_strtol_l-no-loc_wcstol_l"></a>strtol, wcstol, _strtol_l, _wcstol_l

Dizeleri bir **`long`** tamsayı değerine dönüştürür.

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

*dizisinde*\
Dönüştürülecek null ile sonlandırılmış dize.

*end_ptr*\
Bir çıktı parametresi, son yorumlanan karakterden sonraki karakteri işaret etmek üzere ayarlanır. **Null** ise yoksayıldı.

*temel*\
Kullanılacak sayı temeli.

*ayarlar*\
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**strtol**, **wcstol** , **_strtol_l** ve **_wcstol_l** *dizesinde* temsil edilen değeri döndürür. Dönüştürme mümkün değilse 0 döndürür. Temsili bir taşmaya neden olduğunda, **LONG_MAX** veya döndürür **LONG_MIN** .

**errno****ERANGE** taşma veya yetersiz gelme gerçekleşirse olarak ayarlanır. **EINVAL** *Dize* **null** ise olarak ayarlanır. Ya da *taban* sıfır değilse veya 2 ' den küçükse ya da 36 ' den büyükse. , Ve diğer dönüş kodları hakkında daha fazla bilgi için **ERANGE** **EINVAL** bkz. [_DOS errno , errno , _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**strtol**,, **wcstol** **_strtol_l** Ve **_wcstol_l** işlevleri *dizeyi* öğesine dönüştürür **`long`** . Bir sayının parçası olarak tanınmayan ilk karakterde *dize* okumayı durdurur. Bu, Sonlandırıcı null karakter veya temelden büyük veya buna eşit olan ilk alfasayısal karakter *olabilir.*

**wcstol** ve, **_wcstol_l** ve öğesinin geniş karakterli sürümleridir **strtol** **_strtol_l** . *Dize* bağımsız değişkeni geniş karakterli bir dizedir. Bu işlevler **strtol** , ve diğer koşullarda aynı şekilde davranır **_strtol_l** . Yerel ayarın **LC_NUMERIC** kategori ayarı, *dizedeki* taban karakterinin (kesirli işaret veya ondalık noktanın) tanınmasını belirler. İşlevleri **strtol** ve **wcstol** geçerli yerel ayarı kullanır. **_strtol_l** ve **_wcstol_l** bunun yerine geçirilen yerel ayarı kullanın. Daha fazla bilgi için bkz setlocale . [] ve [locale](../../c-runtime-library/locale.md).

*End_ptr* **null** olduğunda, yok sayılır. Aksi takdirde, taramayı durduran karaktere yönelik bir işaretçi *end_ptr* tarafından işaret edilen konumda depolanır. Geçerli bir basamak bulunamazsa veya geçersiz bir taban belirtilmişse dönüştürme yapılamaz. Daha sonra *dizenin* değeri *end_ptr* tarafından işaret edilen konumda depolanır.

**strtol***dizenin* aşağıdaki biçimdeki bir dizeye işaret etmek bekler:

> [*boşluk*] [{ **+** &#124; **-** }] [**0** [{ **x** &#124; **x** }]] [*alfasayısal*]

Köşeli parantezler ( `[ ]` ) surround isteğe bağlı öğeleri. Tek bir öğe için küme ayraçları ve dikey çubuk ( `{ | }` ) surround alternatifleri. *boşluk,* yoksayılan boşluk ve sekme karakterlerinden oluşabilir. *alfasayısal* sayılar veya ' a '-' z ' (ya da ' a '-' z ') harfleri ondalık basamaklıdır. Bu forma uymayan ilk karakter taramayı durduruyor. *Taban* 2 ile 36 arasındaysa, sayının temeli olarak kullanılır. *Taban* 0 ise, *dizenin* gösterdiği dizenin başlangıç karakterleri, temeli belirlemede kullanılır. İlk karakter 0 ise ve ikinci karakter ' x ' veya ' X ' değilse, dize sekizlik bir tamsayı olarak yorumlanır. İlk karakter ' 0 ' ise ve ikinci karakter ' x ' veya ' X ' ise, dize onaltılık tamsayı olarak yorumlanır. İlk karakter ' 1 '-' 9 ' arasında ise, dize bir ondalık tamsayı olarak yorumlanır. ' A '-' z ' (veya ' A '-' Z ' arasındaki), 10 ile 35 arası değerlere atanır. Tarama yalnızca değerleri *tabandan* küçük olan harflere izin verir. Taban aralığının dışındaki ilk karakter taramayı sonlandırır. Örneğin, *dizenin* "01" ile başlayacağını varsayın. *Taban* 0 ise, tarayıcı sekizli tamsayı olduğunu varsayar. ' 8 ' veya ' 9 ' karakteri taramayı durduruyor.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstol**|**strtol**|**strtol**|**wcstol**|
|**_tcstol_l**|**_strtol_l**|**_strtol_l**|**_wcstol_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtol**|\<stdlib.h>|
|**wcstol**|\<stdlib.h> veya \<wchar.h>|
|**_strtol_l**|\<stdlib.h>|
|**_wcstol_l**|\<stdlib.h> veya \<wchar.h>|

**_strtol_l** Ve **_wcstol_l** Işlevleri, standart C kitaplığının bir parçası değil, Microsoft 'a özgüdür. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../compatibility.md).

## <a name="example"></a>Örnek

İçin örneğe bakın [strtod](strtod-strtod-l-wcstod-wcstod-l.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Veri dönüştürme](../data-conversion.md)\
[Ayarlar](../locale.md)\
[localeconv](localeconv.md)\
[setlocale, _wsetlocale](setlocale-wsetlocale.md)\
[Sayısal değer işlevlerine dize](../string-to-numeric-value-functions.md)\
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)\
[strtoll, _strtoll_l, wcstoll, _wcstoll_l](strtoll-strtoll-l-wcstoll-wcstoll-l.md)\
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)\
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)
