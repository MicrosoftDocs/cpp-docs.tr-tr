---
title: Derleyici Uyarısı (düzey 4) C4565
ms.date: 08/27/2018
f1_keywords:
- C4565
helpviewer_keywords:
- C4565
ms.assetid: a71f1341-a4a1-4060-ad1e-9322531883ed
ms.openlocfilehash: ba2e1e7eb490a28626937a3911608ff9686d6f38
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87195986"
---
# <a name="compiler-warning-level-4-c4565"></a>Derleyici Uyarısı (düzey 4) C4565

> '*Function*': yeniden tanımlama; sembol daha önce __declspec (*değiştirici*) ile bildirildi

## <a name="remarks"></a>Açıklamalar

Bir sembol yeniden tanımlandı veya yeniden bildirildi ve ikinci tanım ya da bildirim, ilk tanım veya bildirimin aksine **`__declspec`** değiştirici (*değiştirici*) yoktu. Bu uyarı bilgilendirme amaçlıdır. Bu uyarıyı onarmak için tanımlardan birini silin.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4565 oluşturur:

```cpp
// C4565.cpp
// compile with: /W4 /LD
__declspec(noalias) void f();
void f();   // C4565
```
