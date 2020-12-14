---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3646'
title: Derleyici hatası C3646
ms.date: 06/14/2018
f1_keywords:
- C3646
helpviewer_keywords:
- C3646
ms.assetid: 4391ead2-9637-4ca3-aeda-5a991b18d66d
ms.openlocfilehash: 0c6f731a09612e6c128756de8d0690c922047e49
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203789"
---
# <a name="compiler-error-c3646"></a>Derleyici hatası C3646

> ' belirtici ': bilinmeyen geçersiz kılma belirticisi

## <a name="remarks"></a>Açıklamalar

Derleyici, bir geçersiz kılma belirticisi bulmak beklenen konumda bir belirteç buldu, ancak belirteç derleyici tarafından tanınmadı.

Örneğin, tanınmayan *belirtici* **_NOEXCEPT**, anahtar sözcüğü ile değiştirin **`noexcept`** .

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
