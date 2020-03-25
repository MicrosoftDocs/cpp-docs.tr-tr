---
title: Derleyici Uyarısı (düzey 4) C4565
ms.date: 08/27/2018
f1_keywords:
- C4565
helpviewer_keywords:
- C4565
ms.assetid: a71f1341-a4a1-4060-ad1e-9322531883ed
ms.openlocfilehash: 5eccb3c29da612a39f7fcdf4ef25dedb898c8d43
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198334"
---
# <a name="compiler-warning-level-4-c4565"></a>Derleyici Uyarısı (düzey 4) C4565

> '*Function*': yeniden tanımlama; sembol daha önce __declspec (*değiştirici*) ile bildirildi

## <a name="remarks"></a>Açıklamalar

Bir sembol yeniden tanımlandı veya yeniden bildirildi ve ikinci tanım ya da bildirim, ilk tanım veya bildirimin aksine, `__declspec` değiştirici (*değiştirici*) yoktu. Bu uyarı bilgilendirme amaçlıdır. Bu uyarıyı onarmak için tanımlardan birini silin.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4565 oluşturur:

```cpp
// C4565.cpp
// compile with: /W4 /LD
__declspec(noalias) void f();
void f();   // C4565
```
