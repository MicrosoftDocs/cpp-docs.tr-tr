---
title: Derleyici Hatası C3176 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3176
dev_langs:
- C++
helpviewer_keywords:
- C3176
ms.assetid: 6cc8d602-8e15-47a7-b1b5-e93e5d50e271
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aa2ec269061531688620b89279a9670982c72578
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104199"
---
# <a name="compiler-error-c3176"></a>Derleyici Hatası C3176

'type': yerel değer türünün bildirimi yapılamıyor

Bir sınıf yalnızca genel kapsamda bir değer türü olarak bildirilebilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3176 oluşturur.

```
// C3176.cpp
// compile with: /clr
int main () {
   enum class C {};   // C3176
}
```