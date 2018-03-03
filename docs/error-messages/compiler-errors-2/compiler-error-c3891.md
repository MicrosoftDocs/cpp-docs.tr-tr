---
title: "Derleyici Hatası C3891 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3891
dev_langs:
- C++
helpviewer_keywords:
- C3891
ms.assetid: 6e1a9458-97f5-4580-bc0f-aa97a1bfd20d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: daf8c50dfb041194e376b1b62943da021a423ed4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3891"></a>Derleyici Hatası C3891
'var': değişmez değer veri üyesi l-değeri kullanılamaz  
  
 A [değişmez değer](../../windows/literal-cpp-component-extensions.md) değişkenidir const ve bildiriminde başlatıldıktan sonra değeri değiştirilemez.  
  
 Aşağıdaki örnek C3891 oluşturur:  
  
```  
// C3891.cpp  
// compile with: /clr  
ref struct Y1 {  
   literal int staticConst = 9;  
};  
  
int main() {  
   Y1::staticConst = 0;   // C3891  
}  
```