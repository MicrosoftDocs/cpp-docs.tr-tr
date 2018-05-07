---
title: Bağlayıcı araçları uyarısı LNK4253 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4253
dev_langs:
- C++
helpviewer_keywords:
- LNK4253
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bae4e88e1fe1434cd638d5c31cc8fd4d5c02c4de
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4253"></a>Bağlayıcı Araçları Uyarısı LNK4253
Bölüm 'Bölümü1 birleştirilmedi 'section2 ';' zaten 'section3 ' birleştirilmiş  
  
 Bağlayıcı birden çok, algılanan çakışan birleştirme ister. Bağlayıcı istekleri birini göz ardı eder.  
  
 A **/birleştirme** seçeneği veya yönergesi ile karşılaştı ve `from` bölümü zaten birleştirildi önceki nedeniyle farklı bir bölüme **/birleştirme** seçeneği veya yönergesi (veya nedeniyle örtük bir birleştirme Bağlayıcı).  
  
 LNK4253 çözümlemek için birleştirme isteği birini kaldırın.  
  
 X86 hedeflerken makineler ve Visual C++ ile Windows CE hedefleri (ARM, MIPS, SH4 ve Flash). CRT bölümü artık salt okunur. Kodunuzu önceki davranışı bağımlıysa (. CRT bölümleridir okuma/yazma), beklenmeyen davranışları görebilir.  
  
 Daha fazla bilgi için bkz:  
  
-   [/MERGE (Bölümleri Birleştir)](../../build/reference/merge-combine-sections.md)  
  
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