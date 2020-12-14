---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2286'
title: Derleyici hatası C2286
ms.date: 11/04/2016
f1_keywords:
- C2286
helpviewer_keywords:
- C2286
ms.assetid: 078e0201-35cc-42e2-8dbc-6f8cf557b098
ms.openlocfilehash: 89c8b69c42188d448fad0cd08287773d7a713d08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298467"
---
# <a name="compiler-error-c2286"></a>Derleyici hatası C2286

' Identifier ' gösteriminin üyelerine yönelik işaretçiler zaten ' devralma ' olarak ayarlanmış-bildirim yoksayıldı

Sınıfı için iki farklı işaretçiden üyeye gösterimi mevcuttur.

Daha fazla bilgi için bkz. [Devralma anahtar sözcükleri](../../cpp/inheritance-keywords.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C2286 oluşturur:

```cpp
// C2286.cpp
// compile with: /c
class __single_inheritance X;
class __multiple_inheritance X;   // C2286
class  __multiple_inheritance Y;   // OK
```
