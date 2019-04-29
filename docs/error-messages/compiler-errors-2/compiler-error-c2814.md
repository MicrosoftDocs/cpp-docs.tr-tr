---
title: Derleyici Hatası C2814
ms.date: 11/04/2016
f1_keywords:
- C2814
helpviewer_keywords:
- C2814
ms.assetid: 7d165136-a08b-4497-a76d-60a21bb19404
ms.openlocfilehash: 6562e8a0968f83a0e7e968b538b4d94dc1047fa5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62329562"
---
# <a name="compiler-error-c2814"></a>Derleyici Hatası C2814

'member': yerel bir tür yönetilen veya WinRT içinde yuvalanamaz 'type' yazın

## <a name="example"></a>Örnek

Yerel bir tür bir CLR veya WinRT türü iç içe olamaz. Aşağıdaki örnek, C2814 oluşturur ve bu sorunun nasıl gösterir.

```
// C2814.cpp
// compile with: /clr /c
ref class A {
   class B {};   // C2814
   ref class C {};   // OK
};
```
