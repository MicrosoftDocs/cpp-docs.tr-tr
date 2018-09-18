---
title: Derleyici Hatası C2513 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2513
dev_langs:
- C++
helpviewer_keywords:
- C2513
ms.assetid: ab5b21d3-61e2-4df7-8eea-6f14d6ba8620
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82df537e49ca17140d70977486314f43a072022d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045438"
---
# <a name="compiler-error-c2513"></a>Derleyici Hatası C2513

'type': hiçbir değişken bildirimi '=' öncesinde

Tür tanımlayıcısına sahip hiçbir değişken tanımlayıcının bildirimini görüntülenir.

Aşağıdaki örnek, C2513 oluşturur:

```
// C2513.cpp
int main() {
   int = 9;   // C2513
   int i = 9;   // OK
}
```

Bu hata, Visual Studio .NET 2003'te yapılan bir derleyici uyumluluğu iş sonucu olarak da oluşturulabilir: başlatma artık izin verilen bir TypeDef. Bir TypeDef başlatma standart tarafından izin verilmiyor ve artık bir derleyici hatasına neden olur.

```
// C2513b.cpp
// compile with: /c
typedef struct S {
   int m_i;
} S = { 1 };   // C2513
// try the following line instead
// } S;
```

Silmek için bir alternatif olabilir `typedef` bu tür olarak aynı ada sahip bir değişken oluşturun ve tür adı gizlemek için toplu başlatıcı listesi, ancak bu bir değişkeni tanımlamak için önerilmez.