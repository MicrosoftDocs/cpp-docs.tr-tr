---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4565'
title: Derleyici Uyarısı (düzey 4) C4565
ms.date: 08/27/2018
f1_keywords:
- C4565
helpviewer_keywords:
- C4565
ms.assetid: a71f1341-a4a1-4060-ad1e-9322531883ed
ms.openlocfilehash: bdcf36234ef5a7d8f371d8d25d31b9cb3a36590d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255151"
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
