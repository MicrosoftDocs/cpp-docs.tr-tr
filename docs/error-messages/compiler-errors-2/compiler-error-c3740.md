---
title: Derleyici Hatası C3740 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3740
dev_langs:
- C++
helpviewer_keywords:
- C3740
ms.assetid: edb17a90-2307-4df6-943d-580460d26d2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6bda1392ae4ebe95c6038b8dd0ec322b32ba4d8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044203"
---
# <a name="compiler-error-c3740"></a>Derleyici Hatası C3740

Şablon kaynağı veya olayları alma

Bir şablonlu sınıfın veya yapının içeremez [olayları](../../cpp/event-handling.md).

Aşağıdaki örnek, C3740 oluşturur:

```
// C3740.cpp
template <typename T>   // Delete the template specification
struct E {
   __event void f();   // C3740
};

int main() {
}
```