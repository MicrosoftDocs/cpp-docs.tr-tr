---
title: Derleyici hatası C3227
ms.date: 11/04/2016
f1_keywords:
- C3227
helpviewer_keywords:
- C3227
ms.assetid: 7939c23a-96c8-43c2-89e9-f217d132d155
ms.openlocfilehash: 460000531dba77e42379199f276c9e2e02f43a9b
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743425"
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
