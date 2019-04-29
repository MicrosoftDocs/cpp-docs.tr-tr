---
title: Derleyici Hatası C3387
ms.date: 11/04/2016
f1_keywords:
- C3387
helpviewer_keywords:
- C3387
ms.assetid: c54d9925-ed14-4976-b8db-e8d4dc84e536
ms.openlocfilehash: bd783d9510b1699b33f108a4ce8d8c491028b758
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328711"
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