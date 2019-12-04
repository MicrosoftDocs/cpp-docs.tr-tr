---
title: Derleyici hatası C2605
ms.date: 11/04/2016
f1_keywords:
- C2605
helpviewer_keywords:
- C2605
ms.assetid: a0e6f132-5acf-4e19-b277-ddf196d182bf
ms.openlocfilehash: dfa221500d27e71cdbe1ab581eec346c0f268b66
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737887"
---
# <a name="compiler-error-c2605"></a>Derleyici hatası C2605

' name ': Bu yöntem yönetilen veya WinRT sınıfı içinde ayrılmıştır

Bazı adlar derleyici tarafından iç işlevler için ayrılmıştır.  Daha fazla bilgi için bkz. yok [ediciler ve sonlandırıcılar](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Örnek

Aşağıdaki örnek C2605 oluşturur.

```cpp
// C2605.cpp
// compile with: /clr /c
ref class R {
protected:
   void Finalize() {}   // C2605
};
```
