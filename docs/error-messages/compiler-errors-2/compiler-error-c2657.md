---
title: "Derleyici Hatası C2657 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2657
dev_langs: C++
helpviewer_keywords: C2657
ms.assetid: f7cf29a9-684a-4605-9469-ecfee9ba4b03
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2e0e06104458961297a4d0a3de8b7cda756d16ab
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2657"></a>Derleyici Hatası C2657
' sınıfı:: *' deyiminin başlangıcında bulundu (bir türünü belirtmek unuttunuz mu?)  
  
 Satır işaretçi-üye tanımlayıcısı ile başlamıştır.  
  
 Bu hata bir işaretçi bildiriminde eksik bir tür belirleyici bir üyesine neden olabilir.  
  
 Aşağıdaki örnek C2657 oluşturur:  
  
```  
// C2657.cpp  
class C {};  
int main() {  
   C::* pmc1;        // C2657  
   int C::* pmc2;   // OK  
}  
```