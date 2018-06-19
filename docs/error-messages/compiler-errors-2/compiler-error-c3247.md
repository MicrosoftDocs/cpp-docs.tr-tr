---
title: Derleyici Hatası C3247 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3247
dev_langs:
- C++
helpviewer_keywords:
- C3247
ms.assetid: f9a2bbb5-3fce-40bf-9fd3-835a5f164dbb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d64ba734203cdac6a56a82f3fd44853d62af53fd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33249261"
---
# <a name="compiler-error-c3247"></a>Derleyici Hatası C3247
'class1': bir coclass'ı başka bir coclass 'class2' devralır olamaz  
  
 Bir sınıf ile işaretli [coclass](../../windows/coclass.md) özniteliği ile işaretlenmiş başka bir sınıftan devralır olamaz `coclass` özniteliği.  
  
 Aşağıdaki örnek C3247 oluşturur:  
  
```  
// C3247.cpp  
[module(name="MyLib")];  
[coclass]  
class a {  
};  
  
[coclass]  
class b : public a {   // C3247  
};  
int main() {  
}  
```