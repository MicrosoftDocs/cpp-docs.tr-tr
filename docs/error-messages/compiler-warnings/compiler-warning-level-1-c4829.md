---
title: "Derleyici Uyarısı (düzey 1) C4829 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4829
dev_langs:
- C++
helpviewer_keywords:
- C4829
ms.assetid: 4ffabe2b-2ddc-4c52-8564-d1355c93cfa6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5d662aaf24526320c0ced706534099d4c94a3c9f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4829"></a>Derleyici Uyarısı (düzey 1) C4829
Büyük olasılıkla yanlış parametreler ana işlevi. Göz önünde bulundurun ' intmain (Platform::Array\<Platform::String ^ > ^ argv)'  
  
 Belirli işlevler ana gibi başvuru türü parametreleri alamıyor. Derleme başarılı olur, ancak elde edilen görüntü çalıştırın olmayabilir.  
  
 Aşağıdaki örnek C4829 oluşturur:  
  
```  
// C4829.cpp  
// compile by using: cl /EHsc /ZW /W4 /c C4829.cpp  
int main(Platform::String ^ s) {}   // C4829  
  
```