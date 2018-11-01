---
title: Derleyici Uyarısı (düzey 4) C4559
ms.date: 08/27/2018
f1_keywords:
- C4559
helpviewer_keywords:
- C4559
ms.assetid: ed542f60-454d-45cb-85da-987ede61b1ab
ms.openlocfilehash: afb4fb493c7c3e34ca691720a30d74517b0ab5b7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50661415"
---
# <a name="compiler-warning-level-4-c4559"></a>Derleyici Uyarısı (düzey 4) C4559

> '*işlevi*': yeniden tanımlama; işlev kazançlar __declspec (*değiştiricisi*)

## <a name="remarks"></a>Açıklamalar

Bir işlevi yeniden tanımlandı veya yeniden tanımlanıyor ve ikinci tanımında veya bildiriminde eklenen bir **__declspec** değiştirici (*değiştiricisi*). Bu uyarı, bilgi amaçlıdır. Bu uyarıyı düzeltmek için tanımlardan birini silin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4559 oluşturur:

```cpp
// C4559.cpp
// compile with: /W4 /LD
void f();
__declspec(noalias) void f();   // C4559
```