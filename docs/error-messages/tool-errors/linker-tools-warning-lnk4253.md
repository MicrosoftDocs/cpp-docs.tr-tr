---
title: Bağlayıcı Araçları Uyarısı LNK4253
ms.date: 11/04/2016
f1_keywords:
- LNK4253
helpviewer_keywords:
- LNK4253
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
ms.openlocfilehash: c3f45880571e5c06f76d5f063ff993e2f6b2be9b
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988089"
---
# <a name="linker-tools-warning-lnk4253"></a>Bağlayıcı Araçları Uyarısı LNK4253

' Section1 ' bölümü ' section2 ' ile birleştirilmedi; zaten ' section3 ' ile birleştirildi

Bağlayıcı birden çok, çakışan birleştirme isteği algıladı. Bağlayıcı isteklerden birini yok sayacaktır.

Bir **/merge** seçeneği veya yönergesine rastlandı ve daha önce bir **/merge** seçeneği veya yönergesi (ya da bağlayıcıdan dolaylı bir birleştirme nedeniyle) nedeniyle `from` bölümü zaten farklı bir bölümle birleştirildi.

LNK4253 çözümlemek için, birleştirme isteklerinden birini kaldırın.

X86 makinelerini ve Windows CE hedeflerini hedeflerken (ARM, MIPS, SH4 ve Thumb), Visual C++ile. CRT bölümü artık salt okunurdur. Kodunuz önceki davranışa bağımlıysa (. CRT bölümleri okuma/yazma), beklenmeyen bir davranış görebilirsiniz.

Daha fazla bilgi için bkz.,

- [/MERGE (Bölümleri Birleştir)](../../build/reference/merge-combine-sections.md)

- [comment (C/C++)](../../preprocessor/comment-c-cpp.md)

## <a name="example"></a>Örnek

Aşağıdaki örnekte, bağlayıcının `.rdata` bölümünü iki kez birleştirmek, ancak farklı bölümlerde olması talimatı vardır. Aşağıdaki örnek LNK4253 oluşturur.

```cpp
// LNK4253.cpp
// compile with: /W1 /link /merge:.rdata=text2
// LNK4253 expected
#pragma comment(linker, "/merge:.rdata=.text")
int main() {}
```
