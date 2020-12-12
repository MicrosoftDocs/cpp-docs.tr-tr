---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4559'
title: Derleyici Uyarısı (düzey 4) C4559
ms.date: 08/27/2018
f1_keywords:
- C4559
helpviewer_keywords:
- C4559
ms.assetid: ed542f60-454d-45cb-85da-987ede61b1ab
ms.openlocfilehash: 64a8da1a7719d515cc9ddb7b5b6c3e54309ef6cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206636"
---
# <a name="compiler-warning-level-4-c4559"></a>Derleyici Uyarısı (düzey 4) C4559

> '*Function*': yeniden tanımlama; işlev kazancı __declspec (*değiştirici*)

## <a name="remarks"></a>Açıklamalar

Bir işlev yeniden tanımlandı veya yeniden bildirildi ve ikinci tanım veya bildirim bir **`__declspec`** değiştirici (*değiştirici*) ekledi. Bu uyarı bilgilendirme amaçlıdır. Bu uyarıyı onarmak için tanımlardan birini silin.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4559 oluşturur:

```cpp
// C4559.cpp
// compile with: /W4 /LD
void f();
__declspec(noalias) void f();   // C4559
```
