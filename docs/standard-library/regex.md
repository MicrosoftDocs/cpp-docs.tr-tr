---
description: 'Daha fazla bilgi edinin: &lt; Regex&gt;'
title: '&lt;Regex&gt;'
ms.date: 11/04/2016
f1_keywords:
- <regex>
helpviewer_keywords:
- regex header
ms.assetid: 5dd4ef74-6063-4dbc-b692-1960bb736f0b
ms.openlocfilehash: 33eefd09c74731b36d3a8f104e2380944da2f43f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243776"
---
# <a name="ltregexgt"></a>&lt;Regex&gt;

Normal [ifadeleri (C++)](../standard-library/regular-expressions-cpp.md)ayrıştırmak için bir sınıf şablonu ve bir normal ifade nesnesiyle eşleşen metinleri aramak için çeşitli sınıf şablonları ve işlevleri tanımlar.

## <a name="syntax"></a>Syntax

```cpp
#include <regex>
```

## <a name="remarks"></a>Açıklamalar

Bir normal ifade nesnesi oluşturmak için, [regex_constants:: syntax_option_type](../standard-library/regex-constants-class.md#syntax_option_type)türünde sözdizimi bayraklarıyla birlikte [basic_regex sınıfını](../standard-library/basic-regex-class.md) veya kendi uzmanlarından birini, [Regex](../standard-library/regex-typedefs.md#regex) ve [wregex](../standard-library/regex-typedefs.md#wregex)öğesini kullanın.

Bir normal ifade nesnesiyle eşleşen metinleri aramak için, [regex_match](../standard-library/regex-functions.md#regex_match) şablon işlevlerini ve [regex_search](../standard-library/regex-functions.md#regex_search) [regex_constants:: match_flag_type](../standard-library/regex-constants-class.md#match_flag_type)türü eşleşme bayraklarıyla birlikte kullanın. Bu işlevler, sınıf şablonu [Sub_match sınıfı](../standard-library/sub-match-class.md) ve kendi uzmanlık, [csub_match](../standard-library/regex-typedefs.md#csub_match), [wcsub_match](../standard-library/regex-typedefs.md#wcsub_match), [Ssub_match](../standard-library/regex-typedefs.md#ssub_match)ve [wssub_match](../standard-library/regex-typedefs.md#wssub_match)gibi sınıf şablonu [match_results sınıfını](../standard-library/match-results-class.md) ve onun specialmelerini, [cmatch](../standard-library/regex-typedefs.md#cmatch), [wcmatch](../standard-library/regex-typedefs.md#wcmatch), [smatch](../standard-library/regex-typedefs.md#smatch)ve [wsmatch](../standard-library/regex-typedefs.md#wsmatch)kullanarak sonuçları döndürür.

Bir normal ifade nesnesiyle eşleşen metni değiştirmek için, [regex_replace](../standard-library/regex-functions.md#regex_replace)şablon işlevini, [regex_constants:: match_flag_type](../standard-library/regex-constants-class.md#match_flag_type)türündeki eşleşme bayraklarıyla birlikte kullanın.

Bir normal ifade nesnesinin birden çok eşleştirmesinden yinelemek için, sınıf şablonları [regex_iterator](../standard-library/regex-iterator-class.md) sınıf ve [regex_token_iterator sınıfı](../standard-library/regex-token-iterator-class.md) ya da kendi uzmanlarından biri olan [cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator), [sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator), [wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator), [wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator), [cregex_token_iterator](../standard-library/regex-typedefs.md#cregex_token_iterator), [sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator), [wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator)veya [wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator), [regex_constants:: match_flag_type](../standard-library/regex-constants-class.md#match_flag_type)türündeki eşleşme bayraklarıyla birlikte kullanın.

Normal ifadelerin dilbilgisinin ayrıntılarını değiştirmek için normal ifade niteliklerini uygulayan bir sınıf yazın.

### <a name="classes"></a>Sınıflar

|Sınıf|Açıklama|
|-|-|
|[basic_regex](../standard-library/basic-regex-class.md)|Normal bir ifadeyi sarar.|
|[match_results](../standard-library/match-results-class.md)|Bir dizi alt eşleşme tutar.|
|[regex_constants](../standard-library/regex-constants-class.md)|Assıralanan sabitleri tutar.|
|[regex_error](../standard-library/regex-error-class.md)|Hatalı bir normal ifade bildiriyor.|
|[regex_iterator](../standard-library/regex-iterator-class.md)|Eşleştirme sonuçlarıyla yinelenir.|
|[regex_traits](../standard-library/regex-traits-class.md)|Eşleme için öğelerin özelliklerini açıklar.|
|[regex_traits\<char>](../standard-library/regex-traits-char-class.md)|Eşleme özelliklerini açıklar **`char`** .|
|[regex_traits<wchar_t>](../standard-library/regex-traits-wchar-t-class.md)|Eşleme özelliklerini açıklar **`wchar_t`** .|
|[regex_token_iterator](../standard-library/regex-token-iterator-class.md)|Alt eşleşmeler arasında yinelenir.|
|[sub_match](../standard-library/sub-match-class.md)|Bir alt eşleşme tanımlar.|

### <a name="type-definitions"></a>Tür Tanımları

|Ad|Açıklama|
|-|-|
|[cmatch](../standard-library/regex-typedefs.md#cmatch)|İçin tür tanımı **`char`** `match_results` .|
|[cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator)|İçin tür tanımı **`char`** `regex_iterator` .|
|[cregex_token_iterator](../standard-library/regex-typedefs.md#cregex_token_iterator)|İçin tür tanımı **`char`** `regex_token_iterator` .|
|[csub_match](../standard-library/regex-typedefs.md#csub_match)|İçin tür tanımı **`char`** `sub_match` .|
|[Regex](../standard-library/regex-typedefs.md#regex)|İçin tür tanımı **`char`** `basic_regex` .|
|[smatch](../standard-library/regex-typedefs.md#smatch)|İçin tür tanımı `string` `match_results` .|
|[sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator)|İçin tür tanımı `string` `regex_iterator` .|
|[sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator)|İçin tür tanımı `string` `regex_token_iterator` .|
|[ssub_match](../standard-library/regex-typedefs.md#ssub_match)|İçin tür tanımı `string` `sub_match` .|
|[wcmatch](../standard-library/regex-typedefs.md#wcmatch)|İçin tür tanımı **`wchar_t`** `match_results` .|
|[wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator)|İçin tür tanımı **`wchar_t`** `regex_iterator` .|
|[wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator)|İçin tür tanımı **`wchar_t`** `regex_token_iterator` .|
|[wcsub_match](../standard-library/regex-typedefs.md#wcsub_match)|İçin tür tanımı **`wchar_t`** `sub_match` .|
|[wregex](../standard-library/regex-typedefs.md#wregex)|İçin tür tanımı **`wchar_t`** `basic_regex` .|
|[wsmatch](../standard-library/regex-typedefs.md#wsmatch)|İçin tür tanımı `wstring` `match_results` .|
|[wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator)|İçin tür tanımı `wstring` `regex_iterator` .|
|[wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator)|İçin tür tanımı `wstring` `regex_token_iterator` .|
|[wssub_match](../standard-library/regex-typedefs.md#wssub_match)|İçin tür tanımı `wstring` `sub_match` .|

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[regex_match](../standard-library/regex-functions.md#regex_match)|Bir normal ifadeyle tam olarak eşleşir.|
|[regex_replace](../standard-library/regex-functions.md#regex_replace)|Eşleşen normal ifadeleri değiştirir.|
|[regex_search](../standard-library/regex-functions.md#regex_search)|Normal ifade eşleşmesi arar.|
|[Kur](../standard-library/regex-functions.md#swap)|`basic_regex`Nesneleri değiştirir veya değiştirir `match_results` .|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç = =](../standard-library/regex-operators.md#op_eq_eq)|Farklı nesnelerin karşılaştırması, eşittir.|
|[işleç! =](../standard-library/regex-operators.md#op_neq)|Eşit değil, çeşitli nesnelerin karşılaştırması.|
|[işleç<](../standard-library/regex-operators.md#op_lt)|Farklı nesnelerin karşılaştırması, küçüktür.|
|[işlecinde\<=](../standard-library/regex-operators.md#op_gt_eq)|Çeşitli nesnelerin karşılaştırması, küçüktür veya eşittir.|
|[işleç>](../standard-library/regex-operators.md#op_gt)|Çeşitli nesnelerin karşılaştırması, büyüktür.|
|[işleç>=](../standard-library/regex-operators.md#op_gt_eq)|Daha büyük veya eşit birçok nesne karşılaştırması.|
|[işleç<<](../standard-library/regex-operators.md#op_lt_lt)|Bir akışa bir ekler `sub_match` .|

## <a name="see-also"></a>Ayrıca bkz.

[Normal Ifadeler (C++)](../standard-library/regular-expressions-cpp.md)\
[regex_constants sınıfı](../standard-library/regex-constants-class.md)\
[regex_error sınıfı](../standard-library/regex-error-class.md)\
[\<regex> lerdir](../standard-library/regex-functions.md)\
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)\
[\<regex> işletmenlerinin](../standard-library/regex-operators.md)\
[regex_token_iterator sınıfı](../standard-library/regex-token-iterator-class.md)\
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)\
[\<regex> tür tanımları](../standard-library/regex-typedefs.md)
