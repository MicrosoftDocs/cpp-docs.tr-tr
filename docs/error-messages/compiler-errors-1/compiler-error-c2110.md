---
title: "Derleyici Hatası C2110 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2110
dev_langs: C++
helpviewer_keywords: C2110
ms.assetid: 48fd76ed-90d6-4a60-9c7b-f6ce9355b4ca
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d43975aea670c695faeb3869517de7b216b0a15d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2110"></a>Derleyici Hatası C2110
'+': iki işaretçisi ekleyemezsiniz  
  
 Artı kullanarak iki işaretçi değerleri eklemek için girişimde bulunuldu ( `+` ) işleci.  
  
 Aşağıdaki örnek C2110 oluşturur:  
  
```  
// C2110.cpp  
int main() {  
   int a = 0;  
   int *pa;  
   int *pb;  
   a = pa + pb;   // C2110  
}  
```