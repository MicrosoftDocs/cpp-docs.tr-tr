---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3816'
title: Derleyici hatası C3816
ms.date: 11/04/2016
f1_keywords:
- C3816
helpviewer_keywords:
- C3816
ms.assetid: 2e52cc7f-e31c-41a3-8d6f-9f5fab3648c0
ms.openlocfilehash: b2a4ffc435ad4fc2e0c516d99ade1058799fb4b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180961"
---
# <a name="compiler-error-c3816"></a>Derleyici hatası C3816

' declaration ' daha önce farklı bir yönetilen veya Wınrtmodifier ile bildirildi veya tanımlandı

İleri bildirimi ve gerçek bildiriminde, özniteliklerin bildiriminde çakışma veya tutarsızlıklar olmaması gerekir.

Aşağıdaki örnek C3816 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C3816a.cpp
// compile with: /clr /c
class C1;
// try the following line instead
// ref class C1;

ref class C1{  // C3816, forward declaration does not use ref
};
```
