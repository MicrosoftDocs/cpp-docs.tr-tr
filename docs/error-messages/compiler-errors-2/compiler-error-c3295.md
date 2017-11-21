---
title: "Derleyici Hatası C3295 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3295
dev_langs: C++
helpviewer_keywords: C3295
ms.assetid: 83f0aa4d-0e0a-4905-9f66-fcf9991fc07a
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b72e4839341006d2058c21a1523b0d7567f51696
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3295"></a>Derleyici Hatası C3295
'#pragma pragma' yalnızca kullanılabilir genel veya ad alanı kapsamı  
  
 Bazı pragmaları bir işlevi kullanılamaz.  Bkz: [Pragma yönergeleri ve __Pragma anahtar sözcüğü](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) daha fazla bilgi için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3295 oluşturur.  
  
```  
// C3295.cpp  
int main() {  
   #pragma managed   // C3295  
}  
```