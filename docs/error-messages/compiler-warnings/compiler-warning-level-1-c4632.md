---
title: Derleyici Uyarısı (düzey 1) C4632
ms.date: 11/04/2016
f1_keywords:
- C4632
helpviewer_keywords:
- C4632
ms.assetid: 9e35d205-cf21-4e34-8bd5-e1e7b0e2cdd3
ms.openlocfilehash: 3a5e6ef8cb461f609ff06fad227b8c7bce81e58c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199561"
---
# <a name="compiler-warning-level-1-c4632"></a>Derleyici Uyarısı (düzey 1) C4632

XML belgesi açıklaması: dosya erişimi reddedildi: neden

. Xdc dosyasının (`file`) yolu geçerli değildi ve. xdc dosyası oluşturulmadı.

Aşağıdaki örnek C4632 oluşturur:

```cpp
// C4632.cpp
// compile with: /clr /docv:\\falsedir /LD /W1
// C4632 expected

/// Text for class MyClass.
public ref class MyClass {};
```
