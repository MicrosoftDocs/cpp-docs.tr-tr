---
title: Derleyici Hatası C3387
ms.date: 11/04/2016
f1_keywords:
- C3387
helpviewer_keywords:
- C3387
ms.assetid: c54d9925-ed14-4976-b8db-e8d4dc84e536
ms.openlocfilehash: bd783d9510b1699b33f108a4ce8d8c491028b758
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50541910"
---
# <a name="compiler-error-c3387"></a>Derleyici Hatası C3387

'member': __declspec(dllexport) /\__declspec(dllimport) bir yönetilen bir üyesi ya da WinRT türüne uygulanamaz

`dllimport` Ve [dllexport](../../cpp/dllexport-dllimport.md) `__declspec` değiştiriciler yönetilen üyeleri veya Windows çalışma zamanı türü geçerli değil.

Aşağıdaki örnek, C3387 oluşturur ve bu sorunun nasıl gösterir:

```
// C3387a.cpp
// compile with: /clr /c
ref class X2 {
   void __declspec(dllexport) mf() {   // C3387
   // try the following line instead
   // void mf() {
   }
};
```