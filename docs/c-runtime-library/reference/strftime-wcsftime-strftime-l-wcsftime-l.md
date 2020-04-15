---
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 5da2c128c54fd88bb874b360f5a966f17b14a935
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350018"
---
# <a name="strftime-wcsftime-_strftime_l-_wcsftime_l"></a>strftime, wcsftime, _strftime_l, _wcsftime_l

Bir zaman dizesi biçimlendirin.

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

*Maxsize*<br/>
Karakter cinsinden ölçülen *strDest* arabelleği boyutu **(char** veya **wchar_t).**

*Biçim*<br/>
Biçim denetimi dizesi.

*timeptr*<br/>
**tm** veri yapısı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**strftime** *strDest* ve **wcsftime** yerleştirilen karakter sayısını döndürür geniş karakter karşılık gelen sayısını döndürür.

Sonlandırıcı null da dahil olmak üzere toplam karakter sayısı *maxsize*daha fazla ise , hem **strftime** ve **wcsftime** return 0 ve *strDest* içeriği belirsizdir.

*strDest'teki* karakter sayısı, *biçimdeki* gerçek karakter sayısına ve biçimlendirme kodları aracılığıyla *biçime* eklenebilecek karakterlere eşittir. Bir dizenin sonlandırıcı null'u iade değerinde sayılmaz.

## <a name="remarks"></a>Açıklamalar

