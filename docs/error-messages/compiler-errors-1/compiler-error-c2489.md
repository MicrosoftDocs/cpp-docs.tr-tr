---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2489'
title: Derleyici hatası C2489
ms.date: 11/04/2016
f1_keywords:
- C2489
helpviewer_keywords:
- C2489
ms.assetid: 67d8cd98-db7e-4f7f-86b4-4af7bc89ec8b
ms.openlocfilehash: 21e7a935ee3cf9c0dc1aa886b94ada931fbb64ca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305409"
---
# <a name="compiler-error-c2489"></a>Derleyici hatası C2489

' tanımlayıcı ': başlatılan otomatik veya yazmaç değişkenine ' Naked ' işlevindeki işlev kapsamında izin verilmiyor

Daha fazla bilgi için bkz. [Naked](../../cpp/naked-cpp.md).

Aşağıdaki örnek C2489 oluşturur:

```cpp
// C2489.cpp
// processor: x86
__declspec( naked ) int func() {
   int i = 1;   // C2489
   register int j = 1;   // C2489
}
```
