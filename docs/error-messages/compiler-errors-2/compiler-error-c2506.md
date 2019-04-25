---
title: Derleyici Hatası C2506
ms.date: 11/04/2016
f1_keywords:
- C2506
helpviewer_keywords:
- C2506
ms.assetid: cfed21cd-2404-46f2-985e-d0c2c3820830
ms.openlocfilehash: 02f0a81204c4bc1c41111d32bae1c6946dee09ac
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62164871"
---
# <a name="compiler-error-c2506"></a>Derleyici Hatası C2506

'member': '__declspec(modifier)' bu simgeye uygulanamaz

Statik bir yönetilen sınıf üyeleri için işlem içi appdomain başına bildiremezsiniz.

Bkz: [appdomain](../../cpp/appdomain.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2506 oluşturur.

```
// C2506.cpp
// compile with: /clr /c
ref struct R {
   __declspec(process) static int n;   // C2506
   int o;   // OK
};
```