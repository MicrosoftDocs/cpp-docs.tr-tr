---
title: Derleyici Uyarısı (düzey 4) C4201 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4201
dev_langs:
- C++
helpviewer_keywords:
- C4201
ms.assetid: 6156f508-9393-4d77-9e73-1ec3e1c32d0d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 56805506c112d0d92b627b905199bcbbeae8d2f7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4201"></a>Derleyici Uyarısı (düzey 4) C4201
kullanılan standart olmayan uzantısı: Adsız struct/birleşim  
  
 Microsoft Uzantıları (/Ze) altında bir bildirimcisi olmadan bir yapı başka bir yapı veya birleşim üyeleri olarak belirtebilirsiniz. Bu yapıları ANSI Uyumluluğu altında bir hata oluştur ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).  
  
## <a name="example"></a>Örnek  
  
```  
// C4201.cpp  
// compile with: /W4  
struct S  
{  
   float y;  
   struct  
   {  
      int a, b, c;  // C4201  
   };  
} *p_s;  
  
int main()  
{  
}  
```