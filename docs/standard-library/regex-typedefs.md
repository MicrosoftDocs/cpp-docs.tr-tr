---
title: '&lt;Regex&gt; tür tanımları'
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
ms.openlocfilehash: 82067819d144cbbdd2790e92aa6de5a1e7c0386a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451457"
---
# <a name="ltregexgt-typedefs"></a>&lt;Regex&gt; tür tanımları

||||
|-|-|-|
|[cmatch](#cmatch)|[cregex_iterator](#cregex_iterator)|[cregex_token_iterator](#cregex_token_iterator)|
|[csub_match](#csub_match)|[Regex](#regex)|[smatch](#smatch)|
|[sregex_iterator](#sregex_iterator)|[sregex_token_iterator](#sregex_token_iterator)|[ssub_match](#ssub_match)|
|[wcmatch](#wcmatch)|[wcregex_iterator](#wcregex_iterator)|[wcregex_token_iterator](#wcregex_token_iterator)|
|[wcsub_match](#wcsub_match)|[wregex](#wregex)|[wsmatch](#wsmatch)|
|[wsregex_iterator](#wsregex_iterator)|[wsregex_token_iterator](#wsregex_token_iterator)|[wssub_match](#wssub_match)|

## <a name="cmatch"></a>cmatch typedef

Char match_results için tür tanımı.

```cpp
typedef match_results<const char*> cmatch;
```

### <a name="remarks"></a>Açıklamalar

Türü yineleyiciler `const char*`için şablon sınıfı [match_results sınıfının](../standard-library/match-results-class.md) bir özelleştirmesi tanımlar.

## <a name="cregex_iterator"></a>cregex_iterator typedef

Char regex_iterator için tür tanımı.

```cpp
typedef regex_iterator<const char*> cregex_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü yineleyiciler `const char*`için şablon sınıfı [regex_iterator sınıfının](../standard-library/regex-iterator-class.md) bir özelleştirmesi tanımlar.

## <a name="cregex_token_iterator"></a>cregex_token_iterator typedef

Char regex_token_iterator için tür tanımı

```cpp
typedef regex_token_iterator<const char*> cregex_token_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü yineleyiciler `const char*`için şablon sınıfı [regex_token_iterator sınıfının](../standard-library/regex-token-iterator-class.md) bir özelleştirmesi tanımlar.

## <a name="csub_match"></a>csub_match typedef

Char sub_match için tür tanımı.

```cpp
typedef sub_match<const char*> csub_match;
```

### <a name="remarks"></a>Açıklamalar

Türü yineleyiciler `const char*`için şablon sınıfı [sub_match sınıfının](../standard-library/sub-match-class.md) bir özelleştirmesi tanımlar.

## <a name="regex"></a>Regex typedef

Char basic_regex için tür tanımı.

```cpp
typedef basic_regex<char> regex;
```

### <a name="remarks"></a>Açıklamalar

Tür, **char**türündeki öğeler için şablon sınıfı [basic_regex sınıfının](../standard-library/basic-regex-class.md) bir özelleştirmesi tanımlar.

> [!NOTE]
> Yüksek bit karakterler ile `regex`öngörülemeyen sonuçlara sahip olacaktır. 0 ile 127 aralığının dışındaki değerler tanımsız davranışa neden olabilir.

## <a name="smatch"></a>smatch typedef

Match_results dizesi için tanım yazın.

```cpp
typedef match_results<string::const_iterator> smatch;
```

### <a name="remarks"></a>Açıklamalar

Türü yineleyiciler `string::const_iterator`için şablon sınıfı [match_results sınıfının](../standard-library/match-results-class.md) bir özelleştirmesi tanımlar.

## <a name="sregex_iterator"></a>sregex_iterator typedef

Regex_iterator dizesi için tanım yazın.

```cpp
typedef regex_iterator<string::const_iterator> sregex_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü yineleyiciler `string::const_iterator`için şablon sınıfı [regex_iterator sınıfının](../standard-library/regex-iterator-class.md) bir özelleştirmesi tanımlar.

## <a name="sregex_token_iterator"></a>sregex_token_iterator typedef

Regex_token_iterator dizesi için tanım yazın.

```cpp
typedef regex_token_iterator<string::const_iterator> sregex_token_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü yineleyiciler `string::const_iterator`için şablon sınıfı [regex_token_iterator sınıfının](../standard-library/regex-token-iterator-class.md) bir özelleştirmesi tanımlar.

## <a name="ssub_match"></a>ssub_match typedef

Sub_match dizesi için tanım yazın.

```cpp
typedef sub_match<string::const_iterator> ssub_match;
```

### <a name="remarks"></a>Açıklamalar

Türü yineleyiciler `string::const_iterator`için şablon sınıfı [sub_match sınıfının](../standard-library/sub-match-class.md) bir özelleştirmesi tanımlar.

## <a name="wcmatch"></a>wcmatch typedef

Wchar_t match_results için tanım yazın.

```cpp
typedef match_results<const wchar_t *> wcmatch;
```

### <a name="remarks"></a>Açıklamalar

Türü yineleyiciler `const wchar_t*`için şablon sınıfı [match_results sınıfının](../standard-library/match-results-class.md) bir özelleştirmesi tanımlar.

## <a name="wcregex_iterator"></a>wcregex_iterator typedef

Wchar_t regex_iterator için tanım yazın.

```cpp
typedef regex_iterator<const wchar_t*> wcregex_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü yineleyiciler `const wchar_t*`için şablon sınıfı [regex_iterator sınıfının](../standard-library/regex-iterator-class.md) bir özelleştirmesi tanımlar.

## <a name="wcregex_token_iterator"></a>wcregex_token_iterator typedef

Wchar_t regex_token_iterator için tanım yazın.

```cpp
typedef regex_token_iterator<const wchar_t*> wcregex_token_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü yineleyiciler `const wchar_t*`için şablon sınıfı [regex_token_iterator sınıfının](../standard-library/regex-token-iterator-class.md) bir özelleştirmesi tanımlar.

## <a name="wcsub_match"></a>wcsub_match typedef

Wchar_t sub_match için tanım yazın.

```cpp
typedef sub_match<const wchar_t*> wcsub_match;
```

### <a name="remarks"></a>Açıklamalar

Türü yineleyiciler `const wchar_t*`için şablon sınıfı [sub_match sınıfının](../standard-library/sub-match-class.md) bir özelleştirmesi tanımlar.

## <a name="wregex"></a>wregex Typedef

Wchar_t basic_regex için tanım yazın.

```cpp
typedef basic_regex<wchar_t> wregex;
```

### <a name="remarks"></a>Açıklamalar

Tür, **wchar_t**türü öğeler için şablon sınıfı [basic_regex sınıfının](../standard-library/basic-regex-class.md) bir özelleştirmesi tanımlar.

## <a name="wsmatch"></a>wsmatch typedef

Wstring match_results için tür tanımı.

```cpp
typedef match_results<wstring::const_iterator> wsmatch;
```

### <a name="remarks"></a>Açıklamalar

Türü yineleyiciler `wstring::const_iterator`için şablon sınıfı [match_results sınıfının](../standard-library/match-results-class.md) bir özelleştirmesi tanımlar.

## <a name="wsregex_iterator"></a>wsregex_iterator typedef

Wstring regex_iterator için tür tanımı.

```cpp
typedef regex_iterator<wstring::const_iterator> wsregex_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü yineleyiciler `wstring::const_iterator`için şablon sınıfı [regex_iterator sınıfının](../standard-library/regex-iterator-class.md) bir özelleştirmesi tanımlar.

## <a name="wsregex_token_iterator"></a>wsregex_token_iterator typedef

Wstring regex_token_iterator için tür tanımı.

```cpp
typedef regex_token_iterator<wstring::const_iterator> wsregex_token_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü yineleyiciler `wstring::const_iterator`için şablon sınıfı [regex_token_iterator sınıfının](../standard-library/regex-token-iterator-class.md) bir özelleştirmesi tanımlar.

## <a name="wssub_match"></a>wssub_match typedef

Wstring sub_match için tür tanımı.

```cpp
typedef sub_match<wstring::const_iterator> wssub_match;
```

### <a name="remarks"></a>Açıklamalar

Türü yineleyiciler `wstring::const_iterator`için şablon sınıfı [sub_match sınıfının](../standard-library/sub-match-class.md) bir özelleştirmesi tanımlar.

## <a name="see-also"></a>Ayrıca bkz.

[\<Regex >](../standard-library/regex.md)\
[regex_constants sınıfı](../standard-library/regex-constants-class.md)\
[regex_error sınıfı](../standard-library/regex-error-class.md)\
[\<Regex > işlevleri](../standard-library/regex-functions.md)\
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)\
[\<Regex > işleçleri](../standard-library/regex-operators.md)\
[regex_token_iterator sınıfı](../standard-library/regex-token-iterator-class.md)\
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)
