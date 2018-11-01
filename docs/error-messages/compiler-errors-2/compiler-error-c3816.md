---
title: Derleyici Hatası C3816
ms.date: 11/04/2016
f1_keywords:
- C3816
helpviewer_keywords:
- C3816
ms.assetid: 2e52cc7f-e31c-41a3-8d6f-9f5fab3648c0
ms.openlocfilehash: d362480b3380fe4576ef56b8ca76dfa10eaa1408
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50557306"
---
# <a name="compiler-error-c3816"></a>Derleyici Hatası C3816

'bildirim' daha önce bildirilen veya farklı bir yönetilen veya WinRTmodifier ile tanımlanan

İleri dönük bildirimi ve bir gerçek bildirimi gerektiren herhangi bir çakışma veya öznitelikleri bildirimi tutarsızlıklar olması.

Aşağıdaki örnek, C3816 oluşturur ve bu sorunun nasıl gösterir:

```
// C3816a.cpp
// compile with: /clr /c
class C1;
// try the following line instead
// ref class C1;

ref class C1{  // C3816, forward declaration does not use ref
};
```