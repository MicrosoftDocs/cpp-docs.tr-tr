---
title: '&lt;Regex&gt; typedefs | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b32031103e6e6d9922fdb3b0fc3a0d95e5eb280c
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38957047"
---
# <a name="ltregexgt-typedefs"></a>&lt;Regex&gt; tür tanımları

||||
|-|-|-|
|[cmatch](#cmatch)|[cregex_iterator](#cregex_iterator)|[cregex_token_iterator](#cregex_token_iterator)|
|[csub_match](#csub_match)|[Normal ifade](#regex)|[smatch](#smatch)|
|[sregex_iterator](#sregex_iterator)|[sregex_token_iterator](#sregex_token_iterator)|[ssub_match](#ssub_match)|
|[wcmatch](#wcmatch)|[wcregex_iterator](#wcregex_iterator)|[wcregex_token_iterator](#wcregex_token_iterator)|
|[wcsub_match](#wcsub_match)|[wchar_t](#wregex)|[wsmatch](#wsmatch)|
|[wsregex_iterator](#wsregex_iterator)|[wsregex_token_iterator](#wsregex_token_iterator)|[wssub_match](#wssub_match)|

## <a name="cmatch"></a>  Typedef cmatch

Char match_results için tanım yazın.

```cpp
typedef match_results<const char*> cmatch;
```

### <a name="remarks"></a>Açıklamalar

Türü tanımlayan Şablon sınıfı bir alt uzmanlaşması [match_results sınıfı](../standard-library/match-results-class.md) yineleyicileri türü için `const char*`.

## <a name="cregex_iterator"></a>  Typedef cregex_iterator

Char regex_iterator için tanım yazın.

```cpp
typedef regex_iterator<const char*> cregex_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü tanımlayan Şablon sınıfı bir alt uzmanlaşması [regex_iterator sınıfı](../standard-library/regex-iterator-class.md) yineleyicileri türü için `const char*`.

## <a name="cregex_token_iterator"></a>  Typedef cregex_token_iterator

Char regex_token_iterator için tür tanımı

```cpp
typedef regex_token_iterator<const char*> cregex_token_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü tanımlayan Şablon sınıfı bir alt uzmanlaşması [regex_token_iterator sınıfı](../standard-library/regex-token-iterator-class.md) yineleyicileri türü için `const char*`.

## <a name="csub_match"></a>  Typedef csub_match

Char sub_match için tanım yazın.

```cpp
typedef sub_match<const char*> csub_match;
```

### <a name="remarks"></a>Açıklamalar

Türü tanımlayan Şablon sınıfı bir alt uzmanlaşması [sub_match sınıfı](../standard-library/sub-match-class.md) yineleyicileri türü için `const char*`.

## <a name="regex"></a>  Regex tür tanımı

Char basic_regex için tanım yazın.

```cpp
typedef basic_regex<char> regex;
```

### <a name="remarks"></a>Açıklamalar

Türü tanımlayan Şablon sınıfı bir alt uzmanlaşması [basic_regex sınıfı](../standard-library/basic-regex-class.md) türü öğeler için **char**.

> [!NOTE]
> Yüksek bit karakterleri ile öngörülemeyen sonuçlara sahip olacak `regex`. Değerler 0 ile 127 aralığının dışında tanımsız davranışlara neden.

## <a name="smatch"></a>  Typedef smatch

Dize match_results için tanım yazın.

```cpp
typedef match_results<string::const_iterator> smatch;
```

### <a name="remarks"></a>Açıklamalar

Türü tanımlayan Şablon sınıfı bir alt uzmanlaşması [match_results sınıfı](../standard-library/match-results-class.md) yineleyicileri türü için `string::const_iterator`.

## <a name="sregex_iterator"></a>  Typedef sregex_iterator

Dize regex_iterator için tanım yazın.

```cpp
typedef regex_iterator<string::const_iterator> sregex_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü tanımlayan Şablon sınıfı bir alt uzmanlaşması [regex_iterator sınıfı](../standard-library/regex-iterator-class.md) yineleyicileri türü için `string::const_iterator`.

## <a name="sregex_token_iterator"></a>  Typedef sregex_token_iterator

Dize regex_token_iterator için tanım yazın.

```cpp
typedef regex_token_iterator<string::const_iterator> sregex_token_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü tanımlayan Şablon sınıfı bir alt uzmanlaşması [regex_token_iterator sınıfı](../standard-library/regex-token-iterator-class.md) yineleyicileri türü için `string::const_iterator`.

## <a name="ssub_match"></a>  Typedef ssub_match

Dize sub_match için tanım yazın.

```cpp
typedef sub_match<string::const_iterator> ssub_match;
```

### <a name="remarks"></a>Açıklamalar

Türü tanımlayan Şablon sınıfı bir alt uzmanlaşması [sub_match sınıfı](../standard-library/sub-match-class.md) yineleyicileri türü için `string::const_iterator`.

## <a name="wcmatch"></a>  Typedef wcmatch

Wchar_t match_results için tanım yazın.

```cpp
typedef match_results<const wchar_t *> wcmatch;
```

### <a name="remarks"></a>Açıklamalar

Türü tanımlayan Şablon sınıfı bir alt uzmanlaşması [match_results sınıfı](../standard-library/match-results-class.md) yineleyicileri türü için `const wchar_t*`.

## <a name="wcregex_iterator"></a>  Typedef wcregex_iterator

Wchar_t regex_iterator için tanım yazın.

```cpp
typedef regex_iterator<const wchar_t*> wcregex_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü tanımlayan Şablon sınıfı bir alt uzmanlaşması [regex_iterator sınıfı](../standard-library/regex-iterator-class.md) yineleyicileri türü için `const wchar_t*`.

## <a name="wcregex_token_iterator"></a>  Typedef wcregex_token_iterator

Wchar_t regex_token_iterator için tanım yazın.

```cpp
typedef regex_token_iterator<const wchar_t*> wcregex_token_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü tanımlayan Şablon sınıfı bir alt uzmanlaşması [regex_token_iterator sınıfı](../standard-library/regex-token-iterator-class.md) yineleyicileri türü için `const wchar_t*`.

## <a name="wcsub_match"></a>  Typedef wcsub_match

Wchar_t sub_match için tanım yazın.

```cpp
typedef sub_match<const wchar_t*> wcsub_match;
```

### <a name="remarks"></a>Açıklamalar

Türü tanımlayan Şablon sınıfı bir alt uzmanlaşması [sub_match sınıfı](../standard-library/sub-match-class.md) yineleyicileri türü için `const wchar_t*`.

## <a name="wregex"></a>  wchar_t tür tanımı

Wchar_t basic_regex için tanım yazın.

```cpp
typedef basic_regex<wchar_t> wregex;
```

### <a name="remarks"></a>Açıklamalar

Türü tanımlayan Şablon sınıfı bir alt uzmanlaşması [basic_regex sınıfı](../standard-library/basic-regex-class.md) türü öğeler için **wchar_t**.

## <a name="wsmatch"></a>  Typedef wsmatch

Wstring match_results için tanım yazın.

```cpp
typedef match_results<wstring::const_iterator> wsmatch;
```

### <a name="remarks"></a>Açıklamalar

Türü tanımlayan Şablon sınıfı bir alt uzmanlaşması [match_results sınıfı](../standard-library/match-results-class.md) yineleyicileri türü için `wstring::const_iterator`.

## <a name="wsregex_iterator"></a>  Typedef wsregex_iterator

Wstring regex_iterator için tanım yazın.

```cpp
typedef regex_iterator<wstring::const_iterator> wsregex_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü tanımlayan Şablon sınıfı bir alt uzmanlaşması [regex_iterator sınıfı](../standard-library/regex-iterator-class.md) yineleyicileri türü için `wstring::const_iterator`.

## <a name="wsregex_token_iterator"></a>  Typedef wsregex_token_iterator

Wstring regex_token_iterator için tanım yazın.

```cpp
typedef regex_token_iterator<wstring::const_iterator> wsregex_token_iterator;
```

### <a name="remarks"></a>Açıklamalar

Türü tanımlayan Şablon sınıfı bir alt uzmanlaşması [regex_token_iterator sınıfı](../standard-library/regex-token-iterator-class.md) yineleyicileri türü için `wstring::const_iterator`.

## <a name="wssub_match"></a>  Typedef wssub_match

Wstring sub_match için tanım yazın.

```cpp
typedef sub_match<wstring::const_iterator> wssub_match;
```

### <a name="remarks"></a>Açıklamalar

Türü tanımlayan Şablon sınıfı bir alt uzmanlaşması [sub_match sınıfı](../standard-library/sub-match-class.md) yineleyicileri türü için `wstring::const_iterator`.

## <a name="see-also"></a>Ayrıca bkz.

[\<Regex >](../standard-library/regex.md)<br/>
[regex_constants Sınıfı](../standard-library/regex-constants-class.md)<br/>
[regex_error Sınıfı](../standard-library/regex-error-class.md)<br/>
[\<Regex > işlevleri](../standard-library/regex-functions.md)<br/>
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)<br/>
[\<Regex > işleçleri](../standard-library/regex-operators.md)<br/>
[regex_token_iterator Sınıfı](../standard-library/regex-token-iterator-class.md)<br/>
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)<br/>
