---
title: "Derleyici Uyarısı (Düzey 3) C4316 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4316
dev_langs: C++
helpviewer_keywords: C4316
ms.assetid: 10371f01-aeb8-40ac-a290-59e63efa5ad4
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0a36f436090ef7ca3790f4bd5dd15443c0ed52f9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4316"></a>Derleyici Uyarısı (Düzey 3) C4316
Yığında ayrılmış nesne bu tür için hizalı değil.  
  
 Aşırı hizalanmış nesneyi kullanarak ayrılan `operator new` belirtilen hizalama olmayabilir. Geçersiz kılma [new işleci](../../c-runtime-library/operator-new-crt.md) ve [delete işleci](../../c-runtime-library/operator-delete-crt.md) için aşırı hizalı türleri hizalanmış ayırma yordamları kullanmasını sağlayarak — Örneğin, [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) ve [_aligned_free](../../c-runtime-library/reference/aligned-free.md). Aşağıdaki örnek C4316 oluşturur:  
  
```cpp  
// C4316.cpp  
// Test: cl /W3 /c C4316.cpp  
  
__declspec(align(32)) struct S {}; // C4324  
  
int main() {  
    new S; // C4316  
}  
```