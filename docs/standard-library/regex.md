---
title: '&lt;Regex&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- <regex>
dev_langs:
- C++
helpviewer_keywords:
- regex header
ms.assetid: 5dd4ef74-6063-4dbc-b692-1960bb736f0b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c586cf909ce07f17dfdba08005d1efd8489db869
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ltregexgt"></a>&lt;regex&gt;
Ayrıştırmak için bir şablon sınıfı tanımlar [normal ifadeler (C++)](../standard-library/regular-expressions-cpp.md)ve birkaç şablon sınıfları ve işlevleri metin bir normal ifade nesnesi için eşleşme aramak için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#include <regex>  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir normal ifade nesnesi oluşturmak için şablon sınıfını kullanmak [basic_regex sınıfı](../standard-library/basic-regex-class.md) veya kendi özelleştirmeleri [regex](../standard-library/regex-typedefs.md#regex) ve [wregex](../standard-library/regex-typedefs.md#wregex), söz dizimi bayraklarını ile birlikte tür [regex_constants::syntax_option_type](../standard-library/regex-constants-class.md#syntax_option_type).  
  
 Metin bir normal ifade nesnesi için eşleşme aramak için şablon işlevleri kullanmak [regex_match](../standard-library/regex-functions.md#regex_match) ve [regex_search](../standard-library/regex-functions.md#regex_search), eşleşme bayrakları türü ile birlikte [regex_constants::match_ flag_type](../standard-library/regex-constants-class.md#match_flag_type). Şablon sınıfı kullanarak bu işlevler sonuçlar döndürebilir [match_results sınıfı](../standard-library/match-results-class.md) ve kendi özelleştirmeleri [cmatch](../standard-library/regex-typedefs.md#cmatch), [wcmatch](../standard-library/regex-typedefs.md#wcmatch), [smatch](../standard-library/regex-typedefs.md#smatch), ve [wsmatch](../standard-library/regex-typedefs.md#wsmatch), Şablon sınıfı ile birlikte [sub_match sınıfı](../standard-library/sub-match-class.md) ve kendi özelleştirmeleri [csub_match](../standard-library/regex-typedefs.md#csub_match), [wcsub_ eşleşen](../standard-library/regex-typedefs.md#wcsub_match), [ssub_match](../standard-library/regex-typedefs.md#ssub_match), ve [wssub_match](../standard-library/regex-typedefs.md#wssub_match).  
  
 Normal ifade nesnesi eşleşen metni değiştirmek için şablon işlevi kullanın [regex_replace](../standard-library/regex-functions.md#regex_replace), eşleşme bayrakları türü ile birlikte [regex_constants::match_flag_type](../standard-library/regex-constants-class.md#match_flag_type).  
  
 Normal ifade nesnesi birden çok eşleşme ile yinelemek için şablon sınıfları kullanan [regex_iterator sınıfı](../standard-library/regex-iterator-class.md) ve [regex_token_iterator sınıfı](../standard-library/regex-token-iterator-class.md) veya kendi özelleştirmeleri [ cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator), [sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator), [wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator), [wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator), [cregex_token_iterator ](../standard-library/regex-typedefs.md#cregex_token_iterator), [sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator), [wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator), veya [wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator), eşleşme bayrakları türü ile birlikte [regex_constants::match_flag_type](../standard-library/regex-constants-class.md#match_flag_type).  
  
 Normal ifadeler dilbilgisi ayrıntılarını değiştirmek için normal ifade nitelikler uygulayan bir sınıf yazma.  
  
### <a name="classes"></a>Sınıflar  
  
|||  
|-|-|  
|[basic_regex](../standard-library/basic-regex-class.md)|Normal bir ifadeyi sarar.|  
|[match_results](../standard-library/match-results-class.md)|Bir dizi submatches tutar.|  
|[regex_constants](../standard-library/regex-constants-class.md)|Ayrı tutma sabitleri getirilebilir.|  
|[regex_error](../standard-library/regex-error-class.md)|Bozuk bir normal ifade bildirir.|  
|[regex_iterator](../standard-library/regex-iterator-class.md)|Eşleşme sonuçları arasında yineler.|  
|[regex_traits](../standard-library/regex-traits-class.md)|Eşleşen öğelerin özelliklerini açıklar.|  
|[regex_traits\<char>](../standard-library/regex-traits-char-class.md)|Özelliklerini açıklayan `char` eşleme.|  
|[regex_traits<wchar_t>](../standard-library/regex-traits-wchar-t-class.md)|Özelliklerini açıklayan `wchar_t` eşleme.|  
|[regex_token_iterator](../standard-library/regex-token-iterator-class.md)|Submatches yineler.|  
|[sub_match](../standard-library/sub-match-class.md)|Bir submatch açıklar.|  
  
### <a name="type-definitions"></a>Tür tanımları  
  
|||  
|-|-|  
|[cmatch](../standard-library/regex-typedefs.md#cmatch)|Tür tanımı için `char` `match_results`.|  
|[cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator)|Tür tanımı için `char` `regex_iterator`.|  
|[cregex_token_iterator](../standard-library/regex-typedefs.md#cregex_token_iterator)|Tür tanımı için `char` `regex_token_iterator`.|  
|[csub_match](../standard-library/regex-typedefs.md#csub_match)|Tür tanımı için `char` `sub_match`.|  
|[regex](../standard-library/regex-typedefs.md#regex)|Tür tanımı için `char` `basic_regex`.|  
|[smatch](../standard-library/regex-typedefs.md#smatch)|Tür tanımı için `string` `match_results`.|  
|[sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator)|Tür tanımı için `string` `regex_iterator`.|  
|[sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator)|Tür tanımı için `string` `regex_token_iterator`.|  
|[ssub_match](../standard-library/regex-typedefs.md#ssub_match)|Tür tanımı için `string` `sub_match`.|  
|[wcmatch](../standard-library/regex-typedefs.md#wcmatch)|Tür tanımı için `wchar_t` `match_results`.|  
|[wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator)|Tür tanımı için `wchar_t` `regex_iterator`.|  
|[wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator)|Tür tanımı için `wchar_t` `regex_token_iterator`.|  
|[wcsub_match](../standard-library/regex-typedefs.md#wcsub_match)|Tür tanımı için `wchar_t` `sub_match`.|  
|[wregex](../standard-library/regex-typedefs.md#wregex)|Tür tanımı için `wchar_t` `basic_regex`.|  
|[wsmatch](../standard-library/regex-typedefs.md#wsmatch)|Tür tanımı için `wstring` `match_results`.|  
|[wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator)|Tür tanımı için `wstring` `regex_iterator`.|  
|[wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator)|Tür tanımı için `wstring` `regex_token_iterator`.|  
|[wssub_match](../standard-library/regex-typedefs.md#wssub_match)|Tür tanımı için `wstring` `sub_match`.|  
  
### <a name="functions"></a>İşlevler  
  
|||  
|-|-|  
|[regex_match](../standard-library/regex-functions.md#regex_match)|Tam olarak normal ifadeyle eşleşir.|  
|[regex_replace](../standard-library/regex-functions.md#regex_replace)|Normal ifadeler değiştirir eşleşmedi.|  
|[regex_search](../standard-library/regex-functions.md#regex_search)|Normal ifade eşleştirmesi arar.|  
|[Değiştirme](../standard-library/regex-functions.md#swap)|Değiştirir `basic_regex` veya `match_results` nesneleri.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[operator==](../standard-library/regex-operators.md#op_eq_eq)|Çeşitli nesneleri, eşit karşılaştırması.|  
|[operator!=](../standard-library/regex-operators.md#op_neq)|Karşılaştırma nesnelerin çeşitli eşit değil.|  
|[operator <](../standard-library/regex-operators.md#op_lt)|Çeşitli nesnelerin karşılaştırma küçüktür.|  
|[işleci\<=](../standard-library/regex-operators.md#op_gt_eq)|Karşılaştırma çeşitli nesnelerin küçüktür veya eşittir.|  
|[operator>](../standard-library/regex-operators.md#op_gt)|Karşılaştırma nesnelerin çeşitli büyüktür.|  
|[operator>=](../standard-library/regex-operators.md#op_gt_eq)|Büyük veya ona eşit olmak üzere çeşitli nesneleri karşılaştırması.|  
|[işleç <<](../standard-library/regex-operators.md#op_lt_lt)|Ekler bir `sub_match` bir akış.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[Normal İfadeler (C++)](../standard-library/regular-expressions-cpp.md)  
[regex_constants Sınıfı](../standard-library/regex-constants-class.md)  
[regex_error Sınıfı](../standard-library/regex-error-class.md)  
[\<Regex > işlevleri](../standard-library/regex-functions.md)  
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)  
[\<Regex > işleçleri](../standard-library/regex-operators.md)  
[regex_token_iterator Sınıfı](../standard-library/regex-token-iterator-class.md)  
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)  
[\<Regex > tür tanımları](../standard-library/regex-typedefs.md)  



