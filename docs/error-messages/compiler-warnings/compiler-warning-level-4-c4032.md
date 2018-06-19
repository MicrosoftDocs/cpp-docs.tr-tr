---
title: Derleyici Uyarısı (düzey 4) C4032 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4032
dev_langs:
- C++
helpviewer_keywords:
- C4032
ms.assetid: 70dd0c85-0239-43f9-bb06-507f6a57d206
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb61588c12378972194305d979ecdd89140ac6f6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33291693"
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