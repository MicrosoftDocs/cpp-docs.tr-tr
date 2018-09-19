---
title: Derleyici Uyarısı (düzey 4) C4634 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4634
dev_langs:
- C++
helpviewer_keywords:
- C4634
ms.assetid: 3e3496ce-2ac7-43d0-a48a-f514c950e81d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4fe89eaffda80ab40efedc4facf75929d07a7537
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034921"
---
# <a name="compiler-warning-level-4-c4634"></a>Derleyici Uyarısı (düzey 4) C4634

XML belgesi açıklaması: uygulanamaz: nedeni

XML belge etiketleri için tüm C++ değil uygulanabilir oluşturur.  Örneğin, bir ad alanı veya şablon belge açıklaması eklenemiyor.

Daha fazla bilgi için [XML belgeleri](../../ide/xml-documentation-visual-cpp.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4634 oluşturur.

```
// C4634.cpp
// compile with: /W4 /doc /c
/// This is a namespace.   // C4634
namespace hello {
   class MyClass  {};
};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4634 oluşturur.

```
// C4634_b.cpp
// compile with: /W4 /doc /c
/// This is a template.   // C4634
template <class T>
class MyClass  {};
```