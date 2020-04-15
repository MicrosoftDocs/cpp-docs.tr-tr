---
title: '&lt;regex&gt; typedefs'
ms.date: 11/04/2016
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
ms.assetid: e6a69067-106c-4a24-9e08-7c867a3a2260
ms.openlocfilehash: 5dbda2df4877da7594dd633e9f203a3780b4adb1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368554"
---
# <a name="ltregexgt-typedefs"></a>&lt;regex&gt; typedefs

||||
|-|-|-|
|[cmatch](#cmatch)|[cregex_iterator](#cregex_iterator)|[cregex_token_iterator](#cregex_token_iterator)|
|[csub_match](#csub_match)|[Regex](#regex)|[smatch](#smatch)|
|[sregex_iterator](#sregex_iterator)|[sregex_token_iterator](#sregex_token_iterator)|[ssub_match](#ssub_match)|
|[wcmatch](#wcmatch)|[wcregex_iterator](#wcregex_iterator)|[wcregex_token_iterator](#wcregex_token_iterator)|
|[wcsub_match](#wcsub_match)|[wregex](#wregex)|[wsmatch](#wsmatch)|
|[wsregex_iterator](#wsregex_iterator)|[wsregex_token_iterator](#wsregex_token_iterator)|[wssub_match](#wssub_match)|

## <a name="cmatch-typedef"></a><a name="cmatch"></a>cmatch Typedef

Char match_results için yazı tanımı.

```cpp
typedef match_results<const char*> cmatch;
```

### <a name="remarks"></a>Açıklamalar

Tür, sınıf şablonu [match_results sınıfının](../standard-library/match-results-class.md) tür `const char*`yineleyicileri için özelleştirilmesini açıklar.

## <a name="cregex_iterator-typedef"></a><a name="cregex_iterator"></a>cregex_iterator Typedef

Char regex_iterator için yazı tanımı.

```cpp
typedef regex_iterator<const char*> cregex_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, sınıf şablonu [regex_iterator](../standard-library/regex-iterator-class.md) sınıf `const char*`yineleyicileri için bir uzmanlık açıklar.

## <a name="cregex_token_iterator-typedef"></a><a name="cregex_token_iterator"></a>cregex_token_iterator Typedef

Char regex_token_iterator için tür tanımı

```cpp
typedef regex_token_iterator<const char*> cregex_token_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, sınıf şablonu [regex_token_iterator sınıfının](../standard-library/regex-token-iterator-class.md) tür `const char*`yineleyicileri için özelleştirilmesini açıklar.

## <a name="csub_match-typedef"></a><a name="csub_match"></a>csub_match Typedef

Char sub_match için yazı tanımı.

```cpp
typedef sub_match<const char*> csub_match;
```

### <a name="remarks"></a>Açıklamalar

Tür, sınıf şablonu [sub_match sınıfının](../standard-library/sub-match-class.md) tür `const char*`yineleyicileri için özelleştirilmesini açıklar.

## <a name="regex-typedef"></a><a name="regex"></a>regex Typedef

Char basic_regex için yazı tanımı.

```cpp
typedef basic_regex<char> regex;
```

### <a name="remarks"></a>Açıklamalar

Tür, sınıf şablonu [basic_regex sınıf](../standard-library/basic-regex-class.md) türü **char**öğeleri için bir uzmanlık açıklar.

> [!NOTE]
> Yüksek bit karakterleri ile `regex`öngörülemeyen sonuçlar olacaktır. 0 ile 127 aralığı dışındaki değerler tanımlanmamış davranışlara neden olabilir.

## <a name="smatch-typedef"></a><a name="smatch"></a>smatch Typedef

Dize match_results için yazı tanımı.

```cpp
typedef match_results<string::const_iterator> smatch;
```

### <a name="remarks"></a>Açıklamalar

Tür, sınıf şablonu [match_results sınıfının](../standard-library/match-results-class.md) tür `string::const_iterator`yineleyicileri için özelleştirilmesini açıklar.

## <a name="sregex_iterator-typedef"></a><a name="sregex_iterator"></a>sregex_iterator Typedef

Dize regex_iterator için yazı tanımı.

```cpp
typedef regex_iterator<string::const_iterator> sregex_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, sınıf şablonu [regex_iterator](../standard-library/regex-iterator-class.md) sınıf `string::const_iterator`yineleyicileri için bir uzmanlık açıklar.

## <a name="sregex_token_iterator-typedef"></a><a name="sregex_token_iterator"></a>sregex_token_iterator Typedef

Dize regex_token_iterator için yazı tanımı.

```cpp
typedef regex_token_iterator<string::const_iterator> sregex_token_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, sınıf şablonu [regex_token_iterator sınıfının](../standard-library/regex-token-iterator-class.md) tür `string::const_iterator`yineleyicileri için özelleştirilmesini açıklar.

## <a name="ssub_match-typedef"></a><a name="ssub_match"></a>ssub_match Typedef

Dize sub_match için yazı tanımı.

```cpp
typedef sub_match<string::const_iterator> ssub_match;
```

### <a name="remarks"></a>Açıklamalar

Tür, sınıf şablonu [sub_match sınıfının](../standard-library/sub-match-class.md) tür `string::const_iterator`yineleyicileri için özelleştirilmesini açıklar.

## <a name="wcmatch-typedef"></a><a name="wcmatch"></a>wcmatch Typedef

wchar_t match_results için yazı tanımı.

```cpp
typedef match_results<const wchar_t *> wcmatch;
```

### <a name="remarks"></a>Açıklamalar

Tür, sınıf şablonu [match_results sınıfının](../standard-library/match-results-class.md) tür `const wchar_t*`yineleyicileri için özelleştirilmesini açıklar.

## <a name="wcregex_iterator-typedef"></a><a name="wcregex_iterator"></a>wcregex_iterator Typedef

wchar_t regex_iterator için yazı tanımı.

```cpp
typedef regex_iterator<const wchar_t*> wcregex_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, sınıf şablonu [regex_iterator](../standard-library/regex-iterator-class.md) sınıf `const wchar_t*`yineleyicileri için bir uzmanlık açıklar.

## <a name="wcregex_token_iterator-typedef"></a><a name="wcregex_token_iterator"></a>wcregex_token_iterator Typedef

wchar_t regex_token_iterator için tür tanımı.

```cpp
typedef regex_token_iterator<const wchar_t*> wcregex_token_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, sınıf şablonu [regex_token_iterator sınıfının](../standard-library/regex-token-iterator-class.md) tür `const wchar_t*`yineleyicileri için özelleştirilmesini açıklar.

## <a name="wcsub_match-typedef"></a><a name="wcsub_match"></a>wcsub_match Typedef

wchar_t sub_match için yazı tanımı.

```cpp
typedef sub_match<const wchar_t*> wcsub_match;
```

### <a name="remarks"></a>Açıklamalar

Tür, sınıf şablonu [sub_match sınıfının](../standard-library/sub-match-class.md) tür `const wchar_t*`yineleyicileri için özelleştirilmesini açıklar.

## <a name="wregex-typedef"></a><a name="wregex"></a>wregex Typedef

wchar_t basic_regex için yazı tanımı.

```cpp
typedef basic_regex<wchar_t> wregex;
```

### <a name="remarks"></a>Açıklamalar

Tür, sınıf şablonu [basic_regex Sınıf'ın](../standard-library/basic-regex-class.md) **wchar_t**türü öğeleri için uzmanlaşmasını açıklar.

## <a name="wsmatch-typedef"></a><a name="wsmatch"></a>wsmatch Typedef

Wstring match_results için yazı tanımı.

```cpp
typedef match_results<wstring::const_iterator> wsmatch;
```

### <a name="remarks"></a>Açıklamalar

Tür, sınıf şablonu [match_results sınıfının](../standard-library/match-results-class.md) tür `wstring::const_iterator`yineleyicileri için özelleştirilmesini açıklar.

## <a name="wsregex_iterator-typedef"></a><a name="wsregex_iterator"></a>wsregex_iterator Typedef

Wstring regex_iterator için yazı tanımı.

```cpp
typedef regex_iterator<wstring::const_iterator> wsregex_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, sınıf şablonu [regex_iterator](../standard-library/regex-iterator-class.md) sınıf `wstring::const_iterator`yineleyicileri için bir uzmanlık açıklar.

## <a name="wsregex_token_iterator-typedef"></a><a name="wsregex_token_iterator"></a>wsregex_token_iterator Typedef

Wstring regex_token_iterator için yazı tanımı.

```cpp
typedef regex_token_iterator<wstring::const_iterator> wsregex_token_iterator;
```

### <a name="remarks"></a>Açıklamalar

Tür, sınıf şablonu [regex_token_iterator sınıfının](../standard-library/regex-token-iterator-class.md) tür `wstring::const_iterator`yineleyicileri için özelleştirilmesini açıklar.

## <a name="wssub_match-typedef"></a><a name="wssub_match"></a>wssub_match Typedef

Wstring sub_match için yazı tanımı.

```cpp
typedef sub_match<wstring::const_iterator> wssub_match;
```

### <a name="remarks"></a>Açıklamalar

Tür, sınıf şablonu [sub_match sınıfının](../standard-library/sub-match-class.md) tür `wstring::const_iterator`yineleyicileri için özelleştirilmesini açıklar.

## <a name="see-also"></a>Ayrıca bkz.

[\<regex>](../standard-library/regex.md)\
[regex_constants Sınıfı](../standard-library/regex-constants-class.md)\
[regex_error Sınıfı](../standard-library/regex-error-class.md)\
[\<regex> fonksiyonları](../standard-library/regex-functions.md)\
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)\
[\<regex> operatörleri](../standard-library/regex-operators.md)\
[regex_token_iterator Sınıfı](../standard-library/regex-token-iterator-class.md)\
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)