**Strftime** ve **wcsftime** fonksiyonları verilen biçim bağımsız *değişkenine* göre *timeptr* **tm** zaman değerini biçimlendirin ve arabellek *strDest*sonucu depolamak . En fazla, *maxsize* karakterler dize yerleştirilir. *Zaman ptr* yapısındaki alanların açıklaması için [asctime'a](asctime-wasctime.md)bakın. **wcsftime** **strftime**geniş karakter eşdeğerdir; dize işaretçisi bağımsız değişkeni geniş karakterli bir dizeyi işaret eder. Bu işlevler aynı şekilde başka türlü çalışır.

Bu işlev parametrelerini doğrular. *StrDest*, *biçim*, veya *timeptr* null işaretçisi ise veya *timeptr* tarafından adreslenen **tm** veri yapısı geçersizse (örneğin, saat veya tarih için aralık dışı değerler içeriyorsa) veya *biçim* dizesi geçersiz biçimlendirme kodu içeriyorsa, geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, işlev 0 döndürür ve **EINVAL** **için errno** ayarlar.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsftime**|**strftime**|**strftime**|**wcsftime**|

*Biçim* bağımsız değişkeni bir veya daha fazla koddan oluşur; **printf'te**olduğu gibi, biçimlendirme kodları yüzde**%** işaretinden önce gelir ( ). Ile **%** başlamayan karakterler *strDest'e*değişmeden kopyalanır. Geçerli **LC_TIME** yerel LC_TIME kategorisi **strftime**çıktı biçimlendirme etkiler. (LC_TIME hakkında **LC_TIME**daha fazla bilgi için [setlocale'a](setlocale-wsetlocale.md)bakın.) **Strftime** ve **wcsftime** işlevleri şu anda ayarlanmış yerel kullanın. Bu işlevlerin **_strftime_l** ve **_wcsftime_l** sürümleri, yerel alanı bir parametre olarak almaları ve şu anda ayarlanmış yerel ayar yerine bunu kullanmaları dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

**strftime** işlevleri bu biçimlendirme kodlarını destekler:

|||
|-|-|
|Kod|Yedek dize|
|**%a**|Yerel olarak kısaltılmış hafta içi adı|
|**%A**|Yerel olarak tam hafta içi adı|
|**%b**|Yerel deki kısaltılmış ay adı|
|**%B**|Yerel deki tam ay adı|
|**%c**|Yerel ekibe uygun tarih ve saat gösterimi|
|**%C**|Yıl 100'e bölünüp bir tamsayıya bölündü, ondalık sayı (00−99) olarak|
|**%d**|Ondalık sayı olarak ayın günü (01 - 31)|
|**%D**|**%m/%d/%y eşdeğeri**|
|**%e**|Tek basamaklı bir boşluktan önce gelen ondalık sayı (1 - 31) olarak ayın günü|
|**%F**|**%Y-%m-%d eşdeğeri**|
|**%g**|ISO 8601 hafta tabanlı yılın son 2 hanesi ondalık sayı olarak (00 - 99)|
|**%G**|ONdalık sayı olarak ISO 8601 hafta tabanlı yıl|
|**%h**|Kısaltılmış ay adı **(%b'ye**eşdeğer)|
|**%H**|24 saat biçiminde saat (00 - 23)|
|**%I**|12 saatlik formatta saat (01 - 12)|
|**%j**|Ondalık sayı olarak yılın günü (001 - 366)|
|**%m**|Ondalık sayı olarak ay (01 - 12)|
|**%M**|Ondalık sayı olarak dakika (00 - 59)|
|**%n**|Yeni bir çizgi karakteri (**\n**)|
|**%p**|Yerel bölge A.M./P.M. 12 saatlik saat için gösterge|
|**%r**|Yerel yerin 12 saatlik saat süresi|
|**%R**|**%H:%M'ye** eşdeğer|
|**%S**|Ondalık sayı olarak ikinci (00 - 59)|
|**%t**|Yatay sekme karakteri (**\t**)|
|**%T**|**%H:%M:%S'ye**eşdeğer , ISO 8601 zaman biçimi|
|**%u**|ISO 8601 ondalık sayı olarak hafta içi (1 - 7; Pazartesi 1)|
|**%U**|İlk Pazar haftanın ilk günü olan ondalık sayı (00 - 53) olarak yılın hafta sayısı|
|**%V**|ONdalık sayı olarak ISO 8601 hafta numarası (00 - 53)|
|**%w**|Ondalık sayı olarak hafta içi (0 - 6; Pazar 0)|
|**%W**|Ondalık sayı (00 - 53) olarak yılın hafta sayısı, ilk Pazartesi haftanın ilk günü 1|
|**%x**|Yerel bölge için tarih gösterimi|
|**%X**|Yerel alan için zaman gösterimi|
|**%y**|Yüzyıl olmadan yıl, ondalık sayı (00 - 99) olarak|
|**%Y**|Yüzyıl ile yıl, ondalık sayı olarak|
|**%z**|ISO 8601 formatında UTC'den mahsup; saat dilimi bilinmiyorsa karakter yok|
|**%Z**|Kayıt defteri ayarlarına bağlı olarak, yerel yerin saat dilimi adı veya saat dilimi kısaltması; saat dilimi bilinmiyorsa karakter yok|
|**%%**|Yüzde işareti|

**printf** işlevinde olduğu **#** gibi, bayrak herhangi bir biçimlendirme kodunu öneleyebilir. Bu durumda, biçim kodunun anlamı aşağıdaki gibi değiştirilir.

|Kodu biçimlendirme|Anlamı|
|-----------------|-------------|
|**%#a**, **%#A**, **%#b**, **%#B**, **%#g**, **%#G**, **%#h**, **%#n**, **%#p**, **%#t,** **%#u**, **%#w**, **%#X,** **%#z**, **%#Z**,**%#%**|**#** bayrak yoksayılır.|
|**%#c**|Uzun tarih ve saat gösterimi, yerel için uygundur. Örneğin: "Salı, Mart 14, 1995, 12:41:29".|
|**%#x**|Uzun tarih gösterimi, yerel ekibe uygun. Örneğin: "Salı, 14 Mart 1995".|
|**%#d**, **%#D**, **%#e**, **%#F**, **%#H**, **%#I**, **%#j**, **%#m**, **%#M**, **%#r**, **%#R**, **%#S**, **%#T**, **%#U**, **%#V #W** **,** **%#y**, **%#Y**|Önde gelen sıfırları veya boşlukları (varsa) kaldırın.|

%V , **%g**ve **%G**tarafından **%V**üretilen ISO 8601 haftası ve hafta bazlı yıl, 1. Yılın ilk Pazartesi günü 2, 3 veya 4 ise, önceki günler bir önceki yılın son haftasının bir parçasıdır. Bu günler için **%V** 53 ile değiştirilir ve hem **%g** hem de **%G** bir önceki yılın rakamlarıyla değiştirilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strftime**|\<time.h>|
|**wcsftime**|\<time.h> \<veya wchar.h>|
|**_strftime_l**|\<time.h>|
|**_wcsftime_l**|\<time.h> \<veya wchar.h>|

**_strftime_l** ve **_wcsftime_l** işlevleri Microsoft'a özgüdir. Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

[Zaman](time-time32-time64.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Yerel Ayar](../../c-runtime-library/locale.md) <br/>
[Zaman Yönetimi](../../c-runtime-library/time-management.md) <br/>
[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md) <br/>
[localeconv](localeconv.md) <br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md) <br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md) <br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
