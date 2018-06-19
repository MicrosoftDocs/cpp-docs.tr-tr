---
title: Derleyici Hatası C3285 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3285
dev_langs:
- C++
helpviewer_keywords:
- C3285
ms.assetid: 04e8f210-d67e-4810-b153-e1efe2986c8f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8991383147618d1168a9819ee02e2567cc4a6852
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33252647"
---
# <a name="compiler-error-c3285"></a>Derleyici Hatası C3285
for each deyimi türü 'type' değişkenlerde çalıştırılamıyor  
  
 `for each` Deyimi bir dizi veya nesne koleksiyonu her öğe için bir grup katıştırılmış ifadeler tekrarlar.  
  
 Bkz: [her biri için de](../../dotnet/for-each-in.md) daha fazla bilgi için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3285 oluşturur.  
  
```  
// C3285.cpp  
// compile with: /clr  
int main() {  
   for each (int i in 0) {}   // C3285   
  
   array<int> ^p = { 1, 2, 3 };  
   for each (int j in p) {}   // OK  
}  
```