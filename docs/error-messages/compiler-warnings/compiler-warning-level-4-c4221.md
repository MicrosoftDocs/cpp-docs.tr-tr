---
title: "Derleyici Uyarısı (düzey 4) C4221 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4221
dev_langs: C++
helpviewer_keywords: C4221
ms.assetid: 8532bd68-54dc-4526-8597-f61dcb0a0129
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6a08b300961bd19cc0355cc556d52dd00d05632e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4221"></a>Derleyici Uyarısı (düzey 4) C4221
kullanılan standart olmayan uzantısı: 'tanımlayıcısı': otomatik değişkenin adresini kullanarak başlatılamaz  
  
 Varsayılan Microsoft Uzantıları (/Ze), bir toplama türü başlatabilir (**dizi**, `struct`, veya **UNION**) yerel (otomatik) değişken adresine sahip.  
  
## <a name="example"></a>Örnek  
  
```  
// C4221.c  
// compile with: /W4  
struct S  
{  
   int *i;  
};  
  
void func()  
{  
   int j;  
   struct S s1 = { &j };   // C4221  
}  
  
int main()  
{  
}  
```  
  
 Bu tür başlatmaları ANSI Uyumluluğu altında geçersiz ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).