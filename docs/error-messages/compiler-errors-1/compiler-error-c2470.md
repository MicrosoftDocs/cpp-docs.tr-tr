---
title: "Derleyici Hatası C2470 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2470
dev_langs: C++
helpviewer_keywords: C2470
ms.assetid: e17d2cb8-b84c-447c-976a-625f0c96f3fe
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 834ad581956c99e40e54a97f9d307691dce08600
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2470"></a>Derleyici Hatası C2470
'function': işlev tanımı gibi görünüyor, ancak hiçbir parametre listesi; yok görünen gövde atlanıyor  
  
 Bağımsız değişken listesi bir işlev tanımı eksik.  
  
 Aşağıdaki örnek C2470 oluşturur:  
  
```  
// C2470.cpp  
int MyFunc {};  // C2470  
void MyFunc2() {};  //OK  
  
int main(){  
   MyFunc();  
   MyFunc2();  
}  
```