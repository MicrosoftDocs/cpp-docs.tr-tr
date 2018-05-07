---
title: Derleyici Hatası C3533 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3533
dev_langs:
- C++
helpviewer_keywords:
- C3533
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f184f0459e7ec2251d6ff34e2ee76559fe0dea42
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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
 [/Zc:auto (Değişken Türünü Türet)](../../build/reference/zc-auto-deduce-variable-type.md)