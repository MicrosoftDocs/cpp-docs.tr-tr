---
title: Derleyici Uyarısı (düzey 1) C4376
ms.date: 11/04/2016
f1_keywords:
- C4376
helpviewer_keywords:
- C4376
ms.assetid: 5f202c74-9489-48fe-b36f-19cd882b1589
ms.openlocfilehash: 8009d2e5d09ad173f6150ebe9a907be9f4947cd7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80162862"
---
# <a name="compiler-warning-level-1-c4376"></a>Derleyici Uyarısı (düzey 1) C4376

erişim belirticisi ' old_specifier: ' artık desteklenmiyor: Lütfen bunun yerine ' new_specifier: ' kullanın

Meta verilerde tür ve üye erişilebilirliğini belirtme hakkında daha fazla bilgi için bkz. [nasıl yapılır: sınıfları ve yapıları tanımlama ve kullanma (C++/CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md)Içinde [tür görünürlüğü](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) ve [üye görünürlüğü](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C4376 oluşturur.

```cpp
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
