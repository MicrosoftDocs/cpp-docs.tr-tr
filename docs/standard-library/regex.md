---
title: '&lt;regex &gt;'
ms.date: 11/04/2016
f1_keywords:
- <regex>
helpviewer_keywords:
- regex header
ms.assetid: 5dd4ef74-6063-4dbc-b692-1960bb736f0b
ms.openlocfilehash: 69adc738d5af3de5997e01c0f861400eb61f1712
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72686597"
---
# <a name="ltregexgt"></a>&lt;regex &gt;

Normal [ifadeleri (C++)](../standard-library/regular-expressions-cpp.md)ayrıştırmak için bir sınıf şablonu ve bir normal ifade nesnesi ile eşleşen metinleri aramak için birkaç sınıf şablonu ve işlevi tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <regex>
```

## <a name="remarks"></a>Açıklamalar

Bir normal ifade nesnesi oluşturmak için, [regex_constants:: syntax_option_type](../standard-library/regex-constants-class.md#syntax_option_type)türünde sözdizimi bayraklarıyla birlikte, [basic_regex sınıfını](../standard-library/basic-regex-class.md) veya kendi specialpplication, [Regex](../standard-library/regex-typedefs.md#regex) ve [wregex](../standard-library/regex-typedefs.md#wregex)olan sınıf şablonu kullanın.

Bir normal ifade nesnesiyle eşleşen metinleri aramak için, [regex_match](../standard-library/regex-functions.md#regex_match) ve [regex_search](../standard-library/regex-functions.md#regex_search)şablon işlevlerini [regex_constants:: match_flag_type](../standard-library/regex-constants-class.md#match_flag_type)türünde Match bayraklarıyla birlikte kullanın. Bu işlevler, sınıf şablonu [Sub_match sınıfı](../standard-library/sub-match-class.md) ve onun [match_results](../standard-library/match-results-class.md) sınıfını ve onun specialmelerini, [cmatch](../standard-library/regex-typedefs.md#cmatch), [wcmatch](../standard-library/regex-typedefs.md#wcmatch), [smatch](../standard-library/regex-typedefs.md#smatch)ve [wsmatch](../standard-library/regex-typedefs.md#wsmatch)sınıf şablonunu kullanarak sonuçları döndürür. specialmeler, [csub_match](../standard-library/regex-typedefs.md#csub_match), [wcsub_match](../standard-library/regex-typedefs.md#wcsub_match), [ssub_match](../standard-library/regex-typedefs.md#ssub_match)ve [wssub_match](../standard-library/regex-typedefs.md#wssub_match).

Bir normal ifade nesnesiyle eşleşen metni değiştirmek için, [regex_constants:: match_flag_type](../standard-library/regex-constants-class.md#match_flag_type)türünde Match bayraklarıyla birlikte [regex_replace](../standard-library/regex-functions.md#regex_replace)şablon işlevini kullanın.

Bir normal ifade nesnesinin birden çok eşleştirmelerinde yinelemek için, [Regex_iterator Class](../standard-library/regex-iterator-class.md) and [regex_token_iterator Class](../standard-library/regex-token-iterator-class.md) veya uzmanlıklarıyla, [cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator), [sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator), [sınıf şablonları kullanın wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator), [wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator), [cregex_token_iterator](../standard-library/regex-typedefs.md#cregex_token_iterator), [sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator), [wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator)veya [wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator), regex_ tür eşleştirme bayraklarıyla birlikte [ sabitler:: match_flag_type](../standard-library/regex-constants-class.md#match_flag_type).

Normal ifadelerin dilbilgisinin ayrıntılarını değiştirmek için normal ifade niteliklerini uygulayan bir sınıf yazın.

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[basic_regex](../standard-library/basic-regex-class.md)|Normal bir ifadeyi sarar.|
|[match_results](../standard-library/match-results-class.md)|Bir dizi alt eşleşme tutar.|
|[regex_constants](../standard-library/regex-constants-class.md)|Assıralanan sabitleri tutar.|
|[regex_error](../standard-library/regex-error-class.md)|Hatalı bir normal ifade bildiriyor.|
|[regex_iterator](../standard-library/regex-iterator-class.md)|Eşleştirme sonuçlarıyla yinelenir.|
|[regex_traits](../standard-library/regex-traits-class.md)|Eşleme için öğelerin özelliklerini açıklar.|
|[regex_traits \<char >](../standard-library/regex-traits-char-class.md)|Eşleştirme için **char** 'ın özelliklerini açıklar.|
|[regex_traits < wchar_t >](../standard-library/regex-traits-wchar-t-class.md)|Eşleşen **wchar_t** 'nin özelliklerini açıklar.|
|[regex_token_iterator](../standard-library/regex-token-iterator-class.md)|Alt eşleşmeler arasında yinelenir.|
|[sub_match](../standard-library/sub-match-class.md)|Bir alt eşleşme tanımlar.|

### <a name="type-definitions"></a>Tür Tanımları

|||
|-|-|
|[cmatch](../standard-library/regex-typedefs.md#cmatch)|**Char** `match_results` için tür tanımı.|
|[cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator)|**Char** `regex_iterator` için tür tanımı.|
|[cregex_token_iterator](../standard-library/regex-typedefs.md#cregex_token_iterator)|**Char** `regex_token_iterator` için tür tanımı.|
|[csub_match](../standard-library/regex-typedefs.md#csub_match)|**Char** `sub_match` için tür tanımı.|
|[Regex](../standard-library/regex-typedefs.md#regex)|**Char** `basic_regex` için tür tanımı.|
|[smatch](../standard-library/regex-typedefs.md#smatch)|@No__t_0 `match_results` için tanım yazın.|
|[sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator)|@No__t_0 `regex_iterator` için tanım yazın.|
|[sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator)|@No__t_0 `regex_token_iterator` için tanım yazın.|
|[ssub_match](../standard-library/regex-typedefs.md#ssub_match)|@No__t_0 `sub_match` için tanım yazın.|
|[wcmatch](../standard-library/regex-typedefs.md#wcmatch)|**Wchar_t** `match_results` için tanım yazın.|
|[wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator)|**Wchar_t** `regex_iterator` için tanım yazın.|
|[wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator)|**Wchar_t** `regex_token_iterator` için tanım yazın.|
|[wcsub_match](../standard-library/regex-typedefs.md#wcsub_match)|**Wchar_t** `sub_match` için tanım yazın.|
|[wregex](../standard-library/regex-typedefs.md#wregex)|**Wchar_t** `basic_regex` için tanım yazın.|
|[wsmatch](../standard-library/regex-typedefs.md#wsmatch)|@No__t_0 `match_results` için tanım yazın.|
|[wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator)|@No__t_0 `regex_iterator` için tanım yazın.|
|[wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator)|@No__t_0 `regex_token_iterator` için tanım yazın.|
|[wssub_match](../standard-library/regex-typedefs.md#wssub_match)|@No__t_0 `sub_match` için tanım yazın.|

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[regex_match](../standard-library/regex-functions.md#regex_match)|Bir normal ifadeyle tam olarak eşleşir.|
|[regex_replace](../standard-library/regex-functions.md#regex_replace)|Eşleşen normal ifadeleri değiştirir.|
|[regex_search](../standard-library/regex-functions.md#regex_search)|Normal ifade eşleşmesi arar.|
|[Kur](../standard-library/regex-functions.md#swap)|@No__t_0 veya `match_results` nesnelerini değiştirir.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç = =](../standard-library/regex-operators.md#op_eq_eq)|Farklı nesnelerin karşılaştırması, eşittir.|
|[operator!=](../standard-library/regex-operators.md#op_neq)|Eşit değil, çeşitli nesnelerin karşılaştırması.|
|[işleç <](../standard-library/regex-operators.md#op_lt)|Farklı nesnelerin karşılaştırması, küçüktür.|
|[işleç \< =](../standard-library/regex-operators.md#op_gt_eq)|Çeşitli nesnelerin karşılaştırması, küçüktür veya eşittir.|
|[işleç >](../standard-library/regex-operators.md#op_gt)|Çeşitli nesnelerin karşılaştırması, büyüktür.|
|[operator>=](../standard-library/regex-operators.md#op_gt_eq)|Daha büyük veya eşit birçok nesne karşılaştırması.|
|[işleç < <](../standard-library/regex-operators.md#op_lt_lt)|Bir akışa `sub_match` ekler.|

## <a name="see-also"></a>Ayrıca bkz.

[Normal ifadeler (C++)](../standard-library/regular-expressions-cpp.md) \
[Regex_constants sınıfı](../standard-library/regex-constants-class.md) \
[Regex_error sınıfı](../standard-library/regex-error-class.md) \
[\<regex > işlevleri](../standard-library/regex-functions.md) \
[Regex_iterator sınıfı](../standard-library/regex-iterator-class.md) \
[\<regex > işleçleri](../standard-library/regex-operators.md) \
[Regex_token_iterator sınıfı](../standard-library/regex-token-iterator-class.md) \
[regex_traits sınıfı](../standard-library/regex-traits-class.md) \
[\<regex > tür tanımları](../standard-library/regex-typedefs.md)
