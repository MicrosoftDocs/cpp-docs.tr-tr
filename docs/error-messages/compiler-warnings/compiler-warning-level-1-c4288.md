---
title: Derleyici Uyarısı (düzey 1) C4288 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4288
dev_langs:
- C++
helpviewer_keywords:
- C4288
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f2c51bdc201b364d76f1692db8ee14973c90923f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33276636"
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