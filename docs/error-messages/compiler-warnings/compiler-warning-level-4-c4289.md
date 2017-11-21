---
title: "Derleyici Uyarısı (düzey 4) C4289 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4289
dev_langs: C++
helpviewer_keywords: C4289
ms.assetid: 0dbd2863-4cde-4e16-894b-104a2d5fa724
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6e3d37052f5b88d01daa882f0a0ea799bb799cdc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4289"></a>Derleyici Uyarısı (düzey 4) C4289
standart olmayan uzantı kullanıldı : 'var': for döngüsünde bildirimi yapılan döngü denetim değişkeni for döngüsü kapsamının dışında kullanılıyor  
  
 İle derleme yapılırken [/Ze](../../build/reference/za-ze-disable-language-extensions.md) ve **/Zc:forScope-**, bildirilen bir değişken bir [için](../../cpp/for-statement-cpp.md) döngü sonra kullanıldı **için**-döngü kapsamı.  
  
 Bkz: [/ZC: forscope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) standart davranışını belirtme hakkında bilgi için **için** ile döngü **/Ze**.  
  
 Varsayılan olarak bu uyarı kapalıdır. Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.  
  
 Aşağıdaki örnek C4289 oluşturur:  
  
```  
// C4289.cpp  
// compile with: /W4 /Zc:forScope-  
#pragma warning(default:4289)  
int main() {  
   for (int i = 0 ; ; )   // C4289  
      break;  
   i++;  
}  
```