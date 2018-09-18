---
title: Derleyici Uyarısı (düzey 1) C4376 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4376
dev_langs:
- C++
helpviewer_keywords:
- C4376
ms.assetid: 5f202c74-9489-48fe-b36f-19cd882b1589
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1923f2aed19de5e7f438407c25640821a2fa49c2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46039627"
---
# <a name="compiler-warning-level-1-c4376"></a>Derleyici Uyarısı (düzey 1) C4376

erişim belirticisi ' old_specifier:' artık desteklenmiyor: Lütfen ' new_specifier:' yerine

Tür ve üye erişilebilirlik meta verilerinde belirtme hakkında daha fazla bilgi için bkz [türü görünürlük](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) ve [üye görünürlüğü](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility) içinde [nasıl yapılır: tanımlayın ve Consume Classes and Structs (C + +/ CLI) ](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4376 oluşturur.

```
// C4376.cpp
// compile with: /clr /W1 /c
public ref class G {
public public:   // C4376
   void m2();
};

public ref class H {
public:   // OK
   void m2();
};
```