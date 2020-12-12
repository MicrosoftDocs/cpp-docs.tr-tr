---
description: 'Hakkında daha fazla bilgi edinin: regex_error sınıfı'
title: regex_error Sınıfı
ms.date: 09/10/2018
f1_keywords:
- regex/std::regex_error
- regex/std::regex_error::code
helpviewer_keywords:
- regex_error class
ms.assetid: 3333a1a3-ca6f-4612-84b2-1b4c7e3db5a4
ms.openlocfilehash: a6e2ace44c7463cbe43d000d3dabb9cf9f7d6676
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250510"
---
# <a name="regex_error-class"></a>regex_error Sınıfı

Hatalı bir basic_regex nesne bildirir.

## <a name="syntax"></a>Syntax

```cpp
class regex_error
: public std::runtime_error
```

## <a name="remarks"></a>Açıklamalar

Sınıfı, bir nesnesinin oluşturulması veya kullanımı sırasında hata raporlamak için oluşturulan bir özel durum nesnesini açıklar `basic_regex` .

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[regex_error](#regex_error)|Nesnesini oluşturur.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[kodudur](#code)|Hata kodunu döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<regex>

**Ad alanı:** std

## <a name="example"></a>Örnek

```cpp
// std__regex__regex_error.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
    {
    std::regex_error paren(std::regex_constants::error_paren);

    try
        {
        std::regex rx("(a");
        }
    catch (const std::regex_error& rerr)
        {
        std::cout << "regex error: "
            << (rerr.code() == paren.code() ? "unbalanced parentheses" : "")
            << std::endl;
        }
    catch (...)
        {
        std::cout << "unknown exception" << std::endl;
        }

    return (0);
    }
```

```Output
regex error: unbalanced parentheses
```

## <a name="regex_errorcode"></a><a name="code"></a> regex_error:: Code

Hata kodunu döndürür.

```cpp
regex_constants::error_code code() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, nesnenin oluşturucusuna geçirilen değeri döndürür.

## <a name="regex_errorregex_error"></a><a name="regex_error"></a> regex_error:: regex_error

Nesnesini oluşturur.

```cpp
regex_error(regex_constants::error_code error);
```

### <a name="parameters"></a>Parametreler

*hatayla*\
Hata kodu.

### <a name="remarks"></a>Açıklamalar

Oluşturucu, değer *hatasını* tutan bir nesne oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

[\<regex>](../standard-library/regex.md)\
[regex_constants sınıfı](../standard-library/regex-constants-class.md)\
[\<regex> lerdir](../standard-library/regex-functions.md)\
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)\
[\<regex> işletmenlerinin](../standard-library/regex-operators.md)\
[regex_token_iterator sınıfı](../standard-library/regex-token-iterator-class.md)\
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)\
[\<regex> tür tanımları](../standard-library/regex-typedefs.md)
