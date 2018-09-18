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
ms.openlocfilehash: f2ef421cbfa87ecab8a27dfa796eaa4eaacf7b70
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064655"
---
# <a name="linker-tools-warning-lnk4254"></a>Bağlayıcı Araçları Uyarısı LNK4254

Bölüm 'Bölümü1' (kaydırma) 'section2' birleştirilmiş (farklı özniteliklerle uzaklık)

Bir bölümün içeriğini başka bir birleştirilen, ancak iki bölüm özniteliklerini farklıdır. Programınız, beklenmeyen sonuçlar verebilir. Örneğin, verileri okumak için istiyordu yalnızca artık yazılabilir bir bölümü olabilir.

LNK4254 gidermek için değiştirme veya birleştirme isteği kaldırın.

X86 hedeflenirken makineler ve Visual C++ ile Windows CE hedefleri (ARM, MIPS, SH4 ve Flash). CRT bölümü salt okunur. Kodunuzu önceki davranışa bağlıysa (. CRT bölümleridir okuma/yazma), beklenmeyen davranışı görebilir.

Daha fazla bilgi için bkz:

- [/MERGE (Bölümleri Birleştir)](../../build/reference/merge-combine-sections.md)

- [comment (C/C++)](../../preprocessor/comment-c-cpp.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek, LNK4254 oluşturur.

```
// LNK4254.cpp
// compile with: /W1 /link /WX
// LNK4254 expected
#pragma comment(linker, "/merge:.data=.text")
int main() {}
```