---
title: Derleyici Uyarısı (Düzey 3) C4240 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4240
dev_langs:
- C++
helpviewer_keywords:
- C4240
ms.assetid: a2657cdb-18e1-493f-882b-4e10c0bca71d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f0691230454ffd935d67c99f58b857cdc1ce0f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33292707"
---
# <a name="compiler-warning-level-3-c4240"></a>Derleyici Uyarısı (Düzey 3) C4240
kullanılan standart olmayan uzantısı: erişim için 'şimdi 'erişim belirticisi', daha önce onu olarak tanımlanan classname' tanımlandığı 'erişim belirteci' olmalıdır  
  
 ANSI Uyumluluğu altında ([/Za](../../build/reference/za-ze-disable-language-extensions.md)), bir iç içe geçmiş sınıf erişim değiştiremezsiniz. Varsayılan Microsoft uzantıları altında (/Ze), bu uyarı ile kullanabilirsiniz.  
  
## <a name="example"></a>Örnek  
  
```  
// C4240.cpp  
// compile with: /W3  
class X  
{  
private:  
   class N;  
public:  
   class N  
   {   // C4240  
   };  
};  
  
int main()  
{  
}  
```