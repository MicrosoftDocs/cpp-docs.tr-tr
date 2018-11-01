---
title: localeconv
ms.date: 11/04/2016
apiname:
- localeconv
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- localeconv
helpviewer_keywords:
- lconv type
- localeconv function
- locales, getting information on
ms.assetid: 7ecdb1f2-88f5-4037-a0e7-c754ab003660
ms.openlocfilehash: bf26e4f7b7fb4f0334b57604fe5c4996312bd62a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628154"
---
# <a name="localeconv"></a>localeconv

Yerel ayarlar hakkında ayrıntılı bilgi alır.

## <a name="syntax"></a>Sözdizimi

```C
struct lconv *localeconv( void );
```

## <a name="return-value"></a>Dönüş Değeri

**localeconv** doldurulmuş türünde bir nesne için bir işaretçi döndürür [yapı lconv](../../c-runtime-library/standard-types.md). Nesnesinde yer alan değerleri iş parçacığı yerel depolama alanında yerel ayarları kopyalanır ve yapılan sonraki çağrılar tarafından geçersiz kılınabilir **localeconv**. Bu nesne değerleri için yapılan değişiklikler yerel ayarları değiştirmeyin. Çağrılar [setlocale](setlocale-wsetlocale.md) ile *kategori* değerlerini **LC_ALL**, **LC_MONETARY**, veya **lc_numerıc** içeriği yapısının üzerine yazın.

## <a name="remarks"></a>Açıklamalar

**Localeconv** işlevi, geçerli yerel ayarı için sayısal biçimlendirme hakkında ayrıntılı bilgiler alır. Bu bilgileri türündeki yapıda depolanan **lconv**. **Lconv** yerel ayarda tanımlanan yapısı. H, aşağıdaki üyeleri içerir:

|Alan|Açıklama|
|-|-|
decimal_point,<br/>_W_decimal_point|Ondalık ayırıcı karakter parasal miktarlar için işaretçi.
thousands_sep,<br/>_W_thousands_sep|Karakter işaretçisi parasal miktarlar için ondalık noktanın solundaki basamak gruplarına ayırır.
gruplandırma|İşaretçi bir **char**-her parasal miktarlarda basamak grubunun boyutunu içeren tamsayı boyutu.
int_curr_symbol,<br/>_W_int_curr_symbol|Geçerli yerel ayar için uluslararası para birimi simgesi işaretçisi. İlk üç karakter sınıfında tanımlandığı gibi uluslararası alfabetik para birimi simgesi belirtin *ISO 4217 kodları gösterimi, para birimi ve fon* standart. Dördüncü karakterini (hemen önceki null karakter) parasal miktardan uluslararası para birimi simgesi ayırır.
currency_symbol,<br/>_W_currency_symbol|Yerel para birimi simgesi geçerli yerel ayar için işaretçi.
mon_decimal_point,<br/>_W_mon_decimal_point|Ondalık ayırıcı karakter parasal miktarlar için işaretçi.
mon_thousands_sep,<br/>_W_mon_thousands_sep|Ayırıcı parasal miktarlar ondalık basamak solundaki basamak grupları için işaretçi.
mon_grouping|İşaretçi bir **char**-her parasal miktarlarda basamak grubunun boyutunu içeren tamsayı boyutu.
positive_sign,<br/>_W_positive_sign|Negatif olmayan bir parasal miktarlar için işaret belirten dize.
negative_sign,<br/>_W_negative_sign|Negatif parasal miktarlar için işaret belirten dize.
int_frac_digits|Uluslararası olarak biçimlendirilmiş parasal miktarlar ondalık noktasının sağındaki basamak sayısı.
frac_digits|Biçimlendirilmiş parasal miktarlar ondalık noktasının sağındaki basamak sayısı.
p_cs_precedes|Para birimi simgesi değeri negatif olmayan biçimlendirilmiş parasal miktarını önceyse 1 olarak ayarlayın. Sembol değeri izliyorsa 0 olarak ayarlayın.
p_sep_by_space|Para birimi simgesi negatif olmayan biçimlendirilmiş parasal miktar değerinden boşlukla ayrılmış ise 1 olarak ayarlayın. Hiçbir alanı ayırma ise 0 olarak ayarlayın.
n_cs_precedes|Para birimi simgesi değeri negatif biçimlendirilmiş parasal miktarını önceyse 1 olarak ayarlayın. Sembol değeri başarılı olursa 0 olarak ayarlayın.
n_sep_by_space|Para birimi simgesi negatif biçimlendirilmiş parasal miktar değerinden boşlukla ayrılmış ise 1 olarak ayarlayın. Hiçbir alanı ayırma ise 0 olarak ayarlayın.
p_sign_posn|Negatif olmayan biçimlendirilmiş parasal miktarlar artı işareti konumu.
n_sign_posn|Negatif biçimlendirilmiş parasal miktarlar artı işareti konumu.

