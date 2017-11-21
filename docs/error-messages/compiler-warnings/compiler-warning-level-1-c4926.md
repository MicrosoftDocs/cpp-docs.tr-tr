---
title: "Derleyici Uyarısı (düzey 1) C4926 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4926
dev_langs: C++
helpviewer_keywords: C4926
ms.assetid: 5717fce0-146f-4ef2-bde0-e9a01c0922d1
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e5ae52162562fcd2ea16e693981b7b959a290e76
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4926"></a>Derleyici Uyarısı (düzey 1) C4926
'tanımlayıcısı': sembolü zaten tanımlandı: göz ardı öznitelikleri  
  
 İleriye dönük bildirimi bulundu ancak aynı ada sahip bir öznitelikli yapısıyla zaten mevcut. İleriye dönük bildirimi özniteliklerini göz ardı edilir.  
  
 Aşağıdaki örnek C4926 oluşturur:  
  
```  
// C4926.cpp  
// compile with: /W1  
[module(name="MyLib")];  
  
[coclass]  
struct a {  
};  
  
[coclass]  
struct a;   // C4926  
  
int main() {  
}  
```