---
title: "Derleyici Hatası C2879 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2879
dev_langs: C++
helpviewer_keywords: C2879
ms.assetid: ac92b645-2394-49de-8632-43d44e0553ed
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4bb972ffa8bee016dd158490d123353bd6f46a8e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2879"></a>Derleyici Hatası C2879
'simgesi': varolan bir ad bir diğer ad ad alanı diğer ad tanımı verilebilir yalnızca  
  
 Oluşturamazsınız bir [ad alanı diğer adı](../../cpp/namespaces-cpp.md#namespace_aliases) için bir ad alanı dışında bir simge.  
  
 Aşağıdaki örnek C2879 oluşturur:  
  
```  
// C2879.cpp  
int main() {  
   int i;  
   namespace A = i;   // C2879 i is not a namespace  
}  
```