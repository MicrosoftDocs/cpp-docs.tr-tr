---
title: Derleyici Hatası C3669
ms.date: 11/04/2016
f1_keywords:
- C3669
helpviewer_keywords:
- C3669
ms.assetid: be9c7ae4-e96f-47ab-922a-39a3537d5ca6
ms.openlocfilehash: 3b0ad3aa7395f5f423c8c36f547d4a0e2ad792c1
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58777109"
---
# <a name="compiler-error-c3669"></a>Derleyici Hatası C3669

'member': geçersiz kılma belirticisi 'override' izin statik üye işlevler veya oluşturucular üzerinde

Bir geçersiz kılma yanlış olarak belirtildi. Daha fazla bilgi için [açık geçersiz kılmalar](../../extensions/explicit-overrides-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3669 oluşturur.

```
// C3669.cpp
// compile with: /clr
public ref struct R {
   R() override {}   // C3669
};
```