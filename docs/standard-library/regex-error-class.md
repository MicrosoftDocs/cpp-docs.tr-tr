---
title: regex_error sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 09/10/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- regex/std::regex_error
- regex/std::regex_error::code
dev_langs:
- C++
helpviewer_keywords:
- regex_error class
ms.assetid: 3333a1a3-ca6f-4612-84b2-1b4c7e3db5a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7358af41e1a7172daec619bec3e701ff4541fd0c
ms.sourcegitcommit: 27b5712badd09a09c499d887e2e4cf2208a28603
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2018
ms.locfileid: "44384988"
---
# <a name="regexerror-class"></a>regex_error Sınıfı

Hatalı basic_regex nesne bildirir.

## <a name="syntax"></a>Sözdizimi

```cpp
class regex_error
: public std::runtime_error
```

## <a name="remarks"></a>Açıklamalar

Hata oluşturma veya kullanımını raporlamak için oluşturulan bir özel durum nesnesi sınıfı açıklar bir `basic_regex` nesne.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[regex_error](#regex_error)|Bir nesne oluşturur.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Kod](#code)|Hata kodu döndürür.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<regex >

**Namespace:** std

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

## <a name="code"></a>  regex_error::Code

Hata kodu döndürür.

```cpp
regex_constants::error_code code() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, nesnenin oluşturucuya geçirilen değeri döndürür.

## <a name="regex_error"></a>  regex_error::regex_error

Bir nesne oluşturur.

```cpp
regex_error(regex_constants::error_code error);
```

### <a name="parameters"></a>Parametreler

*Hata*<br/>
Hata kodu.

### <a name="remarks"></a>Açıklamalar

Oluşturucu değeri tutan bir nesne oluşturur *hata*.

## <a name="see-also"></a>Ayrıca bkz.

[\<Regex >](../standard-library/regex.md)<br/>
[regex_constants Sınıfı](../standard-library/regex-constants-class.md)<br/>
[\<Regex > işlevleri](../standard-library/regex-functions.md)<br/>
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)<br/>
[\<Regex > işleçleri](../standard-library/regex-operators.md)<br/>
[regex_token_iterator Sınıfı](../standard-library/regex-token-iterator-class.md)<br/>
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)<br/>
[\<Regex > tür tanımları](../standard-library/regex-typedefs.md)<br/>
