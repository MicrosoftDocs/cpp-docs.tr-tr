---
title: "Derleyici Uyarısı (düzey 1) C4144 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4144
dev_langs:
- C++
helpviewer_keywords:
- C4144
ms.assetid: a37b445d-dbc6-43b4-8d95-ffd0e4225464
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d085cfdb4b84f6972dd42d83a94731ff56bfc2ed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4144"></a>Derleyici Uyarısı (düzey 1) C4144
'ifadesi': anahtar ifade olarak ilişkisel ifade  
  
 Belirtilen ilişkisel ifade denetim ifadesi olarak kullanılan bir [geçiş](../../cpp/switch-statement-cpp.md) deyimi. Boole değerleri ilişkili case deyimleri sunulur. Aşağıdaki örnek C4144 oluşturur:  
  
```  
// C4144.cpp  
// compile with: /W1  
int main()  
{  
   int i = 0;  
   switch(!i) {   // C4144, remove the ! to resolve  
      case 1:  
         break;  
      default:  
         break;  
   }  
}  
```