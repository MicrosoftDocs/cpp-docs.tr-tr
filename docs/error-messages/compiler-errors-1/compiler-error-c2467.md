---
title: Derleyici Hatası C2467 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2467
dev_langs:
- C++
helpviewer_keywords:
- C2467
ms.assetid: f9ead270-5d0b-41cc-bdcd-586a647c67a7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8bab320bfdba9fcbd408771b7859a22fc85fa06e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048781"
---
# <a name="compiler-error-c2467"></a>Derleyici Hatası C2467

Anonim 'kullanıcı tanımlı-tür' bildirimi geçersiz

İç içe geçmiş bir kullanıcı tanımlı tür bildirildi. Bu C kaynak kodu ANSI uyumluluk seçeneği ile derleme yapılırken bir hata olduğunu ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) etkin.

Aşağıdaki örnek, C2467 oluşturur:

```
//C2467.c
// compile with: /Za
int main() {
   struct X {
      union { int i; };   // C2467, nested declaration
   };
}
```