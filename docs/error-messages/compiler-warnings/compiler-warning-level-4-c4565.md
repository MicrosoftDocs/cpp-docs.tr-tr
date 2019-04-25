---
title: Derleyici Uyarısı (düzey 4) C4565
ms.date: 08/27/2018
f1_keywords:
- C4565
helpviewer_keywords:
- C4565
ms.assetid: a71f1341-a4a1-4060-ad1e-9322531883ed
ms.openlocfilehash: b655dcfb456d32e45833e89e5a48926ad70d1d9e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62220487"
---
# <a name="compiler-warning-level-4-c4565"></a>Derleyici Uyarısı (düzey 4) C4565

> '*işlevi*': yeniden tanımlama; simge daha önce __declspec ile bildirildi (*değiştiricisi*)

## <a name="remarks"></a>Açıklamalar

Bir sembol yeniden tanımlandı veya yeniden tanımlanıyor ve ikinci tanımlama veya ilk tanımında veya bildiriminde, farklı bir bildirimi olmayan sahip bir `__declspec` değiştirici (*değiştiricisi*). Bu uyarı, bilgi amaçlıdır. Bu uyarıyı düzeltmek için tanımlardan birini silin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4565 oluşturur:

```cpp
// C4565.cpp
// compile with: /W4 /LD
__declspec(noalias) void f();
void f();   // C4565
```