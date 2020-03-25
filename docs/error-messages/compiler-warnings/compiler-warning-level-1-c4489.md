---
title: Derleyici Uyarısı (düzey 1) C4489
ms.date: 11/04/2016
f1_keywords:
- C4489
helpviewer_keywords:
- C4489
ms.assetid: 43b51c8c-27b5-44c9-b974-fe4b48f4896f
ms.openlocfilehash: e9811e9f9c17463fdcd550ffd82af4f81a40bb34
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186614"
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
