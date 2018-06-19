---
title: Derleyici Hatası C3532 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3532
dev_langs:
- C++
helpviewer_keywords:
- C3532
ms.assetid: 51067853-eda8-4f59-86e8-8924e16d3a95
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1efce6659f8d848b47f0c4194b6420177ffad194
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33254980"
---
# <a name="compiler-error-c3532"></a>Derleyici Hatası C3532
'type': 'auto' yanlış kullanımı  
  
 Belirtilen tür ile bildirilemez `auto` anahtar sözcüğü. Örneğin, kullanamazsınız `auto` bir dizi veya bir yöntem bildirmek için anahtar sözcüğü dönüş türü.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Başlatma ifade geçerli bir tür verir emin olun.  
  
2.  Bir dizi veya bir yöntemin dönüş türü bildirme emin olun.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3532 çünkü verir `auto` anahtar sözcüğü bir yöntemin dönüş türü bildiremez.  
  
```  
// C3532a.cpp  
// Compile with /Zc:auto  
auto f(){}   // C3532  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3532 çünkü verir `auto` anahtar sözcüğü bir dizi bildiremez.  
  
```  
// C3532b.cpp  
// Compile with /Zc:auto  
int main()  
{  
   int x[5];  
   auto a[5];            // C3532  
   auto b[1][2];         // C3532  
   auto y[5] = x;        // C3532  
   auto z[] = {1, 2, 3}; // C3532  
   auto w[] = x;         // C3532  
   return 0;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)