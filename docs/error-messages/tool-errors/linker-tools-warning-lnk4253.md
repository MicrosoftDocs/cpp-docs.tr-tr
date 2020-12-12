---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları uyarısı LNK4253'
title: Bağlayıcı Araçları Uyarısı LNK4253
ms.date: 11/04/2016
f1_keywords:
- LNK4253
helpviewer_keywords:
- LNK4253
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
ms.openlocfilehash: 764d7698da8d724842b8387c9c4356bfce951079
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244494"
---
# <a name="linker-tools-warning-lnk4253"></a>Bağlayıcı Araçları Uyarısı LNK4253

' Section1 ' bölümü ' section2 ' ile birleştirilmedi; zaten ' section3 ' ile birleştirildi

Bağlayıcı birden çok, çakışan birleştirme isteği algıladı. Bağlayıcı isteklerden birini yok sayacaktır.

Bir **/merge** seçeneği veya yönergesine rastlandı ve `from` bölüm, önceki **/merge** seçeneği veya yönergesi nedeniyle (veya bağlayıcıdan örtük bir birleştirme nedeniyle) farklı bir bölüm ile birleştirildi.

LNK4253 çözümlemek için, birleştirme isteklerinden birini kaldırın.

X86 makinelerini ve Windows CE hedeflerini (ARM, MIPS, SH4 ve Thumb) hedeflerken, Visual C++. CRT bölümü artık salt okunurdur. Kodunuz önceki davranışa bağımlıysa (. CRT bölümleri okuma/yazma), beklenmeyen bir davranış görebilirsiniz.

Daha fazla bilgi için bkz.,

- [/MERGE (bölümleri Birleştir)](../../build/reference/merge-combine-sections.md)

- [comment (C/C++)](../../preprocessor/comment-c-cpp.md)

## <a name="example"></a>Örnek

Aşağıdaki örnekte, bağlayıcının `.rdata` bölümü iki kez birleştirmek istendi ve farklı bölümler. Aşağıdaki örnek LNK4253 oluşturur.

```cpp
// LNK4253.cpp
// compile with: /W1 /link /merge:.rdata=text2
// LNK4253 expected
#pragma comment(linker, "/merge:.rdata=.text")
int main() {}
```
