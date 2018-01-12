---
title: "Derleyici Uyarısı (düzey 1) C4178 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4178
dev_langs: C++
helpviewer_keywords: C4178
ms.assetid: 2c2c8f97-a5c4-47cd-8dd2-beea172613f3
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7a5080f19d9962509b7f2c716f380722bf402b3a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4178"></a>Derleyici Uyarısı (düzey 1) C4178
Servis talebi sabiti 'constant' türü için çok büyük anahtar ifadesinin  
  
 Bir servis talebi sabit bir `switch` ifadesi kendisine atandı türünde uygun değil.  
  
## <a name="example"></a>Örnek  
  
```  
// C4178.cpp  
// compile with: /W1  
int main()  
{  
    int i;  // maximum size of unsigned long int is 4294967295  
    switch( i )  
    {  
        case 4294967295:   // OK  
            break;  
        case 4294967296:   // C4178  
            break;  
    }  
 }  
```