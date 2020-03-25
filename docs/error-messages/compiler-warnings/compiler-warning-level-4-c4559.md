---
title: Derleyici Uyarısı (düzey 4) C4559
ms.date: 08/27/2018
f1_keywords:
- C4559
helpviewer_keywords:
- C4559
ms.assetid: ed542f60-454d-45cb-85da-987ede61b1ab
ms.openlocfilehash: 0788824dd4180476d81d9682f99fb95883b8c4f0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198347"
---
# <a name="compiler-warning-level-4-c4559"></a>Derleyici Uyarısı (düzey 4) C4559

> '*Function*': yeniden tanımlama; işlev kazancı __declspec (*değiştirici*)

## <a name="remarks"></a>Açıklamalar

Bir işlev yeniden tanımlandı veya yeniden bildirildi ve ikinci tanım veya bildirim bir **__declspec** değiştirici (*değiştirici*) ekledi. Bu uyarı bilgilendirme amaçlıdır. Bu uyarıyı onarmak için tanımlardan birini silin.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4559 oluşturur:

```cpp
// C4559.cpp
// compile with: /W4 /LD
void f();
__declspec(noalias) void f();   // C4559
```
