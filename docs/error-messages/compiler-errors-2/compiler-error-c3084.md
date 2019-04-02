---
title: Derleyici Hatası C3084
ms.date: 11/04/2016
f1_keywords:
- C3084
helpviewer_keywords:
- C3084
ms.assetid: 0362cb70-e24e-476f-a24d-8f5bb97c3afd
ms.openlocfilehash: 01e229fe0ae5bf9e04c577bb653ff1ed7fdb33bf
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58773913"
---
# <a name="compiler-error-c3084"></a>Derleyici Hatası C3084

'function': Sonlandırıcı/yok edici 'anahtar sözcüğü' olamaz

Bir sonlandırıcı ya da yok edici yanlış bildirildi.

Örneğin, bir yok edici değil işaretlenmelidir korumalı olarak.  Yok edici türetilmiş türlere de erişilemez.  Daha fazla bilgi için [açık geçersiz kılmalar](../../extensions/explicit-overrides-cpp-component-extensions.md) ve [yok ediciler ve sonlandırıcılar, nasıl yapılır: Sınıfları ve yapıları tanımlama ve kullanma (C + +/ CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3084 oluşturur.

```
// C3084.cpp
// compile with: /clr /c
ref struct R {
protected:
   !R() sealed;   // C3084
   !R() abstract;   // C3084
   !R();
};
```