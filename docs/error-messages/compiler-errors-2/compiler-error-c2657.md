---
title: Derleyici Hatası C2657 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2657
dev_langs:
- C++
helpviewer_keywords:
- C2657
ms.assetid: f7cf29a9-684a-4605-9469-ecfee9ba4b03
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 70814ce7423bee3147f68d6298babc10eeac56fb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33231390"
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