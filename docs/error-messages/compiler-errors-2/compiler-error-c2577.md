---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2577'
title: Derleyici hatası C2577
ms.date: 11/04/2016
f1_keywords:
- C2577
helpviewer_keywords:
- C2577
ms.assetid: fc79ef83-8362-40a2-9257-8037c3195ce4
ms.openlocfilehash: 9e54791070401f334a4dc0650ca2b1bcee5f32a6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208859"
---
# <a name="compiler-error-c2577"></a>Derleyici hatası C2577

' üye ': yıkıcı/Sonlandırıcı bir dönüş türüne sahip olamaz

Yıkıcı veya Sonlandırıcı bir değer **`void`** ya da başka bir tür döndüremez. **`return`** Yok edicisi tanımından ifadesini kaldırın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2577 oluşturur.

```cpp
// C2577.cpp
// compile with: /c
class A {
public:
   A() {}
   ~A(){
      return 0;   // C2577
   }
};
```
