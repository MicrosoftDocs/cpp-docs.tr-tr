---
title: "Derleyici Hatası C2661 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2661
dev_langs: C++
helpviewer_keywords: C2661
ms.assetid: 60021467-71cd-451b-9877-23840c69309f
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 949d5289d0a2baf65ec00223f66f5eb4abfe0eea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2661"></a>Derleyici Hatası C2661
'function': aşırı yüklenmiş hiçbir işlev sayı parametreleri alır  
  
 Olası nedenler:  
  
1.  İşlev çağrısı yanlış gerçek parametrelerinde.  
  
2.  Eksik işlev bildirimi.  
  
 Aşağıdaki örnek C2661 oluşturur:  
  
```  
// C2661.cpp  
void func( int ){}  
void func( int, int ){}  
int main() {  
   func( );   // C2661 func( void ) was not declared  
   func( 1 );   // OK func( int ) was declared  
}  
```