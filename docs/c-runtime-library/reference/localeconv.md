---
title: localeconv | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: localeconv
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
apitype: DLLExport
f1_keywords: localeconv
dev_langs: C++
helpviewer_keywords:
- lconv type
- localeconv function
- locales, getting information on
ms.assetid: 7ecdb1f2-88f5-4037-a0e7-c754ab003660
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2cbd897b353f8a915fb4a29d61d0954b9b5a7f53
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="localeconv"></a>localeconv
Yerel ayarlar hakkında ayrıntılı bilgi alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct lconv *localeconv( void );  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 `localeconv`doldurulmuş türünde bir nesne için bir işaretçi döndüren [yapısı lconv](../../c-runtime-library/standard-types.md). Nesnesinde yer alan değerleri iş parçacığı yerel depolama alanında yerel ayarları kopyalanır ve sonraki çağrılar tarafından üzerine yazılabilir `localeconv`. Bu nesnenin değerleri yapılan değişiklikleri yerel ayarları değiştirmeyin. Çağrılar [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) ile `category` değerlerini `LC_ALL`, `LC_MONETARY`, veya `LC_NUMERIC` yapısı içeriğinin üzerine.  
  
## <a name="remarks"></a>Açıklamalar  
 `localeconv` İşlevi geçerli yerel sayısal biçimlendirme hakkında ayrıntılı bilgi alır. Bu bilgi türü yapısında depolanmış `lconv`. `lconv` Yapısı, yerel tanımlanmış. H, aşağıdaki üyeleri içerir:  
  
 `char *decimal_point, wchar_t *_W_decimal_point`  
 Ondalık nokta karakteri parasal miktarlar için.  
  
 `char *thousands_sep, wchar_t *_W_thousands_sep`  
 Grupları parasal sayıları Ondalık ayırıcının sol tarafındaki basamak ayıran karakter.  
  
 `char *grouping`  
 İşaretçi bir `char`-parasal miktarlarda basamak grubunun boyutunu içeren tamsayı boyuta sahip.  
  
 `char *int_curr_symbol, wchar_t *_W_int_curr_symbol`  
 Geçerli yerel uluslararası para birimi simgesi. İlk üç karakterden belirtin alfabetik uluslararası para birimi simgesini tanımlandığı gibi *para birimi gösterimi ve fon ISO 4217 kodlarını* standart. Dördüncü karakterini (hemen önceki null karakter) uluslararası para birimi simgesini para miktardan ayırır.  
  
 `char *currency_symbol, wchar_t *_W_currency_symbol`  
 Geçerli yerel ayar için yerel para birimi simgesi.  
  
 `char *mon_decimal_point, wchar_t *_W_mon_decimal_point`  
 Para miktarları ondalık nokta karakteri.  
  
 `char *mon_thousands_sep, wchar_t *_W_mon_thousands_sep`  
 Ayırıcı para miktarları ondalık basamak solundaki basamak grupları için.  
  
 `char *mon_grouping`  
 İşaretçi bir `char`-para miktarlarda basamak grubunun boyutunu içeren tamsayı boyuta sahip.  
  
 `char *positive_sign, wchar_t *_W_positive_sign`  
 Negatif olmayan para miktarları oturum belirten dize.  
  
 `char *negative_sign, wchar_t *_W_negative_sign`  
 Negatif para miktarları oturum belirten dize.  
  
 `char int_frac_digits`  
 Uluslararası biçimlendirilmiş para miktarlarda Ondalık ayırıcının sağındaki basamak sayısı.  
  
 `char frac_digits`  
 Biçimlendirilmiş para miktarlarda Ondalık ayırıcının sağındaki basamak sayısı.  
  
 `char p_cs_precedes`  
 Para birimi simgesini değeri negatif olmayan biçimlendirilmiş para miktarı için önceyse 1 olarak ayarlayın. Sembol değeri izliyorsa 0 olarak ayarlayın.  
  
 `char p_sep_by_space`  
 Para birimi simgesini negatif olmayan biçimlendirilmiş para miktarı için değerinden boşlukla ayrılmış ise 1 olarak ayarlayın. Hiçbir alanı ayırma ise 0 olarak ayarlayın.  
  
 `char n_cs_precedes`  
 Para birimi simgesini değeri negatif biçimlendirilmiş para miktar önceyse 1 olarak ayarlayın. Sembol değeri başarılı olursa 0 olarak ayarlayın.  
  
 `char n_sep_by_space`  
 Para birimi simgesini negatif biçimlendirilmiş para miktar değerinden boşlukla ayrılmış ise 1 olarak ayarlayın. Hiçbir alanı ayırma ise 0 olarak ayarlayın.  
  
 `char p_sign_posn`  
 Negatif olmayan biçimlendirilmiş para miktarları pozitif oturum konumu.  
  
 `char n_sign_posn`  
 Negatif biçimlendirilmiş para miktarları pozitif oturum konumu.  
  
