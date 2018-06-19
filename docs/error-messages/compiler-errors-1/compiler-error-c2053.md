---
title: Derleyici Hatası C2053 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2053
dev_langs:
- C++
helpviewer_keywords:
- C2053
ms.assetid: 13324c85-13a8-4996-bd42-a31bfe7ff80f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ace887e096ca0761f08843a033dc6391cb26aa99
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33165301"
---
# <a name="compiler-error-c2053"></a>Derleyici Hatası C2053
'tanımlayıcısı': geniş dize uyuşmazlığı  
  
 Geniş dizesi uyumsuz bir tür atanır.  
  
 Aşağıdaki örnek C2053 oluşturur:  
  
```  
// C2053.c  
int main() {  
   char array[] = L"Rika";   // C2053  
}  
```