---
title: Derleyici Uyarısı (düzey 4) C4634
ms.date: 11/04/2016
f1_keywords:
- C4634
helpviewer_keywords:
- C4634
ms.assetid: 3e3496ce-2ac7-43d0-a48a-f514c950e81d
ms.openlocfilehash: 0a84773f80e15b4e6d3851de768751d1d6dc4b4e
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990610"
---
# <a name="compiler-warning-level-4-c4634"></a>Derleyici Uyarısı (düzey 4) C4634

XML belgesi açıklaması: uygulanamıyor: neden

XML belge etiketleri tüm C++ yapılara uygulanamaz.  Örneğin, bir ad alanına veya şablona belge açıklaması ekleyemezsiniz.

Daha fazla bilgi için bkz. [XML belgeleri](../../build/reference/xml-documentation-visual-cpp.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C4634 oluşturur.

```cpp
// C4634.cpp
// compile with: /W4 /doc /c
/// This is a namespace.   // C4634
namespace hello {
   class MyClass  {};
};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek C4634 oluşturur.

```cpp
// C4634_b.cpp
// compile with: /W4 /doc /c
/// This is a template.   // C4634
template <class T>
class MyClass  {};
```
