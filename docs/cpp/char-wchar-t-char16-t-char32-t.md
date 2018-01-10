---
title: char, wchar_t, char16_t, char32_t | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- char_cpp
- char16_t_cpp
- wchar_t_cpp
- char32_t_cpp
dev_langs: C++
ms.assetid: 6b33e9f5-455b-4e49-8f12-a150cbfe2e5b
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c01d4718bbc1781ea4705945bb90874384e09058
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="char-wchart-char16t-char32t"></a>char, wchar_t, char16_t, char32_t
Türleri char, wchar_t, char16_t ve char32_t alfasayısal karakterler yanı sıra alfasayısal olmayan karakterlerin ve yazdırılamayan karakterler temsil eden türleri oluşturulur. char boyutu sekiz bittir, wchar_t ve char16_t boyutu 16 bit ve 32 bit char32_t olduğundan.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
char     ch1{ 'a' };    
wchar_t  ch2{ 'a' }; // or {L'a'}    
char16_t ch3{ L'a' };// or {L'a'}    
char32_t ch4{ L'a' };// or {L'a'}  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `char` Türü olan C ve C++ özgün karakter türü. UTF-8 karakter kümesi veya ASCII karakter kümesi ya da herhangi bir ISO 8859 karakter kümesi karakterlerinden depolamak için kullanılabilir. Türü `unsigned char` temsil etmek için kullanılan bir *bayt* c++ yerleşik bir tür değil. Char türü birden çok dilde metin için uygun değil. Genel olarak, modern programlar geniş karakter türlerinden birini metin göstermek için kullanmanız gerekir. Unicode  
  
 C++ Standart Kitaplığı basic_string türü dar ve geniş dizeleri için özelleştirilmiş. Karakterler tür char ve std::wstring olduğunda karakterler türü wchar_t olduğunda std::string kullanın. Std::stringstream ve std::cout dahil olmak üzere bir metin temsil eden diğer özelleştirmeleri dar ve geniş dizeleri vardır.  
  
