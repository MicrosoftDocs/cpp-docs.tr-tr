---
title: strftime, wcsftime, _strftime_l, _wcsftime_l
ms.date: 03/22/2018
apiname:
- strftime
- _wcsftime_l
- _strftime_l
- wcsftime
apilocation:
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
apitype: DLLExport
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
ms.openlocfilehash: 932a7827ef61a5e111f86f8bc44291827843b76e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353852"
---
# <a name="strftime-wcsftime-strftimel-wcsftimel"></a>strftime, wcsftime, _strftime_l, _wcsftime_l

Bir saat dizesi biçimi.

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

*maxsıze*<br/>
Boyutu *strDest* arabelleğinin karakter cinsinden ölçülen (**char** veya **wchar_t**).

*Biçim*<br/>
Biçim denetimi dizesi.

*timeptr*<br/>
**TM** veri yapısı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**strftime** yerleştirilen karakter sayısını döndürür *strDest* ve **wcsftime** karşılık gelen geniş karakter sayısını döndürür.

Toplam sayısı dahil, sonlandırıcı null karakter ise birden fazla *maxsıze*hem **strftime** ve **wcsftime** 0 ve içeriğini döndürmek  *strDest* belirsiz olduğundan.

Karakter sayısı *strDest* değişmez karakter sayısına eşittir *biçimi* eklenebilir herhangi bir karakter yanı sıra *biçimi* biçimlendirme kodları aracılığıyla. Bir dizenin Sonlandırıcı null dönüş değeri katılmaz.

## <a name="remarks"></a>Açıklamalar

**Strftime** ve **wcsftime** işlevleri biçimi **tm** saat değerinde *timeptr* sağlanan göre  *Biçim* bağımsız değişkeni ve depolama arabelleğinde sonucu *strDest*. En fazla *maxsıze* karakter dizesini yerleştirilir. Alanları açıklamasını *timeptr* yapısı için bkz: [asctime](asctime-wasctime.md). **wcsftime** geniş karakter eşdeğerdir **strftime**; dize işaretçisi bağımsız değişkeni bir geniş karakter dizesine işaret eder. Bu işlevler, aynı şekilde davranır.

