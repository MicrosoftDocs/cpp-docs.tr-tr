---
title: "Derleyici Hatası C2767 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2767
dev_langs: C++
helpviewer_keywords: C2767
ms.assetid: e8f84178-a160-4d71-a236-07e4fcc11e96
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9147d85afaee50a2b0c2e47debe5603d6e208712
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2767"></a>Derleyici Hatası C2767
yönetilen veya WinRTarray boyut uyuşmazlığı: N bağımsız değişkenli - M sağlanan bekleniyor  
  
 Bir yönetilen veya WinRT dizi bildirimi ill biçimlendirilmiş. Daha fazla bilgi için bkz: [dizi](../../windows/arrays-cpp-component-extensions.md).  
  
 Aşağıdaki örnek C2767 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C2767.cpp  
// compile with: /clr  
int main() {  
   array<int> ^p1 = new array<int>(2,3); // C2767  
   array<int> ^p2 = new array<int>(2);   // OK  
}  
```