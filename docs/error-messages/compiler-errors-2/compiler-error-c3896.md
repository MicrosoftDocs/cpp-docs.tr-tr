---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3896'
title: Derleyici hatası C3896
ms.date: 11/04/2016
f1_keywords:
- C3896
helpviewer_keywords:
- C3896
ms.assetid: eb8be0f6-5b4e-4d71-8285-8a2a94f8ba29
ms.openlocfilehash: c08a9af6d10e741b39fa2547cfbc6c04a6dd3a1a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222703"
---
# <a name="compiler-error-c3896"></a>Derleyici hatası C3896

' üye ': Hatalı Başlatıcı: Bu sabit değerli veri üyesi yalnızca ' nullptr ' ile başlatılabilir

[Sabit değerli](../../extensions/literal-cpp-component-extensions.md) bir veri üyesi yanlış başlatılmış.  Daha fazla bilgi için bkz. [nullptr](../../extensions/nullptr-cpp-component-extensions.md) .

Aşağıdaki örnek C3896 oluşturur:

```cpp
// C3896.cpp
// compile with: /clr /c
ref class R{};

value class V {
   literal R ^ r = "test";   // C3896
   literal R ^ r2 = nullptr;   // OK
};
```
