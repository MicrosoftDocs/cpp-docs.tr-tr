---
title: Derleyici hatası C3223
ms.date: 11/04/2016
f1_keywords:
- C3223
helpviewer_keywords:
- C3223
ms.assetid: 1f4380b4-0413-40db-a868-62f97babaf78
ms.openlocfilehash: a1897492dd5ae0e3290b2d1a2a36b53a62bde839
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74753620"
---
# <a name="compiler-error-c3223"></a>Derleyici hatası C3223

' Property ': bir özelliğe ' typeid ' uygulayamazsınız

Bir özelliğe [TypeId](../../extensions/typeid-cpp-component-extensions.md) uygulayamazsınız.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3223 oluşturur.

```cpp
// C3223.cpp
// compile with: /clr
ref class R {
public:
   property int myprop;
};

int main() {
   System::Type^ type2 = R::myprop::typeid;   // C3223
}
```
