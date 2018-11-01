---
title: Derleyici Hatası C3223
ms.date: 11/04/2016
f1_keywords:
- C3223
helpviewer_keywords:
- C3223
ms.assetid: 1f4380b4-0413-40db-a868-62f97babaf78
ms.openlocfilehash: 9c53f7c91cc0e8f4c56d8d780b222b199702310e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50486456"
---
# <a name="compiler-error-c3223"></a>Derleyici Hatası C3223

'property': bir özelliğe 'typeid' uygulayamazsınız

Uygulayamazsınız [TypeID](../../windows/typeid-cpp-component-extensions.md) bir özelliğe.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3223 oluşturur.

```
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