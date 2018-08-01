---
title: karakter, wchar_t, char16_t, char32_t | Microsoft Docs
ms.custom: ''
ms.date: 02/14/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- char_cpp
- char16_t_cpp
- wchar_t_cpp
- char32_t_cpp
dev_langs:
- C++
ms.assetid: 6b33e9f5-455b-4e49-8f12-a150cbfe2e5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2d0c89df02c624d96c613f6241c9beefd466827e
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402620"
---
# <a name="char-wchart-char16t-char32t"></a>char, wchar_t, char16_t, char32_t
Türleri **char**, **wchar_t**, **char16_t** ve **char32_t** alfasayısal karakterleri temsil eden yerleşik türleri olarak alfasayısal olmayan karakterleri ve yazdırılamayan karakterler.

## <a name="syntax"></a>Sözdizimi

```cpp  
char     ch1{ 'a' };  // or { u8'a' }   
wchar_t  ch2{ L'a' };    
char16_t ch3{ u'a' };    
char32_t ch4{ U'a' };  
```  
  
## <a name="remarks"></a>Açıklamalar

**Char** türde C ve C++'ta orijinal karakter türü. Türü **imzasız char** temsil etmek için kullanılan bir *bayt*, C++'ta yerleşik bir tür değil. **Char** türü, ASCII karakter kümesi veya herhangi bir ISO-8859 karakter kümesi ve tek tek bayt Shift-JIS gibi çok baytlı karakter veya Unicode karakter kümesini UTF-8 kodlaması karakterlerinden depolamak için kullanılabilir. Dizeleri **char** türü denir *daraltmak* bile çok baytlı karakterleri kodlamak için kullanıldığında, dizeleri. Microsoft derleyicisi, **char** bir 8 bit türüdür.

**Wchar_t** türüdür, uygulamada tanımlı geniş karakter türü. Microsoft derleyicisi Unicode UTF-16LE kodlanmış depolamak için kullanılan bir 16 bit geniş karakter temsil ettiği Windows işletim sistemlerinde yerel karakter türü. Evrensel C çalışma zamanı (UCRT) kitaplığı işlevleri kullanımı geniş karakter sürümleri **wchar_t** ve dizi ve işaretçi türleri parametreler ve dönüş değerleri olarak yerel Windows API'ın geniş karakter sürümleridir.

**Char16_t** ve **char32_t** türleri 16-bit ve 32-bit geniş karakterler sırasıyla temsil eder. Unicode UTF-16 depolanabilir gibi kodlanmış **char16_t** türü ve Unicode UTF-32 depolanabilir gibi kodlanmış **char32_t** türü. Bu tür dizeleri ve **wchar_t** olan tüm denilen *geniş* dizeler özellikle dizeleri için genelde bu terim başvuruyor ancak **wchar_t** türü.

C++ Standart Kitaplığı'nda `basic_string` türü için hem dar hem geniş dize özelleştirilmiş. Kullanım `std::string` karakter türü olduğunda **char**, `std::u16string` karakter türü olduğunda **char16_t**, `std::u32string` karakter türü olduğunda **char32_t** , ve `std::wstring` karakter türü olduğunda **wchar_t**. Metin, diğer türler dahil olmak üzere `std::stringstream` ve `std::cout` dar ve geniş dizeleri uzmanlıklar vardır.  