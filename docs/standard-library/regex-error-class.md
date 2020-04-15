---
title: regex_error Sınıfı
ms.date: 09/10/2018
f1_keywords:
- regex/std::regex_error
- regex/std::regex_error::code
helpviewer_keywords:
- regex_error class
ms.assetid: 3333a1a3-ca6f-4612-84b2-1b4c7e3db5a4
ms.openlocfilehash: f8f3c88c1b203ed7fcea148843fa99590e27b888
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331864"
---
# <a name="regex_error-class"></a>regex_error Sınıfı

Kötü bir basic_regex nesnesi bildirir.

## <a name="syntax"></a>Sözdizimi

```cpp
class regex_error
: public std::runtime_error
```

## <a name="remarks"></a>Açıklamalar

Sınıf, bir `basic_regex` nesnenin yapısında veya kullanımında bir hatayı bildirmek için atılan bir özel durum nesnesini açıklar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[regex_error](#regex_error)|Nesneyi inşa eder.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[Kod](#code)|Hata kodunu döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<regex>

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

## <a name="regex_errorcode"></a><a name="code"></a>regex_error::kod

Hata kodunu döndürür.

```cpp
regex_constants::error_code code() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlev, nesnenin oluşturucusuna geçirilen değeri döndürür.

## <a name="regex_errorregex_error"></a><a name="regex_error"></a>regex_error:regex_error

Nesneyi inşa eder.

```cpp
regex_error(regex_constants::error_code error);
```

### <a name="parameters"></a>Parametreler

*Hata*\
Hata kodu.

### <a name="remarks"></a>Açıklamalar

Kurucu değer *hatasını*tutan bir nesne inşa eder.

## <a name="see-also"></a>Ayrıca bkz.

[\<regex>](../standard-library/regex.md)\
[regex_constants Sınıfı](../standard-library/regex-constants-class.md)\
[\<regex> fonksiyonları](../standard-library/regex-functions.md)\
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)\
[\<regex> operatörleri](../standard-library/regex-operators.md)\
[regex_token_iterator Sınıfı](../standard-library/regex-token-iterator-class.md)\
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)\
[\<regex> typedefs](../standard-library/regex-typedefs.md)
