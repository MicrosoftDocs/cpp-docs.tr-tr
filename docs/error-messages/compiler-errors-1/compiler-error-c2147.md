---
title: Derleyici Hatası C2147 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2147
dev_langs:
- C++
helpviewer_keywords:
- C2147
ms.assetid: d1adb3bf-7ece-4815-922c-ad7492fb6670
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 60047795428aad2da94b117882f351375fed4545
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33167989"
---
# <a name="compiler-error-c2147"></a>Derleyici Hatası C2147
sözdizimi hatası: ' tanımlayıcısıdır ' yeni bir anahtar sözcüğü  
  
 Tanımlayıcı, şu anda ayrılmış bir anahtar sözcük dilde kullanıldı.  
  
 Aşağıdaki örnek C2147 oluşturur:  
  
```  
// C2147.cpp  
// compile with: /clr  
int main() {  
   int gcnew = 0;   // C2147  
   int i = 0;   // OK  
}  
```