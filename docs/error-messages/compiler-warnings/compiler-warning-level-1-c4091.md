---
title: Derleyici Uyarısı (düzey 1) C4091
ms.date: 11/04/2016
f1_keywords:
- C4091
helpviewer_keywords:
- C4091
ms.assetid: 3a404967-ab42-49b0-b324-fd7ba1859d78
ms.openlocfilehash: 1a9fef0a825f98ab3ce8d935c98eefe1866be6cf
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90684696"
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
