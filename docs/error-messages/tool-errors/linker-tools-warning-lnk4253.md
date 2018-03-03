---
title: "Bağlayıcı araçları uyarısı LNK4253 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4253
dev_langs:
- C++
helpviewer_keywords:
- LNK4253
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6d1142544852980b8bd1d543783a9ffdf3361879
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4253"></a>Bağlayıcı Araçları Uyarısı LNK4253
Bölüm 'Bölümü1 birleştirilmedi 'section2 ';' zaten 'section3 ' birleştirilmiş  
  
 Bağlayıcı birden çok, algılanan çakışan birleştirme ister. Bağlayıcı istekleri birini göz ardı eder.  
  
 A **/birleştirme** seçeneği veya yönergesi ile karşılaştı ve `from` bölümü zaten birleştirildi önceki nedeniyle farklı bir bölüme **/birleştirme** seçeneği veya yönergesi (veya nedeniyle örtük bir birleştirme Bağlayıcı).  
  
 LNK4253 çözümlemek için birleştirme isteği birini kaldırın.  
  
 X86 hedeflerken makineler ve Visual C++ ile Windows CE hedefleri (ARM, MIPS, SH4 ve Flash). CRT bölümü artık salt okunur. Kodunuzu önceki davranışı bağımlıysa (. CRT bölümleridir okuma/yazma), beklenmeyen davranışları görebilir.  
  
 Daha fazla bilgi için bkz:  
  
-   [/ MERGE (bölümleri Birleştir)](../../build/reference/merge-combine-sections.md)  
  
-   [comment (C/C++)](../../preprocessor/comment-c-cpp.md)  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, birleştirme için bağlayıcı talimat `.rdata` iki kez ancak farklı bölümlere bölüm. Aşağıdaki örnek LNK4253 oluşturur.  
  
```  
// LNK4253.cpp  
// compile with: /W1 /link /merge:.rdata=text2  
// LNK4253 expected  
#pragma comment(linker, "/merge:.rdata=.text")  
int main() {}  
```