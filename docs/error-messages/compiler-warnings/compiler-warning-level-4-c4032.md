---
title: "Derleyici Uyarısı (düzey 4) C4032 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4032
dev_langs: C++
helpviewer_keywords: C4032
ms.assetid: 70dd0c85-0239-43f9-bb06-507f6a57d206
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 67700d14ef76b0b2f80621b18b6e4b1e469925a4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4032"></a>Derleyici Uyarısı (düzey 4) C4032
biçimsel parametresi 'numara' yükseltilmiş zaman farklı türüne sahip  
  
 Parametre türü önceki bildiriminde türüyle varsayılan promosyonlar aracılığıyla uyumlu değil.  
  
 Bu bir hatadır ANSI c ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) ve Microsoft Uzantıları (/Ze) altında bir uyarı.  
  
## <a name="example"></a>Örnek  
  
```  
// C4032.c  
// compile with: /W4  
void func();  
void func(char);   // C4032, char promotes to int  
  
int main()  
{  
}  
```