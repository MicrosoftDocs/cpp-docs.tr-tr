---
title: '&lt;Normal ifade&gt;'
ms.date: 11/04/2016
f1_keywords:
- <regex>
helpviewer_keywords:
- regex header
ms.assetid: 5dd4ef74-6063-4dbc-b692-1960bb736f0b
ms.openlocfilehash: 0a4728008130119ed9a01334efb2fea2a4ac0639
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50627350"
---
# <a name="ltregexgt"></a>&lt;Normal ifade&gt;

Ayrıştırmak için bir şablon sınıfı tanımlar [normal ifadeler (C++)](../standard-library/regular-expressions-cpp.md), birkaç şablon sınıf ve eşleşen bir normal ifade nesnesi için metin aranacak işlev.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <regex>
```

## <a name="remarks"></a>Açıklamalar

Bir normal ifade nesnesi oluşturmak için Şablon sınıfı kullanın [basic_regex sınıfı](../standard-library/basic-regex-class.md) veya kendi uzmanlıkları [regex](../standard-library/regex-typedefs.md#regex) ve [wchar_t](../standard-library/regex-typedefs.md#wregex)söz dizimi bayraklarını birlikte tür [regex_constants::syntax_option_type](../standard-library/regex-constants-class.md#syntax_option_type).

Metin bir normal ifade nesnesine eşleşme aramak için şablon işlevleri kullanmak [regex_match](../standard-library/regex-functions.md#regex_match) ve [regex_search](../standard-library/regex-functions.md#regex_search)tür eşleşme bayrağı ile birlikte [regex_constants::match_ flag_type](../standard-library/regex-constants-class.md#match_flag_type). Bu işlevler, Şablon sınıfı kullanarak sonuçları döndürmek [match_results sınıfı](../standard-library/match-results-class.md) ve kendi uzmanlıkları [cmatch](../standard-library/regex-typedefs.md#cmatch), [wcmatch](../standard-library/regex-typedefs.md#wcmatch), [smatch](../standard-library/regex-typedefs.md#smatch), ve [wsmatch](../standard-library/regex-typedefs.md#wsmatch)Şablon sınıfı ile birlikte [sub_match sınıfı](../standard-library/sub-match-class.md) ve kendi uzmanlıkları [csub_match](../standard-library/regex-typedefs.md#csub_match), [wcsub_ eşleşen](../standard-library/regex-typedefs.md#wcsub_match), [ssub_match](../standard-library/regex-typedefs.md#ssub_match), ve [wssub_match](../standard-library/regex-typedefs.md#wssub_match).

Bir normal ifade nesnesi eşleşen metni değiştirmek için şablon işlevini [regex_replace](../standard-library/regex-functions.md#regex_replace)tür eşleşme bayrağı ile birlikte [regex_constants::match_flag_type](../standard-library/regex-constants-class.md#match_flag_type).

Bir normal ifade nesnesi birden çok eşleşme ile yinelemek için şablon sınıfları kullanın [regex_iterator sınıfı](../standard-library/regex-iterator-class.md) ve [regex_token_iterator sınıfı](../standard-library/regex-token-iterator-class.md) veya kendi uzmanlıkları [ cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator), [sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator), [wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator), [wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator), [cregex_token_iterator ](../standard-library/regex-typedefs.md#cregex_token_iterator), [sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator), [wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator), veya [wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator)tür eşleşme bayrağı ile birlikte [regex_constants::match_flag_type](../standard-library/regex-constants-class.md#match_flag_type).

Normal ifade dilbilgisi ayrıntılarını değiştirmek için normal ifade niteliklerini uygulayan bir sınıf yazın.

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[basic_regex](../standard-library/basic-regex-class.md)|Normal bir ifadeyi sarar.|
|[match_results](../standard-library/match-results-class.md)|Bir dizi alt eşleşmelerin tutar.|
|[regex_constants](../standard-library/regex-constants-class.md)|Çeşitli sabitleri tutar.|
|[regex_error](../standard-library/regex-error-class.md)|Hatalı bir normal ifade bildirir.|
|[regex_iterator](../standard-library/regex-iterator-class.md)|Eşleştirme sonuçları yinelenir.|
|[regex_traits](../standard-library/regex-traits-class.md)|Eşleşen öğelerin özelliklerini açıklar.|
|[regex_traits\<char >](../standard-library/regex-traits-char-class.md)|Özellikleri açıklanmaktadır **char** eşlemek için.|
|[regex_traits<wchar_t>](../standard-library/regex-traits-wchar-t-class.md)|Özellikleri açıklanmaktadır **wchar_t** eşlemek için.|
|[regex_token_iterator](../standard-library/regex-token-iterator-class.md)|Alt eşleşmeleri yinelenir.|
|[sub_match](../standard-library/sub-match-class.md)|Bir alt eşleşme açıklar.|

### <a name="type-definitions"></a>Tür tanımları

|||
|-|-|
|[cmatch](../standard-library/regex-typedefs.md#cmatch)|Tür tanımına için **char** `match_results`.|
|[cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator)|Tür tanımına için **char** `regex_iterator`.|
|[cregex_token_iterator](../standard-library/regex-typedefs.md#cregex_token_iterator)|Tür tanımına için **char** `regex_token_iterator`.|
|[csub_match](../standard-library/regex-typedefs.md#csub_match)|Tür tanımına için **char** `sub_match`.|
|[Normal ifade](../standard-library/regex-typedefs.md#regex)|Tür tanımına için **char** `basic_regex`.|
|[smatch](../standard-library/regex-typedefs.md#smatch)|Tür tanımına için `string` `match_results`.|
|[sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator)|Tür tanımına için `string` `regex_iterator`.|
|[sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator)|Tür tanımına için `string` `regex_token_iterator`.|
|[ssub_match](../standard-library/regex-typedefs.md#ssub_match)|Tür tanımına için `string` `sub_match`.|
|[wcmatch](../standard-library/regex-typedefs.md#wcmatch)|Tür tanımına için **wchar_t** `match_results`.|
|[wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator)|Tür tanımına için **wchar_t** `regex_iterator`.|
|[wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator)|Tür tanımına için **wchar_t** `regex_token_iterator`.|
|[wcsub_match](../standard-library/regex-typedefs.md#wcsub_match)|Tür tanımına için **wchar_t** `sub_match`.|
|[wchar_t](../standard-library/regex-typedefs.md#wregex)|Tür tanımına için **wchar_t** `basic_regex`.|
|[wsmatch](../standard-library/regex-typedefs.md#wsmatch)|Tür tanımına için `wstring` `match_results`.|
|[wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator)|Tür tanımına için `wstring` `regex_iterator`.|
|[wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator)|Tür tanımına için `wstring` `regex_token_iterator`.|
|[wssub_match](../standard-library/regex-typedefs.md#wssub_match)|Tür tanımına için `wstring` `sub_match`.|

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[regex_match](../standard-library/regex-functions.md#regex_match)|Tam olarak normal bir ifadeyle eşleşiyor.|
|[regex_replace](../standard-library/regex-functions.md#regex_replace)|Normal ifadeler değiştirir eşleşti.|
|[regex_search](../standard-library/regex-functions.md#regex_search)|Bir normal ifade eşleştirmesi arar.|
|[değiştirme](../standard-library/regex-functions.md#swap)|Değiştirir `basic_regex` veya `match_results` nesneleri.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator==](../standard-library/regex-operators.md#op_eq_eq)|Çeşitli nesneler eşit karşılaştırması.|
|[operator!=](../standard-library/regex-operators.md#op_neq)|Çeşitli nesneler eşit değildir karşılaştırma.|
|[işleç <](../standard-library/regex-operators.md#op_lt)|Karşılaştırma çeşitli nesnelerin küçüktür.|
|[İşleci\<=](../standard-library/regex-operators.md#op_gt_eq)|Karşılaştırma çeşitli nesnelerin küçüktür veya eşittir.|
|[operator >](../standard-library/regex-operators.md#op_gt)|Çeşitli nesneleri, büyüktür karşılaştırması.|
|[operator>=](../standard-library/regex-operators.md#op_gt_eq)|Büyük veya buna eşit olmak üzere çeşitli nesneleri karşılaştırması.|
|[işleç <<](../standard-library/regex-operators.md#op_lt_lt)|Ekler bir `sub_match` bir akış.|

## <a name="see-also"></a>Ayrıca bkz.

[Normal İfadeler (C++)](../standard-library/regular-expressions-cpp.md)<br/>
[regex_constants Sınıfı](../standard-library/regex-constants-class.md)<br/>
[regex_error Sınıfı](../standard-library/regex-error-class.md)<br/>
[\<Regex > işlevleri](../standard-library/regex-functions.md)<br/>
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)<br/>
[\<Regex > işleçleri](../standard-library/regex-operators.md)<br/>
[regex_token_iterator Sınıfı](../standard-library/regex-token-iterator-class.md)<br/>
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)<br/>
[\<Regex > tür tanımları](../standard-library/regex-typedefs.md)<br/>
