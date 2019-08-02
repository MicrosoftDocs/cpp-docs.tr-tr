---
title: '&lt;Regex&gt;'
ms.date: 11/04/2016
f1_keywords:
- <regex>
helpviewer_keywords:
- regex header
ms.assetid: 5dd4ef74-6063-4dbc-b692-1960bb736f0b
ms.openlocfilehash: 3e3f3b49b3672042e0376e7738a8cf8924e1c2a8
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451442"
---
# <a name="ltregexgt"></a>&lt;Regex&gt;

Normal [ifadeleri (C++)](../standard-library/regular-expressions-cpp.md)ayrıştırmak için bir şablon sınıfı tanımlar ve metni bir normal ifade nesnesiyle eşleşecek şekilde aramak için birkaç şablon sınıfı ve işlevi tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <regex>
```

## <a name="remarks"></a>Açıklamalar

Bir normal ifade nesnesi oluşturmak için, [regex_constants:: syntax_option_type](../standard-library/regex-constants-class.md#syntax_option_type)türünde sözdizimi bayraklarıyla birlikte [basic_regex sınıfını](../standard-library/basic-regex-class.md) veya kendi specialpplication, [Regex](../standard-library/regex-typedefs.md#regex) ve [wregex](../standard-library/regex-typedefs.md#wregex)olan şablon sınıfını kullanın.

Bir normal ifade nesnesiyle eşleşen metinleri aramak için, [regex_match](../standard-library/regex-functions.md#regex_match) ve [regex_search](../standard-library/regex-functions.md#regex_search)şablon işlevlerini [regex_constants:: match_flag_type](../standard-library/regex-constants-class.md#match_flag_type)türünde Match bayraklarıyla birlikte kullanın. Bu işlevler, [Match_results sınıfını](../standard-library/match-results-class.md) ve onun specialmelerini, [cmatch](../standard-library/regex-typedefs.md#cmatch), [](../standard-library/sub-match-class.md) [wcmatch](../standard-library/regex-typedefs.md#wcmatch), [smatch](../standard-library/regex-typedefs.md#smatch)ve [wsmatch](../standard-library/regex-typedefs.md#wsmatch)şablon sınıfı ile birlikte kullanarak sonuçları döndürür. specialmeler, [csub_match](../standard-library/regex-typedefs.md#csub_match), [wcsub_match](../standard-library/regex-typedefs.md#wcsub_match), [ssub_match](../standard-library/regex-typedefs.md#ssub_match)ve [wssub_match](../standard-library/regex-typedefs.md#wssub_match).

Bir normal ifade nesnesiyle eşleşen metni değiştirmek için, [regex_constants:: match_flag_type](../standard-library/regex-constants-class.md#match_flag_type)türünde Match bayraklarıyla birlikte [regex_replace](../standard-library/regex-functions.md#regex_replace)şablon işlevini kullanın.

Bir normal ifade nesnesinin birden çok eşleştirmelerinde yinelemek için, [Regex_iterator Class](../standard-library/regex-iterator-class.md) and [regex_token_iterator Class](../standard-library/regex-token-iterator-class.md) şablon sınıflarını veya uzmanlıklardan birini, [cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator), [sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator), [wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator), [wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator), [cregex_token_iterator](../standard-library/regex-typedefs.md#cregex_token_iterator), [sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator), [wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator)veya [wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator), regex_ tür eşleştirme bayraklarıyla birlikte [ sabitler:: match_flag_type](../standard-library/regex-constants-class.md#match_flag_type).

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
|[regex_traits\<char >](../standard-library/regex-traits-char-class.md)|Eşleştirme için **char** 'ın özelliklerini açıklar.|
|[regex_traits<wchar_t>](../standard-library/regex-traits-wchar-t-class.md)|Eşleşen **wchar_t** 'nin özelliklerini açıklar.|
|[regex_token_iterator](../standard-library/regex-token-iterator-class.md)|Alt eşleşmeler arasında yinelenir.|
|[sub_match](../standard-library/sub-match-class.md)|Bir alt eşleşme tanımlar.|

### <a name="type-definitions"></a>Tür Tanımları

|||
|-|-|
|[cmatch](../standard-library/regex-typedefs.md#cmatch)|Char`match_results`için tür tanımı.|
|[cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator)|Char`regex_iterator`için tür tanımı.|
|[cregex_token_iterator](../standard-library/regex-typedefs.md#cregex_token_iterator)|Char`regex_token_iterator`için tür tanımı.|
|[csub_match](../standard-library/regex-typedefs.md#csub_match)|Char`sub_match`için tür tanımı.|
|[Regex](../standard-library/regex-typedefs.md#regex)|Char`basic_regex`için tür tanımı.|
|[smatch](../standard-library/regex-typedefs.md#smatch)|`string` İçin`match_results`tür tanımı.|
|[sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator)|`string` İçin`regex_iterator`tür tanımı.|
|[sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator)|`string` İçin`regex_token_iterator`tür tanımı.|
|[ssub_match](../standard-library/regex-typedefs.md#ssub_match)|`string` İçin`sub_match`tür tanımı.|
|[wcmatch](../standard-library/regex-typedefs.md#wcmatch)|Wchar_t`match_results`için tanım yazın.|
|[wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator)|Wchar_t`regex_iterator`için tanım yazın.|
|[wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator)|Wchar_t`regex_token_iterator`için tanım yazın.|
|[wcsub_match](../standard-library/regex-typedefs.md#wcsub_match)|Wchar_t`sub_match`için tanım yazın.|
|[wregex](../standard-library/regex-typedefs.md#wregex)|Wchar_t`basic_regex`için tanım yazın.|
|[wsmatch](../standard-library/regex-typedefs.md#wsmatch)|`wstring` İçin`match_results`tür tanımı.|
|[wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator)|`wstring` İçin`regex_iterator`tür tanımı.|
|[wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator)|`wstring` İçin`regex_token_iterator`tür tanımı.|
|[wssub_match](../standard-library/regex-typedefs.md#wssub_match)|`wstring` İçin`sub_match`tür tanımı.|

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[regex_match](../standard-library/regex-functions.md#regex_match)|Bir normal ifadeyle tam olarak eşleşir.|
|[regex_replace](../standard-library/regex-functions.md#regex_replace)|Eşleşen normal ifadeleri değiştirir.|
|[regex_search](../standard-library/regex-functions.md#regex_search)|Normal ifade eşleşmesi arar.|
|[Kur](../standard-library/regex-functions.md#swap)|Nesneleri `basic_regex` değiştirir `match_results` veya değiştirir.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator==](../standard-library/regex-operators.md#op_eq_eq)|Farklı nesnelerin karşılaştırması, eşittir.|
|[operator!=](../standard-library/regex-operators.md#op_neq)|Eşit değil, çeşitli nesnelerin karşılaştırması.|
|[işleç <](../standard-library/regex-operators.md#op_lt)|Farklı nesnelerin karşılaştırması, küçüktür.|
|[işlecinde\<=](../standard-library/regex-operators.md#op_gt_eq)|Çeşitli nesnelerin karşılaştırması, küçüktür veya eşittir.|
|[işleç >](../standard-library/regex-operators.md#op_gt)|Çeşitli nesnelerin karşılaştırması, büyüktür.|
|[operator>=](../standard-library/regex-operators.md#op_gt_eq)|Daha büyük veya eşit birçok nesne karşılaştırması.|
|[işleç < <](../standard-library/regex-operators.md#op_lt_lt)|Bir akışa `sub_match` bir ekler.|

## <a name="see-also"></a>Ayrıca bkz.

[Normal Ifadeler (C++)](../standard-library/regular-expressions-cpp.md)\
[regex_constants sınıfı](../standard-library/regex-constants-class.md)\
[regex_error sınıfı](../standard-library/regex-error-class.md)\
[\<Regex > işlevleri](../standard-library/regex-functions.md)\
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)\
[\<Regex > işleçleri](../standard-library/regex-operators.md)\
[regex_token_iterator sınıfı](../standard-library/regex-token-iterator-class.md)\
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)\
[\<tür tanımları > Regex](../standard-library/regex-typedefs.md)
