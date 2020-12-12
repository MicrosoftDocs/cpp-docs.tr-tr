---
description: 'Daha fazla bilgi edinin: strftime, wcsftime, _strftime_l _wcsftime_l'
title: strftime, wcsftime, _strftime_l, _wcsftime_l
ms.date: 4/2/2020
api_name:
- strftime
- _wcsftime_l
- _strftime_l
- wcsftime
- _o__strftime_l
- _o__wcsftime_l
- _o_strftime
- _o_wcsftime
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
- api-ms-win-crt-time-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tcsftime
- strftime
- wcsftime
- _strftime_l
- _wcsftime_l
helpviewer_keywords:
- _strftime_l function
- strftime function
- tcsftime function
- _wcsftime_l function
- wcsftime function
- _tcsftime function
- time strings
ms.assetid: 6330ff20-4729-4c4a-82af-932915d893ea
ms.openlocfilehash: f6297af6ad7c0f6f9a0280cc47ea7a0caa6440af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97299572"
---
# <a name="strftime-wcsftime-_strftime_l-_wcsftime_l"></a>strftime, wcsftime, _strftime_l, _wcsftime_l

Bir zaman dizesini biçimlendirin.

## <a name="syntax"></a>Sözdizimi

```C
size_t strftime(
   char *strDest,
   size_t maxsize,
   const char *format,
   const struct tm *timeptr
);
size_t _strftime_l(
   char *strDest,
   size_t maxsize,
   const char *format,
   const struct tm *timeptr,
   _locale_t locale
);
size_t wcsftime(
   wchar_t *strDest,
   size_t maxsize,
   const wchar_t *format,
   const struct tm *timeptr
);
size_t _wcsftime_l(
   wchar_t *strDest,
   size_t maxsize,
   const wchar_t *format,
   const struct tm *timeptr,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*strDest*<br/>
Çıkış dizesi.

*MaxSize*<br/>
*StrDest* arabelleğinin karakter cinsinden ( **`char`** veya) ölçülen boyutu **`wchar_t`** .

*formatını*<br/>
Biçim denetimi dizesi.

*timeptr*<br/>
**TM** veri yapısı.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**strftime** , *strDest* öğesine yerleştirilmiş karakter sayısını, **wcsftime** ise karşılık gelen geniş karakter sayısını döndürür.

Sonlandırıcı null değeri de dahil olmak üzere toplam karakter sayısı *MAXSIZE*'dan büyükse, hem **strftime** hem de **wcsftime** 0 döndürür ve *strDest* içeriği belirsiz olur.

*StrDest* içindeki karakter sayısı *, biçimlendirme kodları aracılığıyla biçimlendirmeye* eklenebilir olan karakterlerin yanı sıra *biçimdeki* sabit karakter sayısına eşittir. Bir dizenin Sonlandırıcı null değeri, dönüş değerinde sayılmaz.

## <a name="remarks"></a>Açıklamalar

**Strftime** ve **wcsftime** işlevleri, sağlanan *Biçim* bağımsız değişkenine göre *timeptr* Içindeki **TM** Time değerini biçimlendirir ve sonucu buffer *strDest* içinde depolar. En çok, *MaxSize* karakterleri dizeye yerleştirilir. *Timeptr* yapısındaki alanların açıklaması için bkz. [asctime](asctime-wasctime.md). **wcsftime** , **strftime**'ın geniş karakterli eşdeğeridir. dize işaretçisi bağımsız değişkeni, bir geniş karakter dizesine işaret eder. Bu işlevler, aynı şekilde davranır.

Bu işlev, parametrelerini doğrular. *StrDest*, *Format* veya *timeptr* bir null işaretçisiyse veya *timeptr* tarafından ele alınan **TM** veri yapısı geçersizse (örneğin, saat veya tarih için Aralık dışında değerler içeriyorsa) veya *Biçim* dizesi geçersiz bir biçimlendirme kodu içeriyorsa, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, işlev 0 döndürür ve **errno** öğesini **EINVAL** olarak ayarlar.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsftime**|**strftime**|**strftime**|**wcsftime**|

*Biçim* bağımsız değişkeni bir veya daha fazla kodlardan oluşur; **printf** içinde olduğu gibi, biçimlendirme kodlarının öncesinde bir yüzde işareti () bulunur **%** . İle başlamayan karakterler **%** , *strDest* öğesine değiştirilmeden kopyalanır. Geçerli yerel ayarın **LC_TIME** kategorisi, **strftime** çıkış biçimlendirmesini etkiler. ( **LC_TIME** hakkında daha fazla bilgi için bkz. [setlocale](setlocale-wsetlocale.md).) **Strftime** ve **wcsftime** işlevleri şu anda ayarlanmış yerel ayarı kullanır. Bu işlevlerin **_strftime_l** ve **_wcsftime_l** sürümleri, yerel ayarı bir parametre olarak ele aldıkları ve şu anda ayarlanmış yerel ayar yerine bunu kullanması dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

**Strftime** işlevleri şu biçimlendirme kodlarını destekler:

|Kod|Değiştirme dizesi|
|-|-|
|**% a**|Yerel ayarda kısaltılmış iş günü adı|
|**% A**|Yerel ayarda tam hafta içi ad|
|**% b**|Yerel ayarda kısaltılmış ay adı|
|**% B**|Yerel ayarda tam ay adı|
|**% c**|Yerel ayar için uygun tarih ve saat gösterimi|
|**% C**|Yıl, 100 bölü ve ondalık sayı olarak bir tamsayıya kesildi (00 − 99)|
|**% d**|Ondalık sayı olarak ayın günü (01-31)|
|**% D**|**% M/% d/% y** ile eşdeğer|
|**% e**|Bir ondalık sayı (1-31) olarak ayın günü, tek basamakların önünde bir boşluk|
|**% F**|**% Y ile eşdeğer-% m-% d**|
|**% g**|ISO 8601 hafta tabanlı yılın ondalık sayı olarak son 2 basamağı (00-99)|
|**% G**|Bir ondalık sayı olarak ISO 8601 hafta tabanlı yıl|
|**% h**|Kısaltılmış ay adı ( **% b** ile eşdeğer)|
|**% H**|24 saat biçiminde saat (00-23)|
|**% I**|12 saat biçiminde saat (01-12)|
|**% j**|Ondalık sayı olarak yılın günü (001-366)|
|**% d**|Ondalık sayı olarak ay (01-12)|
|**% D**|Ondalık sayı olarak dakika (00-59)|
|**% n**|Bir yeni satır karakteri (**\n**)|
|**% p**|Yerel ayar olarak/P.M. 12 saatlik saat için gösterge|
|**% r**|Yerel ayarın 12 saat saat|
|**% R**|**% H:%d** ile eşdeğer|
|**% S**|Ondalık sayı olarak saniye (00-59)|
|**% t**|Yatay sekme karakteri (**\t**)|
|**% T**|**% H:%d:% S**, ISO 8601 zaman biçimi ile eşdeğerdir|
|**% u**|Bir ondalık sayı olarak ISO 8601 iş günü (1-7; Pazartesi 1 ' dir)|
|**% U**|Yılın hafta numarası (00-53), ilk Pazar haftanın ilk günü 1|
|**% V**|ISO 8601 hafta numarası ondalık sayı olarak (00-53)|
|**% w**|Ondalık sayı olarak hafta içi (0-6; Pazar 0 ' dır)|
|**% W**|Yılın hafta sayısı (00-53), ilk Pazartesi haftanın ilk günü 1|
|**% x**|Yerel ayar için tarih gösterimi|
|**% X**|Yerel ayar için zaman gösterimi|
|**% y**|Ondalık sayı olarak yüzyıl olmadan yıl (00-99)|
|**% Y**|Ondalık sayı olarak yüzyıl ile yıl|
|**% z**|ISO 8601 biçiminde UTC 'den konum; Saat dilimi bilinmiyorsa karakter yok|
|**% Z**|Kayıt defteri ayarlarına bağlı olarak, yerel ayarın saat dilimi adı ya da saat dilimi kısaltması; Saat dilimi bilinmiyorsa karakter yok|
|**%%**|Yüzde işareti|

**Printf** işlevinde olduğu gibi, **#** bayrak herhangi bir biçimlendirme koduna önek alabilir. Bu durumda, biçim kodunun anlamı aşağıdaki şekilde değiştirilir.

|Kodu biçimlendirme|Anlamı|
|-----------------|-------------|
|**% #a**, **% #A**, **% #b**, **% #B**, **% #g**, **% #G**, **% #h**, **% #n**, **%**#p, **% #t**, **% #u,%** **#w**, **% #X**, **% #z**, **%**#Z, **%#%**|**#** bayrak yoksayıldı.|
|**% #c**|Yerel ayar için uygun olan uzun tarih ve saat gösterimi. Örneğin: "Salı, 12 Mart 1995, 12:41:29".|
|**% #x**|Yerel ayara uygun uzun tarih gösterimi. Örneğin: "Salı, 12 Mart 1995".|
|**% #d**, **% #D**, **% #e**, **% #F**, **% #H**, **% #I**, **% #j**, **% #m**, **%**#M, **% #r**, **% #R,%**#S, **% #T**,% **#U,%** **#V**, **% #W**, **% #y**, **%** #Y |Baştaki sıfırları veya boşlukları (varsa) kaldırın.|

**% V**, **% g** ve **% g** tarafından üretilen ISO 8601 haftası ve hafta tabanlı yıl, Pazartesi günü başlayan, hafta 1 yılı, yılın en az dört günü içeren ilk hafta olan 4 Ocak 'tan oluşan hafta. Yılın ilk Pazartesi değeri 2, 3 veya 4 ise, önceki günler önceki yılın son haftasının bir parçasıdır. Bu günler için, **% V** 53 ile değiştirilmiştir ve hem **% g** hem de **% g** , önceki yılın rakamıyla değiştirilmiştir.

> [!NOTE]
> `strftime`Öğesinden bir işaretçiye döndürülen işlevlerden birini kullanırken, `tm` `gmtime` ve belirticileri ile yazdırılan değerler `%Z` doğru olmayacaktır `%z` . Bunun nedeni, `tm` C standardı tarafından belirtilen yapının saat dilimi adı ve kaydırmasına ilişkin bilgileri içermez. Bunun yerine, saat dilimi bilgileri genel değişkenler [ `_timezone` ve ile `_dstbias` ](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)doldurulur.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strftime**|\<time.h>|
|**wcsftime**|\<time.h> veya \<wchar.h>|
|**_strftime_l**|\<time.h>|
|**_wcsftime_l**|\<time.h> veya \<wchar.h>|

**_Strftime_l** ve **_wcsftime_l** işlevleri Microsoft 'a özgüdür. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[Zaman](time-time32-time64.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Ayarlar](../../c-runtime-library/locale.md) <br/>
[Zaman Yönetimi](../../c-runtime-library/time-management.md) <br/>
[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md) <br/>
[localeconv](localeconv.md) <br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md) <br/>
[strcoll Işlevleri](../../c-runtime-library/strcoll-functions.md) <br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
