---
title: Derleyici Hatası C3387 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3387
dev_langs:
- C++
helpviewer_keywords:
- C3387
ms.assetid: c54d9925-ed14-4976-b8db-e8d4dc84e536
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0dafe972db1b3210e9243e34cc02e7a0366bdd65
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030761"
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