Bu işlev, parametrelerini doğrular. Varsa *strDest*, *biçimi*, veya *timeptr* null bir işaretçiyse veya **tm** veri yapısı tarafından ele *timeptr* (örneğin, tarih veya saat aralık değerleri içeriyorsa), geçersiz veya *biçimi* dizesi geçersiz biçimlendirme kodu içerir, içindeaçıklananşekildegeçersizparametreişleyicisiçağrılır[Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için ayarlar ve işlev 0 döndürür yürütülmesine izin veriliyorsa **errno** için **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsftime**|**strftime**|**strftime**|**wcsftime**|

*Biçimi* bağımsız değişkeni, bir veya daha fazla kodlarının; görüldüğü oluşur **printf**, biçimlendirme kodlarını yüzde işareti tarafından öncelenen (**%**). İle başlamayan karakter **%** için değişmeden kopyalanır *strDest*. **Lc_tıme** geçerli yerel ayarının kategori etkiler çıkış biçimini **strftime**. (Daha fazla bilgi için **lc_tıme**, bkz: [setlocale](setlocale-wsetlocale.md).) **Strftime** ve **wcsftime** işlevleri kullanmak şu anda ayarlanmış yerel ayar. **_Strftime_l** ve **_wcsftime_l** bu işlevlerin sürümleri, yerel ayar bir parametre olarak almak ve ayarlanmış yerine kullanan hariç, aynıdır yerel ayar. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

**Strftime** işlevleri bu kodları biçimlendirme desteği:

|||
|-|-|
|Kod|Değiştirme dizesi|
|**%a**|Kısaltılmış gün adını yerel|
|**%A**|Yerel ayarında tam haftanın günü adı|
|**%b**|Yerel ayar kısaltılmış ay adı|
|**%B**|Tam ay adını yerel|
|**%c**|Tarih ve saat temsili yerel ayar için uygun|
|**%C**|100 ile ayrılmış ve bir tamsayı değerine kesilmiş (00−99) ondalık sayı olarak yıl|
|**%d**|(01-31) ondalık sayı olarak ayın günü|
|**%D**|Eşdeğer **%m/%d/%y**|
|**%e**|Tek basamaklı bir boşluk ile burada öncelenen (1-31) ondalık sayı olarak ayın günü|
|**%F**|Eşdeğer **%Y-%m-%d**|
|**%g**|Son 2 basamaklı bir ondalık sayı olarak ISO 8601 hafta tabanlı yılın (00 - 99)|
|**%G**|ISO 8601 yıl hafta tabanlı bir ondalık sayı olarak|
|**%h**|Kısaltılmış ay adını (eşdeğer **%b**)|
|**%H**|Saat, 24 saat biçiminde (00 - 23)|
|**%I**|Saat 12 saatlik biçimde (01-12)|
|**%j**|Bir ondalık sayı (001-366) olarak yılın günü|
|**%m**|(01-12) bir ondalık sayı olarak ayı|
|**%M**|Ondalık sayı olarak dakika (00 - 59)|
|**%n**|Yeni satır karakteri (**\n**)|
|**%p**|Yerel dakikaları. 12 saatlik düzende göstergesi|
|**%r**|Yerel 12 saatlik zaman|
|**%R**|Eşdeğer **% H: %M**|
|**%S**|İkinci bir ondalık sayı olarak (00 - 59)|
|**%t**|Yatay sekme karakterinin (**\t**)|
|**%T**|Eşdeğer **% H: % M: %S**, ISO 8601 zaman biçimi|
|**%u**|(1-7; ondalık sayı olarak ISO 8601 haftanın günü Pazartesi 1'dir)|
|**%U**|Bir ondalık sayı olarak yıl hafta sayısı (00 - 53), ilk Pazar 1 haftanın ilk günü olduğu|
|**%V**|ISO 8601 hafta numarası bir ondalık sayı olarak (00 - 53)|
|**%w**|Ondalık sayı olarak haftanın günü (0 - 6; Pazar 0'dır)|
|**%W**|Bir ondalık sayı olarak yıl hafta sayısı (00 - 53), ilk Pazartesi 1 haftanın ilk günü olduğu|
|**%x**|Yerel ayar için tarih gösterimi|
|**%X**|Yerel ayar için zaman gösterimi|
|**%y**|Olmadan century, ondalık sayı olarak yıl (00 - 99)|
|**%Y**|Century, ondalık sayı olarak yılı|
|**%z**|ISO 8601 biçimli UTC uzaklığı; saat dilimi bilinmiyorsa, herhangi bir karakter|
|**%Z**|Yerel saat dilimi adını veya kayıt defteri ayarlarına bağlı olarak saat dilimi kısaltması; saat dilimi bilinmiyorsa, herhangi bir karakter|
|**%%**|Yüzde işareti|

Olarak **printf** işlevi **#** bayrağı biçimlendirme kodlar önek. Bu durumda, biçim kodu anlamı şu şekilde değiştirilir.

|Kodu biçimlendirme|Açıklama|
|-----------------|-------------|
|**% #a**, **%#A**, **%#b**, **%#B**, **%#g**, **%#G**, **%#h**, **%#n**, **%#p**, **%#t**, **%#u**, **%#w**, **%#X** , **%#z**, **%#Z**, **%#%**|**#** bayrağı yok sayılır.|
|**%#c**|Uzun tarih ve saat gösterimi, yerel ayar için uygun. Örneğin: "Salı, 14 Mart 1995, 12:41:29".|
|**%#x**|Uzun tarih gösterimi, yerel ayara uygun. Örneğin: "Salı, 14 Mart 1995".|
|**%#d**, **%#D**, **%#e**, **%#F**, **%#H**, **% #I**, **%#j**, **%#m**, **%#M**, **%#r**, **%#R**, **%#S**, **%#T** , **%#U**, **%#V**, **%#W**, **%#y**, **%#Y**|Baştaki sıfırlar veya alanları (varsa) kaldırın.|

ISO 8601 haftanın günü ve hafta tabanlı yıl tarafından üretilen **%V**, **%g**, ve **%G**, Pazartesi günü başlayan bir hafta hafta 1 Ocak, ilk 4, içeren hafta olduğu kullanır. Bu hafta yılın en az dört günü içerir. Yılın ilk Pazartesi 2, 3 veya 4, önceki gün önceki yılın geçen hafta parçasıdır. Söz konusu gün için **%V** 53 hem de tarafından değiştirilir **%g** ve **%G** önceki yılın basamak değiştirilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strftime**|\<TIME.h >|
|**wcsftime**|\<TIME.h > veya \<wchar.h >|
|**_strftime_l**|\<TIME.h >|
|**_wcsftime_l**|\<TIME.h > veya \<wchar.h >|

**_Strftime_l** ve **_wcsftime_l** Microsoft'a özgü işlevlerdir. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bakın [zaman](time-time32-time64.md).

## <a name="see-also"></a>Ayrıca bkz.

[locale](../../c-runtime-library/locale.md) <br/>
[Zaman Yönetimi](../../c-runtime-library/time-management.md) <br/>
[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md) <br/>
[localeconv](localeconv.md) <br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md) <br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md) <br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
