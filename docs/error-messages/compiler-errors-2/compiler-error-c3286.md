---
title: Derleyici Hatası C3286 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3286
dev_langs:
- C++
helpviewer_keywords:
- C3286
ms.assetid: 554328c8-cf44-4f7d-a8d2-def74d28ecdd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dc47c103e93fe1e4f20f5007c6688b5b6648bf32
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33248189"
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