---
title: Derleyici Uyarısı (düzey 1) C4376
ms.date: 11/04/2016
f1_keywords:
- C4376
helpviewer_keywords:
- C4376
ms.assetid: 5f202c74-9489-48fe-b36f-19cd882b1589
ms.openlocfilehash: 73143e38b66471a41cc61f818f7618b9ddafcaa1
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966466"
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