Belirtilen, üyeleri olarak dışında **lconv** sahip yapısı `char *` ve `wchar_t *` sürümleri dizelerin işaretçileridir. Bunlardan birine eşit **""** (veya **L ""** için **wchar_t** <strong>\*</strong>) uzunluğu sıfır ya da geçerli desteklenmiyor yerel ayar. Unutmayın **decimal_point** ve **_W_decimal_point** olan desteklenen her zaman ve sıfır uzunlukta.

**Char** yapının üyeleri olan küçük negatif sayılar, olmayan karakterler. Bunlardan birine eşit **CHAR_MAX** geçerli yerel ayarı desteklenmiyor.

Değerlerini **gruplandırma** ve **mon_grouping** aşağıdaki kurallara göre yorumlanır:

- **CHAR_MAX** -tüm daha fazla gruplandırma gerçekleştirmeyin.

- 0 - her kalan rakamları önceki öğesi kullanın.

- *n* -geçerli grubu oluşturan basamak sayısı. Geçerli Grup önce basamak sonraki grubunun boyutunu belirlemek için sonraki öğeye incelenir.

Değerleri **int_curr_symbol** aşağıdaki kurallara göre yorumlanır:

- İlk üç karakter sınıfında tanımlandığı gibi uluslararası alfabetik para birimi simgesi belirtin *ISO 4217 kodları gösterimi, para birimi ve fon* standart.

- (Null karakteri hemen önceki) Dördüncü karakter uluslararası para birimi simgesi parasal miktardan ayırır.

Değerleri **p_cs_precedes** ve **n_cs_precedes** aşağıdaki kurallara göre yorumlanır ( **n_cs_precedes** kuralıdır parantez içinde):

- 0 - negatif olmayan (negatif) biçimlendirilmiş parasal değerin değerini para birimi simgesi izler.

- 1 - para birimi simgesi için değer negatif olmayan (negatif) biçimlendirilmiş parasal değer önce gelir.

Değerleri **p_sep_by_space** ve **n_sep_by_space** aşağıdaki kurallara göre yorumlanır ( **n_sep_by_space** kuralıdır parantez içinde):

- 0 - para birimi simgesi değerinden negatif olmayan (negatif) biçimlendirilmiş parasal değeri boşlukla ayrılır.

- 1 - para birimi sembolü ve için değer negatif olmayan (negatif) biçimlendirilmiş parasal değer arasında hiçbir alanı ayrım yoktur.

Değerleri **p_sign_posn** ve **n_sign_posn** aşağıdaki kurallara göre yorumlanır:

- 0 - parantez içinde miktar ve para birimi sembolü alın.

- 1 - oturum dize miktar ve para birimi sembolü önce gelir.

- 2 - oturum dize miktar ve para birimi sembolü izler.

- 3 - oturum dize para birimi simgesi hemen önce gelir.

- 4 - oturum aşağıdaki para birimi simgesi hemen dize.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**localeconv**|\<Locale.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Ayrıca bkz.

[locale](../../c-runtime-library/locale.md)<br/>
[setlocale](../../preprocessor/setlocale.md)<br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
