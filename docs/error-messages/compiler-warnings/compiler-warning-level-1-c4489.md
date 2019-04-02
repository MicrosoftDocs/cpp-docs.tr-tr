---
title: Derleyici Uyarısı (düzey 1) C4489
ms.date: 11/04/2016
f1_keywords:
- C4489
helpviewer_keywords:
- C4489
ms.assetid: 43b51c8c-27b5-44c9-b974-fe4b48f4896f
ms.openlocfilehash: dd150621ad3474444861982c095ae8a6addb52fa
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58768243"
---
# <a name="compiler-warning-level-1-c4489"></a>Derleyici Uyarısı (düzey 1) C4489

'belirticisi': arabirim yöntemi 'method';'üzerinde izin verilmiyor geçersiz kılma belirticileri yalnızca başvuru sınıfı ve değer sınıfı yöntemleri üzerinde izin verilir

Belirleyicisi anahtar sözcüğü, bir arabirimi yöntemi üzerinde yanlış kullanıldı.

Daha fazla bilgi için [geçersiz kılma tanımlayıcıları](../../extensions/override-specifiers-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4489 oluşturur.

```
// C4489.cpp
// compile with: /clr /c /W1
public interface class I {
   void f() new;   // C4489
   virtual void b() override;   // C4489

   void g();   // OK
};
```