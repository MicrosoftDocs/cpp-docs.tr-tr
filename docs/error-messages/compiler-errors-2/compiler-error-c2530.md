---
title: Derleyici Hatası C2530 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2530
dev_langs:
- C++
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f41f9ec64e2074ed5e0cd2654f2b6bfec886bc07
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46103201"
---
# <a name="compiler-error-c2530"></a>Derleyici Hatası C2530

'identifier': başvuruların başlatılması gerekir

Bunu bildirildi, zaten bildirildiği sürece bir başvuruyu başlatmak gerekir:

- Anahtar sözcüğü ile [extern](../../cpp/using-extern-to-specify-linkage.md).

- Bir sınıf, yapı veya birleşim üyesi olarak (ve oluşturucuda başlatılır).

- Bir işlev bildirimini veya tanımını parametre olarak.

- Bir işlevin dönüş türü olarak.

Aşağıdaki örnek, C2530 oluşturur:

```
// C2530.cpp
int main() {
   int i = 0;
   int &j;   // C2530
   int &k = i;   // OK
}
```