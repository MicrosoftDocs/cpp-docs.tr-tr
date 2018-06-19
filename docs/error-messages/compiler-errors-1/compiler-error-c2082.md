---
title: Derleyici Hatası C2082 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2082
dev_langs:
- C++
helpviewer_keywords:
- C2082
ms.assetid: 87a6d442-157c-46e8-9bff-8388f8338ae0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbbaa7f59b8853dd1b1ad0f2e839b00086db8eac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33172056"
---
# <a name="compiler-error-c2082"></a>Derleyici Hatası C2082
biçimsel parametresi 'tanımlayıcısı' yeniden tanımlama  
  
 Bir çalışması biçimsel parametresi, işlev gövdesi içinde yeniden bildirilen. Hatayı gidermek için yeniden tanımlama kaldırın.  
  
 Aşağıdaki örnek C2082 oluşturur:  
  
```  
// C2082.cpp  
void func(int i) {  
   int i;   // C2082  
   int ii;   // OK  
}  
```