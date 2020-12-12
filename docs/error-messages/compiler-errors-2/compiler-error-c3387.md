---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3387'
title: Derleyici hatası C3387
ms.date: 11/04/2016
f1_keywords:
- C3387
helpviewer_keywords:
- C3387
ms.assetid: c54d9925-ed14-4976-b8db-e8d4dc84e536
ms.openlocfilehash: febd47004026a7e22ca576c153ee8cf1506c3e1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285558"
---
# <a name="compiler-error-c3387"></a>Derleyici hatası C3387

' Member ': __declspec (dllexport)/ \_ _declspec (dllimport), yönetilen veya WinRT türünün bir üyesine uygulanamaz

`dllimport`Ve [dllexport](../../cpp/dllexport-dllimport.md) **`__declspec`** değiştiricileri, yönetilen veya Windows çalışma zamanı türünün üyelerinde geçerli değildir.

Aşağıdaki örnek C3387 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C3387a.cpp
// compile with: /clr /c
ref class X2 {
   void __declspec(dllexport) mf() {   // C3387
   // try the following line instead
   // void mf() {
   }
};
```
