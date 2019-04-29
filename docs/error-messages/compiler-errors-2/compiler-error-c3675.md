---
title: Derleyici Hatası C3675
ms.date: 11/04/2016
f1_keywords:
- C3675
helpviewer_keywords:
- C3675
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
ms.openlocfilehash: e29e536bf89aef887dc043327e4b4596703d0538
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363901"
---
# <a name="compiler-error-c3675"></a>Derleyici Hatası C3675

'function': 'property' tanımlı olduğundan ayrıldı

Basit bir özelliğin bildirdiğinizde, derleyici alma ve ayarlama erişimci yöntemlerinin ve bu oluşturur adlardır programınızı kapsamı içinde mevcut.  Derleyicinin ürettiği adları get_ ve set_ özellik adının önüne eklenerek oluşturulur.  Bu nedenle, İşlevler derleyici tarafından oluşturulan erişimcileri aynı ada sahip bildiremezsiniz.

Bkz: [özelliği](../../extensions/property-cpp-component-extensions.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3675 oluşturur.

```
// C3675.cpp
// compile with: /clr /c
ref struct C {
public:
   property int Size;
   int get_Size() { return 0; }   // C3675
};
```