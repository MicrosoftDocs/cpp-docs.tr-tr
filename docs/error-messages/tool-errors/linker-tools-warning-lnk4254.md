---
title: Bağlayıcı araçları uyarısı LNK4254 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4254
dev_langs:
- C++
helpviewer_keywords:
- LNK4254
ms.assetid: 6f41dfb3-ca21-40d3-bac7-b637e578efa4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb57882ab4269c06a53ed73fed2a9d6caf2f2c85
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33316900"
---
# <a name="linker-tools-warning-lnk4254"></a>Bağlayıcı Araçları Uyarısı LNK4254
Bölüm 'Bölümü1' (uzaklık) birleştirilmiş 'section2 ' (farklı özniteliklerle uzaklığı).  
  
 Bir bölümün içeriğini başka bir dosyaya birleştirilen, ancak iki bölüm özniteliklerini farklıdır. Programınız beklenmedik sonuçlar verebilir. Örneğin, okunması istemeniz veriler yalnızca şimdi yazılabilir bir bölümü olabilir.  
  
 LNK4254 gidermek için değiştirmek veya birleştirme isteği kaldırın.  
  
 X86 hedeflerken makineler ve Visual C++ ile Windows CE hedefleri (ARM, MIPS, SH4 ve Flash). CRT bölümü salt okunurdur. Kodunuzu önceki davranışı bağımlıysa (. CRT bölümleridir okuma/yazma), beklenmeyen davranışları görebilir.  
  
 Daha fazla bilgi için bkz:  
  
-   [/MERGE (Bölümleri Birleştir)](../../build/reference/merge-combine-sections.md)  
  
-   [comment (C/C++)](../../preprocessor/comment-c-cpp.md)  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek LNK4254 oluşturur.  
  
```  
// LNK4254.cpp  
// compile with: /W1 /link /WX  
// LNK4254 expected  
#pragma comment(linker, "/merge:.data=.text")  
int main() {}  
```