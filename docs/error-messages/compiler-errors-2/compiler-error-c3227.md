---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3227'
title: Derleyici hatası C3227
ms.date: 11/04/2016
f1_keywords:
- C3227
helpviewer_keywords:
- C3227
ms.assetid: 7939c23a-96c8-43c2-89e9-f217d132d155
ms.openlocfilehash: 26d66bf3e0c3bc3a6f391d66608f3e6790b2d11d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97304148"
---
# <a name="compiler-error-c3227"></a>Derleyici hatası C3227

' Parameter ': ' anahtar sözcük ' bir genel tür ayırmak için kullanılamaz

Bir tür oluşturmak için uygun bir Oluşturucu gereklidir. Ancak, derleyici uygun bir oluşturucunun kullanılabilir olduğundan emin olamaz.

Bu hatayı çözmek için genel türler yerine şablonları kullanabilir veya bir tür örneği oluşturmak için çeşitli yöntemlerden birini kullanabilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3227 oluşturur.

```cpp
// C3227.cpp
// compile with: /clr /c
generic<class T> interface class ICreate {
   static T Create();
};

generic <class T>
where T : ICreate<T>
ref class C {
   void f() {
      T t = new T;   // C3227

      // OK
      T t2 = ICreate<T>::Create();
      T t3 = safe_cast<T>( System::Activator::CreateInstance(T::typeid) );
   }
};
```
