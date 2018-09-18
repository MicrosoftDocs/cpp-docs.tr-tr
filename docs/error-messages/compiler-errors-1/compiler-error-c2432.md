---
title: Derleyici Hatası C2432 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2432
dev_langs:
- C++
helpviewer_keywords:
- C2432
ms.assetid: 0e3326e8-cab1-45a5-b48d-61edd33793e8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9ca8c2c62415b6ec3c29c820a23677a87a2695c5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055916"
---
# <a name="compiler-error-c2432"></a>Derleyici Hatası C2432

'identifier' içinde 16-bit verilere geçersiz başvuru

Bir 16-bit kayıt temel kaydettirmeye veya bir dizin kullanılır. Derleyici, 16-bit verilere başvurma desteklemez. 16-bit kayıtlarını dizini veya temel kasa için 32-bit kod derlenirken kullanılamaz.

Aşağıdaki örnek, C2432 oluşturur:

```
// C2432.cpp
// processor: x86
int main() {
   _asm mov eax, DWORD PTR [bx]   // C2432
}
```