---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4489'
title: Derleyici Uyarısı (düzey 1) C4489
ms.date: 11/04/2016
f1_keywords:
- C4489
helpviewer_keywords:
- C4489
ms.assetid: 43b51c8c-27b5-44c9-b974-fe4b48f4896f
ms.openlocfilehash: d2865f7f2eba4db72fa4cbf622609b319197f942
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212421"
---
# <a name="compiler-warning-level-1-c4489"></a>Derleyici Uyarısı (düzey 1) C4489

' belirtici ': ' Method ' arabirim yönteminde izin verilmiyor; geçersiz kılma belirticilerine yalnızca başvuru sınıfı ve değer sınıfı yöntemlerinde izin verilir

Bir tanımlayıcı anahtar sözcüğü, bir arabirim yönteminde yanlış kullanıldı.

Daha fazla bilgi için bkz. [geçersiz kılma belirticileri](../../extensions/override-specifiers-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C4489 oluşturur.

```cpp
// C4489.cpp
// compile with: /clr /c /W1
public interface class I {
   void f() new;   // C4489
   virtual void b() override;   // C4489

   void g();   // OK
};
```
