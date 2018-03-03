---
title: "Derleyici Uyarısı (düzey 1) C4288 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4288
dev_langs:
- C++
helpviewer_keywords:
- C4288
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a10a7573df5986ed20475b34208a1e0f301d9bb9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4288"></a>Derleyici Uyarısı (düzey 1) C4288
kullanılan standart olmayan uzantısı: 'var': for döngüsü denetim değişkeni için-döngüde bildirilen for döngüsü kapsamı dışındadır; kullanılır Dış kapsamdaki bildirimiyle çakışıyor  
  
 İle derleme yapılırken [/Ze](../../build/reference/za-ze-disable-language-extensions.md) ve **/Zc:forscope-**, bildirilen bir değişken bir **için** döngü sonra kullanıldı [için](../../cpp/for-statement-cpp.md)-döngü kapsamı. C++ dili için bir Microsoft uzantısı kapsamda kalması bu değişkeni sağlar ve C4288 değişkeni ilk bildirimi kullanılmaz anımsatır.  
  
 Bkz: [/ZC: forscope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md) Microsoft uzantısı'nda belirtme hakkında bilgi için **için** döngüleri /Ze ile.  
  
 Aşağıdaki örnek C4288 oluşturur:  
  
```  
// C4288.cpp  
// compile with: /W1 /c /Zc:forScope-  
int main() {  
   int i = 0;    // not used in this program  
   for (int i = 0 ; ; ) ;  
   i++;   // C4288 using for-loop declaration of i  
}  
```