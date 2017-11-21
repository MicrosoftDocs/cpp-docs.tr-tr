---
title: "Derleyici Hatası C3286 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3286
dev_langs: C++
helpviewer_keywords: C3286
ms.assetid: 554328c8-cf44-4f7d-a8d2-def74d28ecdd
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ea704fce0aebd3ffa83410104b38ceb5d359a6c6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3286"></a>Derleyici Hatası C3286  
  
> '*belirticisi*': bir yineleme değişkeni tüm depolama sınıfı tanımlayıcıları sahip olamaz  
  
Depolama sınıfı bir yineleme değişkeni belirtilemez. Daha fazla bilgi için bkz: [depolama sınıfları (C++)](../../cpp/storage-classes-cpp.md) ve [her biri için de](../../dotnet/for-each-in.md).  
  
## <a name="example"></a>Örnek  
  
Aşağıdaki örnek C3286 oluşturur ve ayrıca doğru kullanımını gösterir.  
  
```cpp  
// C3286.cpp  
// compile with: /clr  
int main() {  
   array<int> ^p = { 1, 2, 3 };  
   for each (static int i in p) {}   // C3286   
   for each (int j in p) {}   // OK  
}  
```