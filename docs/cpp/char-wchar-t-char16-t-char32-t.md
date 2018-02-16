---
title: char, wchar_t, char16_t, char32_t | Microsoft Docs
ms.custom: 
ms.date: 02/14/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- char_cpp
- char16_t_cpp
- wchar_t_cpp
- char32_t_cpp
dev_langs:
- C++
ms.assetid: 6b33e9f5-455b-4e49-8f12-a150cbfe2e5b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a87eff9801b2754909159ef4d5e2c24c079ee8f1
ms.sourcegitcommit: 23a0ddd271bbcc31631283542981ff5f1693d27f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2018
---
# <a name="char-wchart-char16t-char32t"></a>char, wchar_t, char16_t, char32_t
Türleri **char**, **wchar_t**, **char16_t** ve **char32_t** alfasayısal karakterler temsil eden yerleşik türleri olarak alfasayısal olmayan karakterlerin ve yazdırılamayan karakterler.

## <a name="syntax"></a>Sözdizimi

```cpp  
char     ch1{ 'a' };  // or { u8'a' }   
wchar_t  ch2{ L'a' };    
char16_t ch3{ u'a' };    
char32_t ch4{ U'a' };  
```  
  
## <a name="remarks"></a>Açıklamalar

**Char** türü olan C ve C++ özgün karakter türü. Türü **imzasız char** temsil etmek için kullanılan bir *bayt*, C++'ta yerleşik bir tür değil. **Char** türü, ASCII karakter kümesi veya herhangi bir ISO 8859 karakter kümeleri ve çok baytlı karakter Shift JIS gibi tek tek bayt veya UTF-8 kodlaması Unicode karakter kümesini karakterlerinden depolamak için kullanılabilir. Dizeleri **char** türü denir *daraltmak* bile çok baytlı karakterler kodlamak için kullanıldığında, dizeleri. Microsoft derleyicide **char** bir 8 bit türüdür.

**Wchar_t** türü olan bir uygulama tanımlı geniş karakter türü. Microsoft derleyicide UTF-16LE kodlanmış Unicode depolamak için kullanılan bir 16 bit geniş karakter temsil ettiği Windows işletim sistemlerinde yerel karakter türü. Evrensel C çalışma zamanı (UCRT) kitaplığı işlevleri kullanımı geniş karakter sürümlerini **wchar_t** işaretçi ve dizi türlerini ve parametreler ve dönüş değerleri olarak yerel Windows API geniş karakter sürümleri.

**Char16_t** ve **char32_t** türleri 16 bit ve 32-bit geniş karakterler sırasıyla temsil eder. UTF-16 depolanabilir olarak kodlanmış Unicode **char16_t** türü ve UTF-32 depolanabilir olarak kodlanmış Unicode **char32_t** türü. Bu tür dizeler ve **wchar_t** olan tüm denir *geniş* dizeleri terimi genellikle özellikle dizeleri için anlamına gelir ancak **wchar_t** türü.

C++ Standart Kitaplığı'nda `basic_string` türü dar ve geniş dizeleri için özelleştirilmiş. Kullanım `std::string` karakter türü olduğunda **char**, `std::u16string` karakter türü olduğunda **char16_t**, `std::u32string` karakter türü olduğunda **char32_t** , ve `std::wstring` karakter türü olduğunda **wchar_t**. Bir metin temsil eden diğer türleri dahil olmak üzere `std::stringstream` ve `std::cout` dar ve geniş dizeleri özelleştirmeleri sahip.  
  
