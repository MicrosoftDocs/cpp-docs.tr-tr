---
title: Derleyici Hatası C2180 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2180
dev_langs:
- C++
helpviewer_keywords:
- C2180
ms.assetid: ea71b39e-b977-48a7-b7bd-af68ef5e263b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a43c179b837e840f800a6c468efdd9cdd6a6604b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33171542"
---
# <a name="compiler-error-c2180"></a>Derleyici Hatası C2180
türü 'type' sahip ifade denetleme  
  
 Denetleme ifadesinde bir `if`, `while`, `for`, veya `do` açıklamadır için bir ifade `void`. Bu sorunu gidermek için denetleme ifade üreten değiştirin bir `bool` veya dönüştürülebilir bir türü `bool`.  
  
 Aşağıdaki örnek C2180 oluşturur:  
  
```  
// C2180.c  
  
int main() {  
   while ((void)1)   // C2180  
      return 1;  
   while (1)         // OK  
      return 0;  
}  
```