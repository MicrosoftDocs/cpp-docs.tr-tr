---
title: "Derleyici Hatası C3537 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3537
dev_langs: C++
helpviewer_keywords: C3537
ms.assetid: f537ebd1-4fb0-4e09-a453-4f38db2c6881
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3a131b7bab9c89c7a5ea39a4b5b05d8e91b572fe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3537"></a>Derleyici Hatası C3537
'type': 'auto' içeren bir türü atanamaz  
  
 Belirtilen tür için bir değişken türünü içerdiğinden atanamaz `auto` anahtar sözcüğü ve varsayılan [/Zc:auto](../../build/reference/zc-auto-deduce-variable-type.md) derleyici seçeneği etkindir.  
  
## <a name="example"></a>Örnek  
 Değişkenleri içeren türüne dönüştürmek için aşağıdaki kodu C3537 verir `auto` anahtar sözcüğü.  
  
```  
// C3537.cpp  
// Compile with /Zc:auto  
int main()  
{  
   int value = 123;  
   auto(value);                        // C3537  
   (auto)value;                        // C3537  
   auto x1 = auto(value);              // C3537  
   auto x2 = (auto)value;              // C3537  
   auto x3 = static_cast<auto>(value); // C3537  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)