---
title: Bağlayıcı Araçları Uyarısı LNK4254
ms.date: 11/04/2016
f1_keywords:
- LNK4254
helpviewer_keywords:
- LNK4254
ms.assetid: 6f41dfb3-ca21-40d3-bac7-b637e578efa4
ms.openlocfilehash: 8431bd2d89fd5df5cf076ad006ab04006f552c4c
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988065"
---
# <a name="linker-tools-warning-lnk4254"></a>Bağlayıcı Araçları Uyarısı LNK4254

' Section1 ' bölümü (fark) farklı özniteliklerle ' section2 ' (fark) ile birleştirildi

Bir bölümün içeriği birbiriyle birleştirildi, ancak iki bölümün öznitelikleri farklı. Programınız beklenmedik sonuçlara neden olabilir. Örneğin, okumak istediğiniz veriler artık yazılabilir bir bölümde bulunabilir.

LNK4254 çözümlemek için birleştirme isteğini değiştirin veya kaldırın.

X86 makinelerini ve Windows CE hedeflerini hedeflerken (ARM, MIPS, SH4 ve Thumb), Visual C++ile. CRT bölüm salt okunurdur. Kodunuz önceki davranışa bağımlıysa (. CRT bölümleri okuma/yazma), beklenmeyen bir davranış görebilirsiniz.

Daha fazla bilgi için bkz.,

- [/MERGE (Bölümleri Birleştir)](../../build/reference/merge-combine-sections.md)

- [comment (C/C++)](../../preprocessor/comment-c-cpp.md)

## <a name="example"></a>Örnek

Aşağıdaki örnek LNK4254 oluşturur.

```cpp
// LNK4254.cpp
// compile with: /W1 /link /WX
// LNK4254 expected
#pragma comment(linker, "/merge:.data=.text")
int main() {}
```
