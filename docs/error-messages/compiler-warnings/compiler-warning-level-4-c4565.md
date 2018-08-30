---
title: Derleyici Uyarısı (düzey 4) C4565 | Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4565
dev_langs:
- C++
helpviewer_keywords:
- C4565
ms.assetid: a71f1341-a4a1-4060-ad1e-9322531883ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c25f2f1fc16c6d45a7d1eddec8d3efe62db142f2
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211268"
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