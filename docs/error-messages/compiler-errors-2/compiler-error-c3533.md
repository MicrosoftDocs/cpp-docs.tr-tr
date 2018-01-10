---
title: "Derleyici Hatası C3533 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3533
dev_langs: C++
helpviewer_keywords: C3533
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e7bcd9c710ac5cdd50b966a72291918459d984be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3533"></a>Derleyici Hatası C3533
'type': bir parametre 'auto' içeren bir türe sahip olamaz  
  
 Bir yöntemi veya şablon parametresi ile bildirilemez `auto` anahtar sözcüğü, varsayılan [/Zc:auto](../../build/reference/zc-auto-deduce-variable-type.md) derleyici seçeneği etkindir.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Kaldırma `auto` parametre bildirimi anahtar sözcük.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte bir işlev parametresi ile bildirdiğinden C3535 verir `auto` anahtar sözcüğü ve derlenmiş ile **/Zc:auto**.  
  
```  
// C3533a.cpp  
// Compile with /Zc:auto  
void f(auto j){} // C3533  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte bir şablon parametresi ile bildirdiğinden C3535 verir `auto` anahtar sözcüğü ve derlenmiş ile **/Zc:auto**.  
  
```  
// C3533b.cpp  
// Compile with /Zc:auto  
template<auto T> class C{}; // C3533  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Auto anahtar sözcüğü](../../cpp/auto-keyword.md)   
 [/ZC:Auto (değişken türünü)](../../build/reference/zc-auto-deduce-variable-type.md)