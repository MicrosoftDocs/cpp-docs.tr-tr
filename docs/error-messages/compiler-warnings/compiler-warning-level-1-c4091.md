---
title: Derleyici Uyarısı (düzey 1) C4091
ms.date: 11/04/2016
f1_keywords:
- C4091
helpviewer_keywords:
- C4091
ms.assetid: 3a404967-ab42-49b0-b324-fd7ba1859d78
ms.openlocfilehash: 87432a74dfe7c09a52f436d4e91b3f70eb66856b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491747"
---
# <a name="compiler-warning-level-1-c4091"></a>Derleyici Uyarısı (düzey 1) C4091

'anahtar sözcüğü': hiçbir değişken bildirirken 'type' solunda yoksayılır

Derleyici burada kullanıcının büyük olasılıkla bildirilmesi için bir değişken amaçlandı, ancak derleyicinin değişkenini bildirmek tamamlayamadı bir durum algılandı.

## <a name="example"></a>Örnek

A `__declspec` kullanıcı tanımlı tür bildiriminin başında özniteliği bu türün değişkenlerine uygulanır. Hiçbir değişken bildirimi yapılmadı C4091 gösterir. Aşağıdaki örnek, C4091 oluşturur.

```
// C4091.cpp
// compile with: /W1 /c
__declspec(dllimport) class X {}; // C4091

// __declspec attribute applies to varX
__declspec(dllimport) class X2 {} varX;

// __declspec attribute after the class or struct keyword
// applies to user defined type
class __declspec(dllimport) X3 {};
```

## <a name="example"></a>Örnek

Tanımlayıcının bir typedef ise, ayrıca bir değişken adı olamaz. Aşağıdaki örnek, C4091 oluşturur.

```
// C4091_b.cpp
// compile with: /c /W1 /WX
#define LIST 4
typedef struct _LIST {} LIST;   // C4091
```