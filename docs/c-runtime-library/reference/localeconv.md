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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: c4e1820ac412a0447c5059ecc92375275f7b2701
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218643"
---
# <a name="localeconv"></a>localeconv

Yerel ayarlar hakkında ayrıntılı bilgi alır.

## <a name="syntax"></a>Syntax

```C
struct lconv *localeconv( void );
```

## <a name="return-value"></a>Dönüş Değeri

**localeconv** , [struct lconv](../../c-runtime-library/standard-types.md)türünde bir doldurulmuş nesneye bir işaretçi döndürür. Nesnesinde bulunan değerler, iş parçacığı yerel depolama alanındaki yerel ayarlar ayarlarından kopyalanır ve **localeconv**öğesine yapılan sonraki çağrılar tarafından geçersiz kılınabilir. Bu nesnedeki değerlerde yapılan değişiklikler yerel ayar ayarlarını değiştirmez. **LC_ALL**, **LC_MONETARY**veya **LC_NUMERIC** *Kategori* değerleri ile [setlocale](setlocale-wsetlocale.md) 'e çağrılar yapının içeriğinin üzerine yazar.

## <a name="remarks"></a>Açıklamalar

**Localeconv** işlevi, geçerli yerel ayar için sayısal biçimlendirme hakkında ayrıntılı bilgiler alır. Bu bilgiler **lconv**türünde bir yapıda saklanır. Yerel AYARDA tanımlanan **lconv** yapısı. H, aşağıdaki üyeleri içerir:

|Alan|Anlamı|
|-|-|
decimal_point,<br/>_W_decimal_point|Parasal olmayan miktarlar için ondalık işaret karakteri işaretçisi.
thousands_sep,<br/>_W_thousands_sep|Parasal olmayan miktarlar için basamak gruplarını ondalık noktanın soluna ayıran karakter işaretçisi.
gruplandırma|**`char`** Parasal olmayan miktarlar içindeki her bir basamak grubunun boyutunu içeren, boyutlu bir tamsayı işaretçisi.
int_curr_symbol,<br/>_W_int_curr_symbol|Geçerli yerel ayar için uluslararası para birimi simgesine yönelik işaretçi. İlk üç karakter, *para birimi ve fon standardı gösteriminin ıso 4217 kodlarında* tanımlanan alfabetik uluslararası para birimi sembolünü belirtir. Dördüncü karakter (hemen önceki null karakter), parasal miktardan uluslararası para birimi sembolünü ayırır.
currency_symbol,<br/>_W_currency_symbol|Geçerli yerel ayar için yerel para birimi simgesine yönelik işaretçi.
mon_decimal_point,<br/>_W_mon_decimal_point|Parasal miktarlar için ondalık noktalı karakter işaretçisi.
mon_thousands_sep,<br/>_W_mon_thousands_sep|Para miktarlarındaki ondalık basamak sol tarafında bulunan basamak grupları için ayıraç işaretçisi.
mon_grouping|**`char`** Parasal miktarlar içindeki her bir basamak grubunun boyutunu içeren, boyutlu bir tamsayı işaretçisi.
positive_sign,<br/>_W_positive_sign|Negatif parasal miktarlar için işaret belirten dize.
negative_sign,<br/>_W_negative_sign|Negatif parasal miktarlar için işaret belirten dize.
int_frac_digits|Uluslararası şekilde biçimlendirilen parasal miktarlar içindeki ondalık noktanın sağına doğru basamak sayısı.
frac_digits|Biçimlendirilen parasal miktarlar içindeki ondalık noktanın sağına doğru basamak sayısı.
p_cs_precedes|Eksi biçimli parasal miktar için para birimi simgesi değerden önce geliyorsa 1 olarak ayarlayın. Sembol değeri aşağıdaki ise 0 olarak ayarlanır.
p_sep_by_space|Para birimi simgesi negatif olarak biçimlendirilen parasal miktar için değerden boşlukla ayrılırsa, 1 olarak ayarlanır. Boşluk ayrımı yoksa 0 olarak ayarlayın.
n_cs_precedes|Para birimi simgesi negatif biçimli parasal miktar değerinden önce geliyorsa 1 olarak ayarlayın. Sembol başarılı olursa 0 olarak ayarlayın.
n_sep_by_space|Para birimi simgesi negatif biçimli parasal miktar için değerden boşlukla ayrılırsa, 1 olarak ayarlanır. Boşluk ayrımı yoksa 0 olarak ayarlayın.
p_sign_posn|Eksi biçimli parasal miktarların pozitif işaretin konumu.
n_sign_posn|Negatif biçimli parasal miktarların pozitif oturum açma konumu.

Belirtilmedikçe, ve sürümleri olan **lconv** yapısının üyeleri `char *` `wchar_t *` dizeler için işaretçilerdir. **""** (Veya **L ""** için) değerine eşit olan bunlardan herhangi biri **`wchar_t`** <strong>\*</strong> sıfır uzunluğunda ya da geçerli yerel ayarda desteklenmiyor. **Decimal_point** ve **_W_decimal_point** her zaman desteklendiğini ve sıfır dışı uzunlukta olduğunu unutmayın.

**`char`** Yapının üyeleri karakter değil, küçük negatif olmayan sayılardır. **CHAR_MAX** eşit olan bunlardan herhangi biri geçerli yerel ayarda desteklenmez.

**Gruplandırma** ve **mon_grouping** değerleri aşağıdaki kurallara göre yorumlanır:

- **CHAR_MAX** -daha fazla gruplandırma gerçekleştirmeyin.

- 0-kalan basamakların her biri için önceki öğeyi kullanın.

- *n* -geçerli grubu oluşturan basamak sayısı. Sonraki öğe, geçerli gruptan önceki basamak grubunun boyutunu belirleyecek şekilde incelenir.

**İnt_curr_symbol** değerleri aşağıdaki kurallara göre yorumlanır:

- İlk üç karakter, *para birimi ve fon standardı gösteriminin ıso 4217 kodlarında* tanımlanan alfabetik uluslararası para birimi sembolünü belirtir.

- Dördüncü karakter (null karakterden hemen önce) Uluslararası para birimi sembolünü parasal miktardan ayırır.

**P_cs_precedes** ve **n_cs_precedes** değerleri aşağıdaki kurallara göre yorumlanır ( **n_cs_precedes** kuralı parantez içinde olur):

- 0-para birimi sembolü, negatif olmayan (negatif) biçimli parasal değer için değeri izler.

- 1-para birimi simgesi negatif olmayan (negatif) biçimli parasal değer için değerden önce gelir.

**P_sep_by_space** ve **n_sep_by_space** değerleri aşağıdaki kurallara göre yorumlanır ( **n_sep_by_space** kuralı parantez içinde olur):

- 0-para birimi simgesi, negatif olmayan (negatif) biçimli parasal değer için değerden alana göre ayrılır.

- 1-para birimi sembolü ve negatif olmayan (negatif) biçimli parasal değer için değer arasında boşluk ayrımı yoktur.

**P_sign_posn** ve **n_sign_posn** değerleri aşağıdaki kurallara göre yorumlanır:

- 0-parantez surround miktarı ve para birimi simgesi.

- 1 işareti dize, miktar ve para birimi simgesinden önce gelir.

- 2-imza dizesi, miktar ve para birimi simgesi izler.

- 3-işareti dize, hemen ardından para birimi simgesinden önce gelir.

- 4-imza dizesi hemen ardından para birimi simgesi izler.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**localeconv**|\<locale.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[setlocale](../../preprocessor/setlocale.md)<br/>
[strcoll Işlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
