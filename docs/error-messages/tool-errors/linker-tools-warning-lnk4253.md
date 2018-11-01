---
title: Bağlayıcı Araçları Uyarısı LNK4253
ms.date: 11/04/2016
f1_keywords:
- LNK4253
helpviewer_keywords:
- LNK4253
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
ms.openlocfilehash: d2fd7238a3f57b11b91813bd40b66cb3e9f47202
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628832"
---
# <a name="linker-tools-warning-lnk4253"></a>Bağlayıcı Araçları Uyarısı LNK4253

Bölüm 'Bölümü1 birleştirilmeyen 'section2 ';' zaten 'section3' birleştirilmiş

Bağlayıcı birden çok, algılanan çakışan birleştirme ister. Bağlayıcı isteklerden birini göz ardı eder.

A **/MERGE** seçeneği veya yönergesi ile karşılaştı ve `from` bölümü zaten birleştirilmiştir önceki nedeniyle farklı bir bölüme **/MERGE** seçeneği veya yönergesi (veya bir örtük birleştirmeden nedeniyle Bağlayıcı).

LNK4253 çözmek için birleştirme isteklerden birini kaldırın.

X86 hedeflenirken makineler ve Visual C++ ile Windows CE hedefleri (ARM, MIPS, SH4 ve Flash). CRT bölümü artık salt okunur. Kodunuzu önceki davranışa bağlıysa (. CRT bölümleridir okuma/yazma), beklenmeyen davranışı görebilir.

Daha fazla bilgi için bkz:

- [/MERGE (Bölümleri Birleştir)](../../build/reference/merge-combine-sections.md)

- [comment (C/C++)](../../preprocessor/comment-c-cpp.md)

## <a name="example"></a>Örnek

Aşağıdaki örnekte, merge bağlayıcı bildirilmiştir `.rdata` iki kez ancak farklı bölümlere bölümü. Aşağıdaki örnek, LNK4253 oluşturur.

```
// LNK4253.cpp
// compile with: /W1 /link /merge:.rdata=text2
// LNK4253 expected
#pragma comment(linker, "/merge:.rdata=.text")
int main() {}
```