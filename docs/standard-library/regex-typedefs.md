---
title: "&lt;Regex&gt; tür tanımları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- regex/std::cmatch
- regex/std::cregex_iterator
- regex/std::cregex_token_iterator
- regex/std::csub_match
- regex/std::regex
- regex/std::smatch
- regex/std::sregex_iterator
- regex/std::sregex_token_iterator
- regex/std::ssub_match
- regex/std::wcmatch
- regex/std::wcregex_iterator
- regex/std::wcregex_token_iterator
- regex/std::wcsub_match
- regex/std::wregex
- regex/std::wsmatch
- regex/std::wsregex_iterator
- regex/std::wsregex_token_iterator
- regex/std::wssub_match
dev_langs:
- C++
ms.assetid: e6a69067-106c-4a24-9e08-7c867a3a2260
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a280d441f4ded04f76d82340e4907486f104c49a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ltregexgt-typedefs"></a>&lt;Regex&gt; tür tanımları
||||  
|-|-|-|  
|[cmatch](#cmatch)|[cregex_iterator](#cregex_iterator)|[cregex_token_iterator](#cregex_token_iterator)|  
|[csub_match](#csub_match)|[regex](#regex)|[smatch](#smatch)|  
|[sregex_iterator](#sregex_iterator)|[sregex_token_iterator](#sregex_token_iterator)|[ssub_match](#ssub_match)|  
|[wcmatch](#wcmatch)|[wcregex_iterator](#wcregex_iterator)|[wcregex_token_iterator](#wcregex_token_iterator)|  
|[wcsub_match](#wcsub_match)|[wregex](#wregex)|[wsmatch](#wsmatch)|  
|[wsregex_iterator](#wsregex_iterator)|[wsregex_token_iterator](#wsregex_token_iterator)|[wssub_match](#wssub_match)|  
  
##  <a name="cmatch"></a>  cmatch Typedef  
 Char match_results tanımını yazın.  
  
```  
typedef match_results<const char*> cmatch;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı uzmanlaşması türünü açıklayan [match_results sınıfı](../standard-library/match-results-class.md) yineleyiciler türü için `const char*`.  
  
##  <a name="cregex_iterator"></a>  cregex_iterator Typedef  
 Char regex_iterator tanımını yazın.  
  
```  
typedef regex_iterator<const char*> cregex_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı uzmanlaşması türünü açıklayan [regex_iterator sınıfı](../standard-library/regex-iterator-class.md) yineleyiciler türü için `const char*`.  
  
##  <a name="cregex_token_iterator"></a>  cregex_token_iterator Typedef  
 Char regex_token_iterator için tür tanımı  
  
```  
typedef regex_token_iterator<const char*> cregex_token_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı uzmanlaşması türünü açıklayan [regex_token_iterator sınıfı](../standard-library/regex-token-iterator-class.md) yineleyiciler türü için `const char*`.  
  
##  <a name="csub_match"></a>  csub_match Typedef  
 Char sub_match tanımını yazın.  
  
```  
typedef sub_match<const char*> csub_match;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı uzmanlaşması türünü açıklayan [sub_match sınıfı](../standard-library/sub-match-class.md) yineleyiciler türü için `const char*`.  
  
##  <a name="regex"></a>  Regex Typedef  
 Char basic_regex tanımını yazın.  
  
```  
typedef basic_regex<char> regex;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı uzmanlaşması türünü açıklayan [basic_regex sınıfı](../standard-library/basic-regex-class.md) türündeki öğeler için `char`.  
  
> [!NOTE]
>  Yüksek bit karakterleri öngörülemeyen sonuçlara sahip olmasını `regex`. Değerler 0 ile 127 aralığının dışında tanımsız davranışlara neden olabilir.  
  
##  <a name="smatch"></a>  smatch Typedef  
 Dize match_results tanımını yazın.  
  
```  
typedef match_results<string::const_iterator> smatch;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı uzmanlaşması türünü açıklayan [match_results sınıfı](../standard-library/match-results-class.md) yineleyiciler türü için `string::const_iterator`.  
  
##  <a name="sregex_iterator"></a>  sregex_iterator Typedef  
 Dize regex_iterator tanımını yazın.  
  
```  
typedef regex_iterator<string::const_iterator> sregex_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı uzmanlaşması türünü açıklayan [regex_iterator sınıfı](../standard-library/regex-iterator-class.md) yineleyiciler türü için `string::const_iterator`.  
  
##  <a name="sregex_token_iterator"></a>  sregex_token_iterator Typedef  
 Dize regex_token_iterator tanımını yazın.  
  
```  
typedef regex_token_iterator<string::const_iterator> sregex_token_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı uzmanlaşması türünü açıklayan [regex_token_iterator sınıfı](../standard-library/regex-token-iterator-class.md) yineleyiciler türü için `string::const_iterator`.  
  
##  <a name="ssub_match"></a>  ssub_match Typedef  
 Dize sub_match tanımını yazın.  
  
```  
typedef sub_match<string::const_iterator> ssub_match;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı uzmanlaşması türünü açıklayan [sub_match sınıfı](../standard-library/sub-match-class.md) yineleyiciler türü için `string::const_iterator`.  
  
##  <a name="wcmatch"></a>  wcmatch Typedef  
 Wchar_t match_results tanımını yazın.  
  
```  
typedef match_results<const wchar_t *> wcmatch;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı uzmanlaşması türünü açıklayan [match_results sınıfı](../standard-library/match-results-class.md) yineleyiciler türü için `const wchar_t*`.  
  
##  <a name="wcregex_iterator"></a>  wcregex_iterator Typedef  
 Wchar_t regex_iterator tanımını yazın.  
  
```  
typedef regex_iterator<const wchar_t*> wcregex_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı uzmanlaşması türünü açıklayan [regex_iterator sınıfı](../standard-library/regex-iterator-class.md) yineleyiciler türü için `const wchar_t*`.  
  
##  <a name="wcregex_token_iterator"></a>  wcregex_token_iterator Typedef  
 Wchar_t regex_token_iterator tanımını yazın.  
  
```  
typedef regex_token_iterator<const wchar_t*> wcregex_token_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı uzmanlaşması türünü açıklayan [regex_token_iterator sınıfı](../standard-library/regex-token-iterator-class.md) yineleyiciler türü için `const wchar_t*`.  
  
##  <a name="wcsub_match"></a>  wcsub_match Typedef  
 Wchar_t sub_match tanımını yazın.  
  
```  
typedef sub_match<const wchar_t*> wcsub_match;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı uzmanlaşması türünü açıklayan [sub_match sınıfı](../standard-library/sub-match-class.md) yineleyiciler türü için `const wchar_t*`.  
  
##  <a name="wregex"></a>  wregex Typedef  
 Wchar_t basic_regex tanımını yazın.  
  
```  
typedef basic_regex<wchar_t> wregex;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı uzmanlaşması türünü açıklayan [basic_regex sınıfı](../standard-library/basic-regex-class.md) türündeki öğeler için `wchar_t`.  
  
##  <a name="wsmatch"></a>  wsmatch Typedef  
 Wstring match_results tanımını yazın.  
  
```  
typedef match_results<wstring::const_iterator> wsmatch;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı uzmanlaşması türünü açıklayan [match_results sınıfı](../standard-library/match-results-class.md) yineleyiciler türü için `wstring::const_iterator`.  
  
##  <a name="wsregex_iterator"></a>  wsregex_iterator Typedef  
 Wstring regex_iterator tanımını yazın.  
  
```  
typedef regex_iterator<wstring::const_iterator> wsregex_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı uzmanlaşması türünü açıklayan [regex_iterator sınıfı](../standard-library/regex-iterator-class.md) yineleyiciler türü için `wstring::const_iterator`.  
  
##  <a name="wsregex_token_iterator"></a>  wsregex_token_iterator Typedef  
 Wstring regex_token_iterator tanımını yazın.  
  
```  
typedef regex_token_iterator<wstring::const_iterator> wsregex_token_iterator;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı uzmanlaşması türünü açıklayan [regex_token_iterator sınıfı](../standard-library/regex-token-iterator-class.md) yineleyiciler türü için `wstring::const_iterator`.  
  
##  <a name="wssub_match"></a>  wssub_match Typedef  
 Wstring sub_match tanımını yazın.  
  
```  
typedef sub_match<wstring::const_iterator> wssub_match;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı uzmanlaşması türünü açıklayan [sub_match sınıfı](../standard-library/sub-match-class.md) yineleyiciler türü için `wstring::const_iterator`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[\<regex>](../standard-library/regex.md)  
[regex_constants Sınıfı](../standard-library/regex-constants-class.md)  
[regex_error Sınıfı](../standard-library/regex-error-class.md)  
[\<Regex > işlevleri](../standard-library/regex-functions.md)  
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)  
[\<Regex > işleçleri](../standard-library/regex-operators.md)  
[regex_token_iterator Sınıfı](../standard-library/regex-token-iterator-class.md)  
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)  
