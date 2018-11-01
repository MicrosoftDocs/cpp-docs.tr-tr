---
title: Derleyici Hatası C3646
ms.date: 06/14/2018
f1_keywords:
- C3646
helpviewer_keywords:
- C3646
ms.assetid: 4391ead2-9637-4ca3-aeda-5a991b18d66d
ms.openlocfilehash: df2e52631ed75cc4a473429ea35e136ed0a88f98
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50606732"
---
# <a name="compiler-error-c3646"></a>Derleyici Hatası C3646

> 'belirticisi': Bilinmeyen geçersiz kılma belirticisi

## <a name="remarks"></a>Açıklamalar

Derleyici, burada, bir geçersiz kılma tanımlayıcısı bekleniyordu, ancak belirteç derleyici tarafından tanınmadı konumda bir belirteci bulundu.

Örneğin, tanınmayan *belirticisi* olduğu **_NOEXCEPT**, anahtar sözcüğüyle değiştirin **noexcept**.

Daha fazla bilgi için [geçersiz kılma tanımlayıcıları](../../windows/override-specifiers-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3646 oluşturur ve bunu düzeltmek için bir yol gösterir:

```cpp
// C3646.cpp
// compile with: /clr /c
ref class C {
   void f() unknown;   // C3646
   // try the following line instead
   // virtual void f() abstract;
};
```