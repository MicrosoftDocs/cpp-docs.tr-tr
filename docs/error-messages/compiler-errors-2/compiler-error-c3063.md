---
title: "Derleyici Hatası C3063 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3063
dev_langs: C++
helpviewer_keywords: C3063
ms.assetid: 0ecf6f1f-e4a7-487a-9fd5-79d8ac470001
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 26d30e56c3e694b39f583b29d8bd378b6dcaee0f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3063"></a>Derleyici Hatası C3063
operator 'işleci: tüm işlenenleri aynı numaralandırma türü olmalıdır  
  
İşleçler hakkında numaralandırıcılar kullanırken, her iki işlenen numaralandırma türü olmalıdır. Daha fazla bilgi için bkz: [nasıl yapılır: C + numaralandırmaları tanımlama ve kullanma +/ CLI](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md).  
  
## <a name="example"></a>Örnek  
Aşağıdaki örnek C3063 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C3063.cpp  
// compile with: /clr  
enum class E { a, b } e, mask;  
int main() {  
   if ( ( e & mask ) != 0 ) ;   // C3063 no operator!= (E, int)  
  
   if ( ( e & mask ) != E() )   // OK  
      ;  
}  
```