---
title: strftime, wcsftime, _strftime_l, _wcsftime_l | Microsoft Docs
ms.custom: ''
ms.date: 03/22/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _strftime_l function
- strftime function
- tcsftime function
- _wcsftime_l function
- wcsftime function
- _tcsftime function
- time strings
ms.assetid: 6330ff20-4729-4c4a-82af-932915d893ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 573e89b7be9818ac45f70c7c614e3bf7869c95f7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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

*MaxSize*<br/>
Boyutunu *strDest* karakter cinsinden arabellek (**char** veya **wchar_t**).

*Biçimi*<br/>
Biçim denetimi dizesi.

*timeptr*<br/>
**TM** veri yapısı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**strftime** yerleştirilen karakterlerin sayısını döndürür *strDest* ve **wcsftime** karşılık gelen geniş karakter sayısını verir.

Sonlandırma null gibi karakterler toplam sayısı ise birden fazla *maxsize*, her iki **strftime** ve **wcsftime** 0 ve içeriğini döndürmek  *strDest* belirsiz olduğundan.

Karakter sayısını *strDest* değişmez değer karakter sayısına eşittir *biçimi* eklenebilir herhangi bir karakteri yanı sıra *biçimi* biçimlendirme kodları aracılığıyla. Bir dizenin sonlandırma null dönüş değeri sayılmaz.

## <a name="remarks"></a>Açıklamalar

**Strftime** ve **wcsftime** işlevleri biçimi **tm** saat değerinde *timeptr* sağlanan göre  *Biçim* bağımsız değişkeni ve deposu sonuç arabelleği *strDest*. En fazla *maxsize* karakter dizesini yerleştirilir. Alanları açıklaması *timeptr* yapısı için bkz: [asctime](asctime-wasctime.md). **wcsftime** joker karakter eşdeğerdir **strftime**; dize işaretçisi bağımsız değişkeni bir joker karakter dizesi işaret eder. Bu işlevler aynı şekilde aksi davranır.

