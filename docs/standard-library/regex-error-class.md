---
title: "regex_error sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- regex/std::regex_error
- regex/std::regex_error::code
dev_langs:
- C++
helpviewer_keywords:
- regex_error class
ms.assetid: 3333a1a3-ca6f-4612-84b2-1b4c7e3db5a4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1cc2861da5e133754459d6721c3ce528eaab5897
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="regexerror-class"></a>regex_error Sınıfı
Hatalı basic_regex nesne bildirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class regex_error  
 : public std::runtime_error {  
public:  
    explicit regex_error(regex_constants::error_code error);

    regex_constants::error_code code() const;

 
 };  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Hatayla yapım veya kullanımını raporlamak için oluşturulan bir özel durum nesnesi sınıfı tanımlar bir `basic_regex` nesnesi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<regex >  
  
 **Namespace:** std  
  
##  <a name="code"></a>  regex_error::code  
 Hata kodu döndürür.  
  
```  
regex_constants::error_code code() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini nesnenin oluşturucuya geçirilen değeri döndürür.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__regex__regex_error_code.cpp   
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
            << (rerr.code() == paren.code()   
                 "unbalanced parentheses" : "")   
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
  
##  <a name="regex_error"></a>  regex_error::regex_error  
 Nesnesi oluşturur.  
  
```  
regex_error(regex_constants::error_code error);
```  
  
### <a name="parameters"></a>Parametreler  
 `error`  
 Hata kodu.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturucusu değeri tutan bir nesne oluşturur `error`.  
  
### <a name="example"></a>Örnek  
  
```cpp  
// std__regex__regex_error_construct.cpp   
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
            << (rerr.code() == paren.code()   
                 "unbalanced parentheses" : "")   
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
[\<regex>](../standard-library/regex.md)  
[regex_constants Sınıfı](../standard-library/regex-constants-class.md)  
[\<Regex > işlevleri](../standard-library/regex-functions.md)  
[regex_iterator Sınıfı](../standard-library/regex-iterator-class.md)  
[\<Regex > işleçleri](../standard-library/regex-operators.md)  
[regex_token_iterator Sınıfı](../standard-library/regex-token-iterator-class.md)  
[regex_traits Sınıfı](../standard-library/regex-traits-class.md)  
[\<Regex > tür tanımları](../standard-library/regex-typedefs.md)  
