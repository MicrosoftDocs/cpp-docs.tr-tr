---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3084'
title: Derleyici hatası C3084
ms.date: 11/04/2016
f1_keywords:
- C3084
helpviewer_keywords:
- C3084
ms.assetid: 0362cb70-e24e-476f-a24d-8f5bb97c3afd
ms.openlocfilehash: 8603930e9087f1e407d5e8df65078604836b9a16
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320125"
---
# <a name="compiler-error-c3084"></a>Derleyici hatası C3084

' function ': Sonlandırıcı/yıkıcı ' anahtar sözcük ' olamaz

Sonlandırıcı veya yıkıcı yanlış bildirildi.

Örneğin, yıkıcı korumalı olarak işaretlenmemelidir.  Yok edicinin türetilmiş türler için erişilemez olur.  Daha fazla bilgi için bkz. [nasıl yapılır: sınıfları ve yapıları tanımlama ve kullanma (C++/CLI) Içindeki](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) [Açık geçersiz kılmalar](../../extensions/explicit-overrides-cpp-component-extensions.md) ve yok ediciler ve sonlandırıcılar.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3084 oluşturur.

```cpp
// C3084.cpp
// compile with: /clr /c
ref struct R {
protected:
   !R() sealed;   // C3084
   !R() abstract;   // C3084
   !R();
};
```
