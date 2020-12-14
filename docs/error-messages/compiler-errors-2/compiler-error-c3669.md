---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3669'
title: Derleyici hatası C3669
ms.date: 11/04/2016
f1_keywords:
- C3669
helpviewer_keywords:
- C3669
ms.assetid: be9c7ae4-e96f-47ab-922a-39a3537d5ca6
ms.openlocfilehash: b746c64af06178caf1006417f61c5f1e853cb67d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228956"
---
# <a name="compiler-error-c3669"></a>Derleyici hatası C3669

' üye ': ' override ' geçersiz kılma belirticisi statik üye işlevlerinde veya oluşturucularda kullanılamaz

Geçersiz kılma yanlış belirtildi. Daha fazla bilgi için bkz. [Açık geçersiz kılmalar](../../extensions/explicit-overrides-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3669 oluşturur.

```cpp
// C3669.cpp
// compile with: /clr
public ref struct R {
   R() override {}   // C3669
};
```
