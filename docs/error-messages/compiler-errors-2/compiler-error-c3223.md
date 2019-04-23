---
title: Derleyici Hatası C3223
ms.date: 11/04/2016
f1_keywords:
- C3223
helpviewer_keywords:
- C3223
ms.assetid: 1f4380b4-0413-40db-a868-62f97babaf78
ms.openlocfilehash: 5771de24cd07978903a3e598f1ff5658cb61eafa
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59778557"
---
# <a name="compiler-error-c3223"></a>Derleyici Hatası C3223

'property': bir özelliğe 'typeid' uygulayamazsınız

Uygulayamazsınız [TypeID](../../extensions/typeid-cpp-component-extensions.md) bir özelliğe.

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