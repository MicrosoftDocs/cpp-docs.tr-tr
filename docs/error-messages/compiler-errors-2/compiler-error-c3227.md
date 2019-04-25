---
title: Derleyici Hatası C3227
ms.date: 11/04/2016
f1_keywords:
- C3227
helpviewer_keywords:
- C3227
ms.assetid: 7939c23a-96c8-43c2-89e9-f217d132d155
ms.openlocfilehash: b175b14af55a9a462e040f064cc6e38d13fffb94
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173996"
---
# <a name="compiler-error-c3227"></a>Derleyici Hatası C3227

'parameter': 'anahtar sözcüğü' genel tür ayırmak için kullanılamaz

Bir tür örneği için uygun bir oluşturucu gereklidir. Ancak, derleyicinin uygun bir oluşturucu kullanılabilmesini sağlamak mümkün değildir.

Bu hatayı gidermek için genel türler yerine şablonları kullanabilir veya türün bir örneğini oluşturmak için birkaç yöntemden birini kullanabilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3227 oluşturur.

```
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