---
title: "Komut makroları ve seçenek makroları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- options macros
- command macros in NMAKE
- macros, options macros
- macros, command macros
ms.assetid: 50dff03c-0dc3-4a8a-9a17-57e0e4ea9bac
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 06f5d48395c0395a85c90096bf2dbad8627ac41a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="command-macros-and-options-macros"></a>Komut Makroları ve Seçenek Makroları
Komut makroları Microsoft ürünleri için önceden tanımlanmıştır. Seçenekler makroları bu ürünler için seçenekleri temsil eder ve varsayılan olarak tanımlanmamış. Her ikisi de önceden tanımlanmış çıkarım kurallarındaki kullanılır ve açıklama blokları veya kullanıcı tanımlı çıkarım kuralları kullanılabilir. Komut makroları kısmını veya tamamını seçenekleri de dahil olmak üzere bir komut satırı temsil etmek için tanımlanabilir. Seçenekler makroları sol tanımsız ise boş bir dize oluşturur.  
  
|Microsoft Ürün|Komut makrosu|Olarak tanımlanır|Seçenekler makrosu|  
|-----------------------|-------------------|----------------|-------------------|  
|Makro derleyici|**OLARAK**|ml|**AFLAGS**|  
|Temel derleyici|**BC**|BC|**BFLAGS**|  
|C derleyicisi|**CC**|cl|**CFLAGS**|  
|C++ Derleyicisi|**CPP**|cl|**CPPFLAGS**|  
|C++ Derleyicisi|**CXX**|cl|**CXXFLAGS**|  
|Kaynak Derleyicisi|**RC**|RC|**RFLAGS**|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel NMAKE Makroları](../build/special-nmake-macros.md)