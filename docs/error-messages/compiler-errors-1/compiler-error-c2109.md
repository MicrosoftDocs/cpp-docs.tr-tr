---
title: Derleyici Hatası C2109 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2109
dev_langs:
- C++
helpviewer_keywords:
- C2109
ms.assetid: 2d1ac79d-a985-4904-a38b-b270578d664d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 551c391c67e54c00a26fe6c11fb062adcb9c2f30
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46100800"
---
# <a name="compiler-error-c2109"></a>Derleyici Hatası C2109

alt simge dizi veya işaretçi türü gereklidir

Alt simge dizisi değil bir değişken üzerinde kullanıldı.

Aşağıdaki örnek, C2109 oluşturur:

```
// C2109.cpp
int main() {
   int a, b[10] = {0};
   a[0] = 1;   // C2109
   b[0] = 1;   // OK
}
```