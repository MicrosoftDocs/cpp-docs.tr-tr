---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3197'
title: Derleyici hatası C3197
ms.date: 11/04/2016
f1_keywords:
- C3197
helpviewer_keywords:
- C3197
ms.assetid: 4e385c3b-222e-425c-9612-46e83ed41650
ms.openlocfilehash: f03792a2dd5120ed2b4a05b2110186d5c985e502
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203763"
---
# <a name="compiler-error-c3197"></a>Derleyici hatası C3197

' anahtar sözcüğü ': yalnızca tanımlarda kullanılabilir

Bir bildirimde anahtar sözcük kullanıldı ancak yalnızca tanımda geçerli.

Aşağıdaki örnek C3197 oluşturur:

```cpp
// C3197.cpp
// compile with: /clr /c
ref struct R abstract;   // C3197
ref struct R abstract {};   // OK

public ref class MyObject;   // C3197
ref class MyObject;   // OK
public ref class MyObject {};   // OK
```
