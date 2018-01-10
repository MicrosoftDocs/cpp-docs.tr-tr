---
title: "Birden çok baytlı ve geniş karakterler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- globalization [C++], character sets
- character data types [C]
- Unicode [C++], wide character set
- types [C], character
- characters [C++], wide
- international applications [C++], character display
- multibyte characters [C++]
- wide characters [C++]
- characters [C++], codes
- character codes [C++], wide
- character codes [C++], multibyte
ms.assetid: 1943c469-200d-4724-b18f-781d70520f9e
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d0b2c07429e4401bbecb5e989ac8fd2ece772e29
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="multibyte-and-wide-characters"></a>Birden Çok Baytlı ve Geniş Karakterler
Çok baytlı bir karakter, bir veya daha fazla bayt dizisinden oluşan bir karakterdir. Her bayt dizisi, genişletilmiş karakter kümesinde tek bir karakteri temsil eder. Çok baytlı karakterler Kanji gibi karakter kümelerinde kullanılır.  
  
 Geniş karakterler, her zaman 16 bit genişliğinde olan çok dilli karakter kodlarıdır. Karakter sabitlerinin türü `char`, geniş karakterlerin türü ise `wchar_t`'dir. Geniş karakterler her zaman sabit boyutta olduğu için geniş karakterlerin kullanılması uluslararası karakter kümeleriyle programlamayı basitleştirir.  
  
 `L"hello"` geniş karakter dize sabit değeri, `wchar_t` türünden altı tamsayı dizisi haline gelir.  
  
```  
{L'h', L'e', L'l', L'l', L'o', 0}  
```  
  
 Unicode belirtimi, geniş karakterlere yönelik belirtimdir. Çok baytlı ve geniş karakterler arasında çeviriye yönelik çalışma zamanı kitaplık yordamları arasında `mbstowcs`, `mbtowc`, `wcstombs` ve `wctomb` bulunur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Tanımlayıcıları](../c-language/c-identifiers.md)