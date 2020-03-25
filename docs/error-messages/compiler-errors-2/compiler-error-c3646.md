---
title: Derleyici hatası C3646
ms.date: 06/14/2018
f1_keywords:
- C3646
helpviewer_keywords:
- C3646
ms.assetid: 4391ead2-9637-4ca3-aeda-5a991b18d66d
ms.openlocfilehash: 13a3ebeb6e7783687abc73cd0dcc018abe827809
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80200479"
---
# <a name="compiler-error-c3646"></a>Derleyici hatası C3646

> ' belirtici ': bilinmeyen geçersiz kılma belirticisi

## <a name="remarks"></a>Açıklamalar

Derleyici, bir geçersiz kılma belirticisi bulmak beklenen konumda bir belirteç buldu, ancak belirteç derleyici tarafından tanınmadı.

Örneğin, tanınmayan *belirleyici* **_NOEXCEPT**, bunu **NOEXCEPT**anahtar sözcüğüyle değiştirin.

Daha fazla bilgi için bkz. [geçersiz kılma belirticileri](../../extensions/override-specifiers-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3646 oluşturur ve bunu çözmek için bir yol gösterir:

```cpp
// C3646.cpp
// compile with: /clr /c
ref class C {
   void f() unknown;   // C3646
   // try the following line instead
   // virtual void f() abstract;
};
```
