---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4634'
title: Derleyici Uyarısı (düzey 4) C4634
ms.date: 11/04/2016
f1_keywords:
- C4634
helpviewer_keywords:
- C4634
ms.assetid: 3e3496ce-2ac7-43d0-a48a-f514c950e81d
ms.openlocfilehash: 87144f1a3c95f46159b07dc776707da06a56ff21
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134140"
---
# <a name="compiler-warning-level-4-c4634"></a>Derleyici Uyarısı (düzey 4) C4634

XML belgesi açıklaması: uygulanamıyor: neden

XML belge etiketleri tüm C++ yapılarına uygulanamaz.  Örneğin, bir ad alanına veya şablona belge açıklaması ekleyemezsiniz.

Daha fazla bilgi için bkz. [XML belgeleri](../../build/reference/xml-documentation-visual-cpp.md).

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C4634 oluşturur.

```cpp
// C4634.cpp
// compile with: /W4 /doc /c
/// This is a namespace.   // C4634
namespace hello {
   class MyClass  {};
};
```

Aşağıdaki örnek C4634 oluşturur.

```cpp
// C4634_b.cpp
// compile with: /W4 /doc /c
/// This is a template.   // C4634
template <class T>
class MyClass  {};
```
