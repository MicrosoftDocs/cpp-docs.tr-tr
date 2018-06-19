---
title: Derleyici Hatası C2109 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2109
dev_langs:
- C++
helpviewer_keywords:
- C2109
ms.assetid: 2d1ac79d-a985-4904-a38b-b270578d664d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e2cb488bca97fa88c58a82b6404ff2845ef65b5d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33166019"
---
# <a name="compiler-error-c2109"></a>Derleyici Hatası C2109
alt simge dizi veya işaretçi türü gerektirir  
  
 Alt simge bir dizi değildi bir değişken kullanıldı.  
  
 Aşağıdaki örnek C2109 oluşturur:  
  
```  
// C2109.cpp  
int main() {  
   int a, b[10] = {0};  
   a[0] = 1;   // C2109  
   b[0] = 1;   // OK  
}  
```