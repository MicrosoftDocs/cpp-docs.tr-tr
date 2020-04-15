---
title: localeconv
ms.date: 4/2/2020
api_name:
- localeconv
- _o_localeconv
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
- api-ms-win-crt-locale-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- localeconv
helpviewer_keywords:
- lconv type
- localeconv function
- locales, getting information on
ms.assetid: 7ecdb1f2-88f5-4037-a0e7-c754ab003660
ms.openlocfilehash: a617980d60b3a12c06b30aab6cd457792a1aa770
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342153"
---
# <a name="localeconv"></a>localeconv

Yerel ayarlar hakkında ayrıntılı bilgi alır.

## <a name="syntax"></a>Sözdizimi

```C
struct lconv *localeconv( void );
```

## <a name="return-value"></a>Dönüş Değeri

**localeconv** bir işaretçiyi dolmuş bir nesne türü [yapı lconv'a](../../c-runtime-library/standard-types.md)döndürür. Nesnede bulunan değerler iş parçacığı yerel depolamadaki yerel ayarlardan kopyalanır ve sonraki **localeconv**çağrıları tarafından üzerine yazılabilir. Bu nesnedeki değerlerde yapılan değişiklikler yerel ayarlar değiştirmez. **LC_ALL,** **LC_MONETARY**veya **LC_NUMERIC** *kategori* değerleriyle [ayaryerele](setlocale-wsetlocale.md) çağrılar yapının içeriğini üzerine yazar.

## <a name="remarks"></a>Açıklamalar

**Localeconv** işlevi, geçerli yerel alan için sayısal biçimlendirme hakkında ayrıntılı bilgi alır. Bu bilgiler **lconv**türünde bir yapıda depolanır. YERELE'de tanımlanan **lconv** yapısı. H, aşağıdaki üyeleri içerir:

|Alan|Anlamı|
|-|-|
decimal_point,<br/>_W_decimal_point|Parasal olmayan miktarlar için ondalık nokta karakterine işaretçi.
thousands_sep,<br/>_W_thousands_sep|Parasal olmayan miktarlar için ondalık noktanın solundaki basamak gruplarını ayıran karakter işaretçisi.
gruplandırma|Parasal olmayan miktarlarda her basamak grubunun boyutunu içeren **char**boyutunda bir tamsayı işaretçisi.
int_curr_symbol,<br/>_W_int_curr_symbol|Geçerli yerel bölge için uluslararası para birimi simgesine işaretçi. İlk üç *karakter, ISO 4217 Para Birimi ve Fonların Temsili için Kodları'nda* tanımlandığı şekilde alfabetik uluslararası para birimi simgesini belirtir. Dördüncü karakter (null karakterden hemen önce) uluslararası para birimi sembolüni parasal miktardan ayırır.
currency_symbol,<br/>_W_currency_symbol|Geçerli yerel bölge için yerel para birimi simgesini işaretçi.
mon_decimal_point,<br/>_W_mon_decimal_point|Parasal miktarlar için ondalık nokta karakterine işaretçi.
mon_thousands_sep,<br/>_W_mon_thousands_sep|Parasal miktarlarda ondalık basamakların solundaki basamak grupları için ayırıcıişaretçi.
mon_grouping|Parasal miktarlarda her basamak grubunun boyutunu içeren **char**boyutunda bir tamsayı işaretçisi.
positive_sign,<br/>_W_positive_sign|Negatif olmayan parasal miktarlar için işaret gösteren dize.
negative_sign,<br/>_W_negative_sign|Negatif parasal miktarlar için işaret gösteren dize.
int_frac_digits|Uluslararası biçimlendirilmiş parasal miktarlarda ondalık noktanın sağına basamak sayısı.
frac_digits|Biçimlendirilmiş parasal miktarlarda ondalık noktanın sağına basamak sayısı.
p_cs_precedes|Negatif biçimlendirilmiş parasal miktar için para birimi sembolü değerden önceyse 1 olarak ayarlayın. Değeri takip eden sembol varsa 0 olarak ayarlayın.
p_sep_by_space|Para birimi sembolü negatif biçimlendirilmiş olmayan parasal miktar için değerden boşlukla ayrılırsa 1 olarak ayarlayın. Boşluk ayrımı yoksa 0 olarak ayarlayın.
n_cs_precedes|Negatif biçimlendirilmiş parasal miktar için para birimi sembolü değerden önceyse 1 olarak ayarlayın. Sembol değer başarılı olursa 0 olarak ayarlayın.
n_sep_by_space|Para birimi sembolü negatif biçimlendirilmiş parasal miktar için değerden boşlukla ayrılırsa 1 olarak ayarlayın. Boşluk ayrımı yoksa 0 olarak ayarlayın.
p_sign_posn|Negatif olmayan biçimlendirilmiş parasal miktarlarda pozitif işaretin konumu.
n_sign_posn|Negatif biçimlendirilmiş parasal miktarlarda pozitif işaretin konumu.

Belirtildiği gibi dışında, **lconv** yapısının `char *` `wchar_t *` üyeleri ve sürümleri dizeleri işaretçilervardır. bunlardan herhangi biri **""** (veya **l""** **wchar_t** <strong>\*</strong>için) eşittir sıfır uzunlukta veya geçerli yerel olarak desteklenmeyen. **decimal_point** ve **_W_decimal_point** her zaman desteklenir ve sıfır olmayan uzunlukta olduğunu unutmayın.

Yapının **char** üyeleri küçük negatif olmayan sayılardır, karakterler değil. **CHAR_MAX** eşit olan bunların hiçbiri geçerli yerel olarak desteklenmez.

**Gruplandırma** ve **mon_grouping** değerleri aşağıdaki kurallara göre yorumlanır:

- **CHAR_MAX** - Başka gruplandırma yapmayın.

- 0 - Kalan basamakların her biri için önceki öğeyi kullanın.

- *n* - Geçerli grubu oluşturan basamak sayısı. Sonraki öğe, geçerli gruptan önce bir sonraki basamak grubunun boyutunu belirlemek için incelenir.

**int_curr_symbol** değerleri aşağıdaki kurallara göre yorumlanır:

- İlk üç karakter, *ISO 4217 Para Birimi ve Fonların Temsili kodları* standardında tanımlandığı şekilde alfabetik uluslararası para birimi simgesini belirtir.

- Dördüncü karakter (null karakterinhemen öncesinde) uluslararası para birimi simgesini parasal miktardan ayırır.

**p_cs_precedes** ve **n_cs_precedes** değerleri aşağıdaki kurallara göre yorumlanır **(n_cs_precedes** kuralı parantez içindedir):

- 0 - Para birimi sembolü negatif olmayan (negatif) biçimlendirilmiş parasal değerin değerini izler.

- 1 - Para birimi sembolü negatif olmayan (negatif) biçimlendirilmiş parasal değeriçin değerden önce gelir.

**p_sep_by_space** ve **n_sep_by_space** değerleri aşağıdaki kurallara göre yorumlanır **(n_sep_by_space** kuralı parantez içindedir):

- 0 - Para birimi sembolü, negatif olmayan (negatif) biçimlendirilmiş parasal değer için boşluktan değere ayrılır.

- 1 - Negatif olmayan (negatif) biçimlendirilmiş parasal değer için para birimi sembolü ile değer arasında boşluk ayrımı yoktur.

**p_sign_posn** ve **n_sign_posn** değerleri aşağıdaki kurallara göre yorumlanır:

- 0 - Parantez, miktar ve para birimi sembolüne çevreler.

- 1 - İşaret dizesi miktar ve para birimi sembolünden önce gelir.

- 2 - İşaret dizesi miktar ve para birimi sembolüizler.

- 3 - İşaret dizesi hemen para birimi sembolü önce gelir.

- 4 - İşaret dizesi hemen para birimi sembolü izler.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**localeconv**|\<locale.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[setlocale](../../preprocessor/setlocale.md)<br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
