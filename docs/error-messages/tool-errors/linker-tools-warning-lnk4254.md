---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları uyarısı LNK4254'
title: Bağlayıcı Araçları Uyarısı LNK4254
ms.date: 11/04/2016
f1_keywords:
- LNK4254
helpviewer_keywords:
- LNK4254
ms.assetid: 6f41dfb3-ca21-40d3-bac7-b637e578efa4
ms.openlocfilehash: 410a904af6af2015a817ac9e254dff7f09811b72
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244478"
---
# <a name="linker-tools-warning-lnk4254"></a>Bağlayıcı Araçları Uyarısı LNK4254

' Section1 ' bölümü (fark) farklı özniteliklerle ' section2 ' (fark) ile birleştirildi

Bir bölümün içeriği birbiriyle birleştirildi, ancak iki bölümün öznitelikleri farklı. Programınız beklenmedik sonuçlara neden olabilir. Örneğin, okumak istediğiniz veriler artık yazılabilir bir bölümde bulunabilir.

LNK4254 çözümlemek için birleştirme isteğini değiştirin veya kaldırın.

X86 makinelerini ve Windows CE hedeflerini (ARM, MIPS, SH4 ve Thumb) hedeflerken, Visual C++. CRT bölüm salt okunurdur. Kodunuz önceki davranışa bağımlıysa (. CRT bölümleri okuma/yazma), beklenmeyen bir davranış görebilirsiniz.

Daha fazla bilgi için bkz.,

- [/MERGE (bölümleri Birleştir)](../../build/reference/merge-combine-sections.md)

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
