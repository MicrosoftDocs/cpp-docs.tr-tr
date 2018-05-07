---
title: Derleyici Uyarısı (düzey 1) C4142 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4142
dev_langs:
- C++
helpviewer_keywords:
- C4142
ms.assetid: 1fdfc3dc-60a2-4f00-b133-20e400f9b7a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c87b7689cf11ab28c1a6377ff85e1594fd1b5fc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4142"></a>Derleyici Uyarısı (düzey 1) C4142
türü zararsız yeniden tanımlama  
  
 Oluşturulan kod üzerinde hiçbir etkisi olmaz bir şekilde bir tür tanımlandı.  
  
 Aşağıdaki olası nedenleri kontrol ederek düzeltmek için:  
  
-   Üye işlevi türetilmiş bir sınıfın temel sınıfın karşılık gelen üye işlevden farklı dönüş türü olan.  
  
-   İle tanımlanan bir türü `typedef` komutu yeniden tanımlandı farklı söz dizimini kullanarak.  
  
 Aşağıdaki örnek C4142 oluşturur:  
  
```  
// C4142.c  
// compile with: /W1  
float X2;  
X2 = 2.0 + 1.0;   // C4142  
  
int main() {  
   float X2;  
   X2 = 2.0 + 1.0;   // OK  
}  
```