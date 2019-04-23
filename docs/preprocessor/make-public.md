---
title: make_public
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.make_public
- make_public_CPP
helpviewer_keywords:
- pragmas, make_public
- make_public pragma
ms.assetid: c3665f4d-268a-4932-9661-c37c8ae6a341
ms.openlocfilehash: d569758f90b9e55f65ad13517f86dea41d151ca8
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59039130"
---
# <a name="makepublic"></a>make_public
Yerel bir tür genel derleme erişilebilirliği olmayacağını gösterir.

## <a name="syntax"></a>Sözdizimi

```
#pragma make_public(type)
```

### <a name="parameters"></a>Parametreler

*tür* genel derleme erişilebilirliği olmasını istediğiniz tür adıdır.

## <a name="remarks"></a>Açıklamalar

**make_public** başvurmak istediğiniz yerel türünü değiştiremezsiniz. h: dosyasından olduğunda için kullanışlıdır. Yerel tür görünürlük sayesinde genel derleme imzası bir tür genel bir işlevde kullanmak istiyorsanız, yerel bir tür ayrıca genel bütünleştirilmiş kod erişilebilirliği olmalıdır veya derleyici bir uyarı verir.

**make_public** genel kapsamda belirtilmiş olmalı ve yalnızca noktasından etkisi, BT kaynak kodu dosyasının sonuna aracılığıyla bildirilir bulunmaktadır.

Yerel bir tür açık veya örtük olarak özel olabilir. bkz: [tür görünürlüğü](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) daha fazla bilgi için.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek, iki yerel yapılar için tanımları içeren bir .h dosyası içeriğidir.

```cpp
// make_public_pragma.h
struct Native_Struct_1 { int i; };
struct Native_Struct_2 { int i; };
```

Aşağıdaki kod örneği üst bilgi dosyası tüketir ve açıkça kullanarak yerel yapılar genel olarak işaretlemek sürece gösteren **make_public**, yerel yapılar için kullanmaya çalıştığınızda, derleyici bir uyarı oluşturur Genel olarak yönetilen bir tür genel işlev imzası.

```cpp
// make_public_pragma.cpp
// compile with: /c /clr /W1
#pragma warning (default : 4692)
#include "make_public_pragma.h"
#pragma make_public(Native_Struct_1)

public ref struct A {
   void Test(Native_Struct_1 u) {u.i = 0;}   // OK
   void Test(Native_Struct_2 u) {u.i = 0;}   // C4692
};
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)