Belirtilen, üye olarak dışında `lconv` sahip yapısı `char *` ve `wchar_t *` dizeleri işaretçiler sürümleridir. Eşittir bunları herhangi biri `""` (veya `L""` için `wchar_t *`) sıfır uzunluktaki ya da geçerli yerel ayarı desteklenmiyor. Unutmayın `decimal_point` ve `_W_decimal_point` olan her zaman desteklenen ve sıfır olmayan uzunluğu.  
  
`char` Yapısı üyeleri olan küçük negatif olmayan sayılar, olmayan karakter. Eşittir bunları herhangi biri `CHAR_MAX` geçerli yerel ayarı desteklenmiyor.  
  
Değerlerini `grouping` ve `mon_grouping` aşağıdaki kurallara göre yorumlanır:  
  
- `CHAR_MAX`-Tüm daha fazla gruplandırma gerçekleştirme.  
  
- 0 - her kalan basamak önceki öğesi kullanın.  
  
- *n*-Geçerli grubu oluşturan basamak sayısı. Bir sonraki öğe basamak geçerli Grup önce sonraki grubunun boyutunu belirlemek için incelenir.  
  
Değerleri `int_curr_symbol` aşağıdaki kurallara göre yorumlanır:  
  
-   İlk üç karakterler alfabetik uluslararası para birimi simgesini tanımlandığı gibi belirtin *para birimi gösterimi ve fon ISO 4217 kodlarını* standart.  
  
-   (Null karakteri hemen önceki) Dördüncü karakter uluslararası para birimi simgesini para miktardan ayırır.  
  
Değerleri `p_cs_precedes` ve `n_cs_precedes` aşağıdaki kurallara göre yorumlanır ( `n_cs_precedes` kuralıdır parantez içinde):  
  
- 0 - para birimi simgesini değeri negatif olmayan (negatif) biçimlendirilmiş para değeri izler.  
  
- 1 - değer negatif olmayan (negatif) biçimlendirilmiş para değeri para birimi simgesini koyar.  
  
Değerleri `p_sep_by_space` ve `n_sep_by_space` aşağıdaki kurallara göre yorumlanır ( `n_sep_by_space` kuralıdır parantez içinde):  
  
- 0 - para birimi simgesini değerinden negatif olmayan (negatif) biçimlendirilmiş para değeri boşlukla ayrılır.  
  
- 1 - para birimi simgesini ve değer negatif olmayan (negatif) biçimlendirilmiş para değeri arasında hiçbir alanı ayırma yok.  
  
Değerleri `p_sign_posn` ve `n_sign_posn` aşağıdaki kurallara göre yorumlanır:  
  
- 0 - miktar ve para birimi simgesini parantez içine alın.  
  
- 1 - oturum dize miktar ve para birimi simge önce gelir.  
  
- 2 - oturum dize miktar ve para birimi simgesini izler.  
  
- 3 - oturum dize para birimi simgesini hemen önce gelir.  
  
- 4 - oturum hemen aşağıdaki para birimi simgesini dize.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`localeconv`|\<Locale.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel ayar](../../c-runtime-library/locale.md)   
 [setlocale](../../preprocessor/setlocale.md)   
 [strcoll işlevleri](../../c-runtime-library/strcoll-functions.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)