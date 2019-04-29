---
title: Bağlayıcı Araçları Uyarısı LNK4254
ms.date: 11/04/2016
f1_keywords:
- LNK4254
helpviewer_keywords:
- LNK4254
ms.assetid: 6f41dfb3-ca21-40d3-bac7-b637e578efa4
ms.openlocfilehash: 2c68e49d58b0fd6b28607eb0ba78c092441f6f4b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352495"
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