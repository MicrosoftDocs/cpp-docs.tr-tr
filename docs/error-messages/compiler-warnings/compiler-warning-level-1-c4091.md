---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4091'
title: Derleyici Uyarısı (düzey 1) C4091
ms.date: 11/04/2016
f1_keywords:
- C4091
helpviewer_keywords:
- C4091
ms.assetid: 3a404967-ab42-49b0-b324-fd7ba1859d78
ms.openlocfilehash: 970283964174ced3f3665ff31199e12d8c14be8b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272259"
---
# <a name="compiler-warning-level-1-c4091"></a>Derleyici Uyarısı (düzey 1) C4091

' anahtar sözcüğü ': hiçbir değişken bildirilmemiş olduğunda ' Type ' sol tarafında yoksayıldı

Derleyici, kullanıcının bildirildiği bir değişkene sahip olduğu, ancak derleyicinin değişkeni bildiremediği bir durum algıladı.

## <a name="examples"></a>Örnekler

**`__declspec`** Kullanıcı tanımlı tür bildiriminin başındaki bir öznitelik, bu tür değişkeni için geçerlidir. C4091, hiçbir değişkenin bildirilmemiş olduğunu gösterir. Aşağıdaki örnek C4091 oluşturur.

```cpp
// C4091.cpp
// compile with: /W1 /c
__declspec(dllimport) class X {}; // C4091

// __declspec attribute applies to varX
__declspec(dllimport) class X2 {} varX;

// __declspec attribute after the class or struct keyword
// applies to user defined type
class __declspec(dllimport) X3 {};
```

Bir tanımlayıcı bir typedef ise, aynı zamanda bir değişken adı olamaz. Aşağıdaki örnek C4091 oluşturur.

```cpp
// C4091_b.cpp
// compile with: /c /W1 /WX
#define LIST 4
typedef struct _LIST {} LIST;   // C4091
```
