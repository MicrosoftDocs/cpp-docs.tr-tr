---
title: Derleyici Hatası C3535 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3535
dev_langs:
- C++
helpviewer_keywords:
- C3535
ms.assetid: 24449c98-f681-484d-a00b-32533dca3a88
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff9935f4a46ba2c3a268ebb761153948ccd82f47
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3535"></a>Derleyici Hatası C3535
'type2' öğesinden 'type1' türünü türetme olamaz  
  
 Tarafından bildirilen değişken türünü `auto` anahtar sözcüğü başlatma ifade türünden anlaşılan olamaz. Örneğin, başlatma ifade değerlendirilirse bu hata oluşur. `void`, bir tür değil.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Başlatma ifade türü olmadığından emin `void`.  
  
2.  Bildirim temel türü için bir işaretçi olmadığından emin olun. Daha fazla bilgi için bkz: [temel türleri](../../cpp/fundamental-types-cpp.md).  
  
3.  Bildirim türü için bir işaretçi ise, başlatma ifadesi bir işaretçi türü olduğundan emin olun.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek için başlatma ifadeyi hesaplar çünkü C3535 verir `void`.  
  
```  
// C3535a.cpp  
// Compile with /Zc:auto  
void f(){}  
int main()  
{  
   auto x = f();   //C3535  
   return 0;  
}  
```  
  
## <a name="example"></a>Örnek  
 Deyim değişkeni bildirdiğinden aşağıdaki örnek C3535 verir `x` sonucuna varılan bir tür, ancak Başlatıcı türü için bir işaretçi olarak çift ifadesidir. Sonuç olarak, derleyici değişken türünü türetme olamaz.  
  
```  
// C3535b.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto* x = 123.0;   // C3535  
   return 0;  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3535 çünkü verir değişkeni `p` sonucuna varılan bir tür için bir işaretçi bildirir, ancak başlatma ifadesi bir işaretçi türü değil.  
  
```  
// C3535c.cpp  
// Compile with /Zc:auto  
class A { };  
A x;  
auto *p = x;  // C3535  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Auto anahtar sözcüğü](../../cpp/auto-keyword.md)   
 [Temel Türler](../../cpp/fundamental-types-cpp.md)