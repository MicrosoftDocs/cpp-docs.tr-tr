---
title: strtol, wcstol, _strtol_l, _wcstol_l
ms.date: 01/14/2020
api_name:
- strtol
- wcstol
- _strtol_l
- _wcstol_l
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
ms.openlocfilehash: 83054e1b31b56fda96bdea198ab34d65d633f335
ms.sourcegitcommit: e93f3e6a110fe38bc642055bdf4785e620d4220f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76123935"
---
# <a name="opno-locstrtol-opno-locwcstol-opno-loc_strtol_l-opno-loc_wcstol_l"></a>strtol, wcstol, _strtol_l, _wcstol_l

Dizeleri **uzun** tamsayı değerine dönüştürür.

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

*dize*\
Dönüştürülecek null ile sonlandırılmış dize.

*end_ptr*\
Bir çıktı parametresi, son yorumlanan karakterden sonraki karakteri işaret etmek üzere ayarlanır. **Null**ise yoksayıldı.

*temel*\
Kullanılacak sayı temeli.

*yerel ayar*\
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**strtol** , **wcstol** , **_strtol_l** ve **_wcstol_l** *dizesinde*temsil edilen değeri döndürür. Dönüştürme mümkün değilse 0 döndürür. Gösterim bir taşmaya neden olduğunda **LONG_MAX** veya **LONG_MIN** döndürür.

**errno** taşma veya yetersiz gelme gerçekleşirse **ERANGE** olarak ayarlanır. *Dize* **null**ise **EINVAL** olarak ayarlanır. Ya da *taban* sıfır değilse veya 2 ' den küçükse ya da 36 ' den büyükse. **ERANGE** , **EINVAL** ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**strtol** , **wcstol** , **_strtol_l** ve **_wcstol_l** işlevleri *dizeyi* **Long**olarak dönüştürür. Bir sayının parçası olarak tanınmayan ilk karakterde *dize* okumayı durdurur. Bu, Sonlandırıcı null karakter veya temelden büyük veya buna eşit olan ilk alfasayısal karakter *olabilir.*

**wcstol** ve **_wcstol_l** , **strtol** ve **_strtol_l** 'ın geniş karakterli sürümleridir. *Dize* bağımsız değişkeni geniş karakterli bir dizedir. Bu işlevler **strtol** ile aynı şekilde davranır ve aksi takdirde **_strtol_l** . Yerel ayarın **LC_NUMERIC** kategori ayarı, *dizedeki*taban karakterinin (kesirli işaret veya ondalık noktanın) tanınmasını belirler. **strtol** ve **wcstol** işlevleri geçerli yerel ayarı kullanır. **_strtol_l** ve **_wcstol_l** bunun yerine geçirilen yerel ayarı kullanır. Daha fazla bilgi için bkz. [setlocale] ve [yerel ayar](../../c-runtime-library/locale.md).

*End_ptr* **null**olduğunda, yok sayılır. Aksi takdirde, taramayı durduran karaktere yönelik bir işaretçi *end_ptr*tarafından işaret edilen konumda depolanır. Geçerli bir basamak bulunamazsa veya geçersiz bir taban belirtilmişse dönüştürme yapılamaz. Daha sonra *dizenin* değeri *end_ptr*tarafından işaret edilen konumda depolanır.

**strtol** , *dizenin* aşağıdaki biçimdeki bir dizeye işaret etmek istiyor:

> [*boşluk*] [{ **+** &#124; **-** }] [**0** [{ **x** &#124; **x** }]] [*alfasayısal*]

Köşeli ayraçlar (`[ ]`), isteğe bağlı öğeleri çevreleyin. Tek bir öğe için küme ayraçları ve dikey çubuk (`{ | }`) surround alternatifleri. *boşluk,* yoksayılan boşluk ve sekme karakterlerinden oluşabilir. *alfasayısal* sayılar veya ' a '-' z ' (ya da ' a '-' z ') harfleri ondalık basamaklıdır. Bu forma uymayan ilk karakter taramayı durduruyor. *Taban* 2 ile 36 arasındaysa, sayının temeli olarak kullanılır. *Taban* 0 ise, *dizenin* gösterdiği dizenin başlangıç karakterleri, temeli belirlemede kullanılır. İlk karakter 0 ise ve ikinci karakter ' x ' veya ' X ' değilse, dize sekizlik bir tamsayı olarak yorumlanır. İlk karakter ' 0 ' ise ve ikinci karakter ' x ' veya ' X ' ise, dize onaltılık tamsayı olarak yorumlanır. İlk karakter ' 1 '-' 9 ' arasında ise, dize bir ondalık tamsayı olarak yorumlanır. ' A '-' z ' (veya ' A '-' Z ' arasındaki), 10 ile 35 arası değerlere atanır. Tarama yalnızca değerleri *tabandan*küçük olan harflere izin verir. Taban aralığının dışındaki ilk karakter taramayı sonlandırır. Örneğin, *dizenin* "01" ile başlayacağını varsayın. *Taban* 0 ise, tarayıcı sekizli tamsayı olduğunu varsayar. ' 8 ' veya ' 9 ' karakteri taramayı durduruyor.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstol**|**strtol**|**strtol**|**wcstol**|
|**_tcstol_l**|**_strtol_l**|**_strtol_l**|**_wcstol_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtol**|\<Stdlib. h >|
|**wcstol**|\<Stdlib. h > veya \<wchar. h >|
|**_strtol_l**|\<Stdlib. h >|
|**_wcstol_l**|\<Stdlib. h > veya \<wchar. h >|

**_strtol_l** ve **_wcstol_l** işlevleri, standart C kitaplığının bir parçası değil, Microsoft 'a özgüdür. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../compatibility.md).

## <a name="example"></a>Örnek

[strtod](strtod-strtod-l-wcstod-wcstod-l.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Veri dönüştürme](../data-conversion.md)\
[Yerel ayar](../locale.md)\
[localeconv](localeconv.md)\
[setlocale, _wsetlocale](setlocale-wsetlocale.md)\
[Sayısal değer işlevlerine yönelik dize](../string-to-numeric-value-functions.md)\
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)\
[strtoll, _strtoll_l, wcstoll, _wcstoll_l](strtoll-strtoll-l-wcstoll-wcstoll-l.md)\
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)\
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)
