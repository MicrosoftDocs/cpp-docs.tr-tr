---
title: Derleyici Hatası C3197
ms.date: 11/04/2016
f1_keywords:
- C3197
helpviewer_keywords:
- C3197
ms.assetid: 4e385c3b-222e-425c-9612-46e83ed41650
ms.openlocfilehash: be9b7dadb4f67a6392cd7a2c46caf61d983e79eb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62329042"
---
# <a name="compiler-error-c3197"></a>Derleyici Hatası C3197

'anahtar sözcüğü': yalnızca tanımlarda kullanılabilir

Bir anahtar sözcüğü bir bildirimde kullanıldı ancak yalnızca bir tanım geçerlidir.

Aşağıdaki örnek, C3197 oluşturur:

```
// C3197.cpp
// compile with: /clr /c
ref struct R abstract;   // C3197
ref struct R abstract {};   // OK

public ref class MyObject;   // C3197
ref class MyObject;   // OK
public ref class MyObject {};   // OK
```