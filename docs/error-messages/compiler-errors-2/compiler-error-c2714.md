---
title: Derleyici Hatası C2714 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2714
dev_langs:
- C++
helpviewer_keywords:
- C2714
ms.assetid: 401a5a42-660c-4bad-9d63-1a2d092bc489
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8a5a8a2157fc574b9a43688bfc8fa9adcbcb676f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46108501"
---
# <a name="compiler-error-c2714"></a>Derleyici Hatası C2714

__alignof(void) izin verilmiyor

Geçersiz bir değer için bir işleç geçirildi.

Bkz: [__alignof işleci](../../cpp/alignof-operator.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2714 oluşturur.

```
// C2714.cpp
int main() {
   return __alignof(void);   // C2714
   return __alignof(char);   // OK
}
```