Bu işlev parametrelerini doğrular. Varsa *strDest*, *biçimi*, veya *timeptr* null işaretçinin veya **tm** veri yapısı tarafından ele *timeptr* (örneğin, tarih veya saat dışında aralık değerleri içeriyorsa), geçersiz veya *biçimi* anlatıldığıgibigeçersizparametreişleyicisiçağrılır,dizegeçersizbirbiçimlendirmekoduiçerir[Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için 0 işlevi döndürür ve kümelerini yürütülmesine izin veriliyorsa **errno** için **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsftime**|**strftime**|**strftime**|**wcsftime**|

*Biçimi* bağımsız değişkeni oluşan bir veya daha fazla kodları; içinde **printf**, biçimlendirme kodları yüzde işaretiyle öncesinde (**%**). İle başlamayan karakter **%** için değişmeden kopyalanır *strDest*. **Lc_tıme** geçerli yerel ayar kategorisi etkiler çıktı biçimlendirmesi **strftime**. (Daha fazla bilgi için **lc_tıme**, bkz: [setlocale](setlocale-wsetlocale.md).) **Strftime** ve **wcsftime** işlevlerini kullanan ayarlanmış yerel ayar. **_Strftime_l** ve **_wcsftime_l** yerel bir parametre olarak geçirmesine ve ayarlanmış yerine kullanan dışında bu işlevlerin sürümleri aynı yerel ayar. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

**Strftime** bu biçimlendirme kodları desteği çalışır:

|||
|-|-|
|Kod|Değiştirme dizesi|
|**%a**|Yerel kısaltılmış haftanın günü adı|
|**%A**|Tam haftanın günü adı yerel|
|**%b**|Yerel kısaltılmış ay adı|
|**%B**|Yerel tam ay adı|
|**%c**|Yerel ayarlar için uygun tarih ve saat gösterimi|
|**%C**|100 ile ayrılmış ve bir tamsayı olarak ondalık bir sayı (00−99) kısaltılır yıl|
|**%d**|Ondalık bir sayı (01-31) olarak ayın günü|
|**%D**|Eşdeğer **%m/%d/%y**|
|**%e**|Tek basamaklı boşlukla burada öncesinde ondalık bir sayı (1-31) olarak ayın günü|
|**%F**|Eşdeğer **%Y-%m-%d**|
|**%g**|Son 2 basamaklı bir ondalık sayı olarak ISO 8601 haftanın tabanlı yılın (00 - 99)|
|**%G**|Ondalık bir sayı olarak ISO 8601 haftanın tabanlı yıl|
|**%h**|Kısaltılmış ay adı (eşdeğer **%b**)|
|**%H**|24 saat biçiminde saat (00 - 23)|
|**%I**|Saat 12 saat biçiminde (01-12)|
|**%j**|Ondalık bir sayı (001-366) olarak yılın günü|
|**%m**|Ondalık bir sayı (01-12) olarak ay|
|**%M**|Ondalık sayı olarak dakika (00 - 59)|
|**%n**|Yeni satır karakteri (**\n**)|
|**%p**|Yerel dakikaları. 12 saatlik göstergesi|
|**%r**|Yerel 12 saatlik zaman|
|**%R**|Eşdeğer **% y: %M**|
|**%S**|İkinci bir ondalık sayı olarak (00 - 59)|
|**%t**|Yatay sekme karakteri (**\t**)|
|**%T**|Eşdeğer **y: % M: %s**, ISO 8601 saat biçimi|
|**%u**|(1-7; ondalık bir sayı olarak ISO 8601 haftanın günü Pazartesi 1.)|
|**%U**|Ondalık bir sayı olarak yılın hafta numarasını (00 - 53), ilk Pazar 1 haftanın ilk günü|
|**%V**|ISO 8601 haftanın sayı ondalık bir sayı olarak (00 - 53)|
|**%w**|Haftanın günü ondalık bir sayı olarak (0 - 6; Pazar 0'dır)|
|**%W**|Ondalık bir sayı olarak yılın hafta numarasını (00 - 53), ilk Pazartesi günü 1 haftanın ilk günü|
|**%x**|Yerel ayar için tarih gösterimi|
|**%X**|Yerel saat gösterimi|
|**%y**|Ondalık sayı olarak century olmadan yıl (00 - 99)|
|**%Y**|Ondalık sayı olarak century yıl|
|**%z**|UTC uzaklığı ISO 8601 biçiminde; saat dilimi bilinmiyorsa herhangi bir karakter|
|**%Z**|Yerel saat dilimi adı ya da kayıt defteri ayarlarına bağlı olarak, saat dilimi kısaltması; saat dilimi bilinmiyorsa herhangi bir karakter|
|**%%**|Yüzde işareti|

Olarak **printf** işlevi, **#** bayrağı herhangi bir biçimlendirme kodu önek. Bu durumda, biçim kodu anlamını şu şekilde değiştirilir.

|Biçim Kodu|Açıklama|
|-----------------|-------------|
|**% #a**, **%#A**, **%#b**, **%#B**, **%#g**, **%#G**, **%#h**, **%#n**, **%#p**, **%#t**, **%#u**, **%#w**, **%#X** , **%#z**, **%#Z**, **%#%**|**#** Bayrak göz ardı edilir.|
|**%#c**|Uzun tarih ve saat gösterimi, yerel uygun. Örneğin: "Salı, 14 Mart 1995, 12:41:29".|
|**%#x**|Uzun tarih gösterimi, yerel ayar için uygun. Örneğin: "Salı, 14 Mart 1995".|
|**%#d**, **%#D**, **%#e**, **%#F**, **%#H**, **% #I**, **%#j**, **%#m**, **%#M**, **%#r**, **%#R**, **%#S**, **%#T** , **%#U**, **%#V**, **%#W**, **%#y**, **%#Y**|Öndeki sıfırların veya alanları (varsa) kaldırın.|

ISO 8601 haftanın günü ve yıl hafta tabanlı üretilen **%V**, **%g**, ve **%G**, Pazartesi günü başlar haftada bir hafta 1 Ocak ilk olan 4, içeren hafta olduğu kullanır en az dört gün yılı içeren haftadır. Yılın ilk Pazartesi 2, 3 veya 4, önceki gün önceki yılın son haftanın bir parçasıdır. Bu gün **%V** 53 ve her iki tarafından değiştirilir **%g** ve **%G** önceki yıl basamak tarafından değiştirilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strftime**|\<time.h >|
|**wcsftime**|\<time.h > veya \<wchar.h >|
|**_strftime_l**|\<time.h >|
|**_wcsftime_l**|\<time.h > veya \<wchar.h >|

**_Strftime_l** ve **_wcsftime_l** Microsoft'a özgü işlevlerdir. Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bkz [zaman](time-time32-time64.md).

## <a name="see-also"></a>Ayrıca bkz.

[locale](../../c-runtime-library/locale.md) <br/>
[Zaman Yönetimi](../../c-runtime-library/time-management.md) <br/>
[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md) <br/>
[localeconv](localeconv.md) <br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md) <br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md) <br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
