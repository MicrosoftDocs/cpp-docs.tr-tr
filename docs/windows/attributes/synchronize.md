---
description: 'Daha fazla bilgi edinin: Synchronize'
title: Synchronize (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.synchronize
helpviewer_keywords:
- synchronize attribute
ms.assetid: 15fc8544-955d-4765-b3d5-0f619c8b3f40
ms.openlocfilehash: bbee19406396e4041b4d7ca1e2acf2b8d7193494
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329551"
---
# <a name="synchronize"></a>synchronize

Hedef yönteme erişimi eşitler.

## <a name="syntax"></a>Syntax

```cpp
[synchronize]
```

## <a name="remarks"></a>Açıklamalar

**Synchronize** C++ özniteliği bir nesnenin Target metodunu eşitlemek için destek uygular. Eşitleme, hedef yöntemin erişimini denetleyerek birden fazla nesnenin ortak bir kaynak (örneğin bir sınıf yöntemi) kullanmasına izin verir.

Bu öznitelik tarafından yerleştirilen kod, `Lock` hedef yöntemin başındaki uygun yöntemi (iş parçacığı modeli tarafından belirlenir) çağırır. Metodun çıkış yapıldığında `Unlock` otomatik olarak çağrılır. Bu işlevler hakkında daha fazla bilgi için bkz [. CComAutoThreadModule:: Lock](../../atl/reference/ccomautothreadmodule-class.md#lock)

Bu öznitelik, [coclass](coclass.md), [ProgID](progid.md)veya [vi_progid](vi-progid.md) özniteliğinin (ya da bunlardan birini belirten başka bir özniteliğin) aynı öğeye uygulanmasını gerektirir. Tek bir öznitelik kullanılırsa, diğer ikisi otomatik olarak uygulanır. Örneğin, `progid` uygulanmışsa `vi_progid` ve `coclass` de uygulanır.

## <a name="example"></a>Örnek

Aşağıdaki kod, nesnesinin yöntemi için eşitleme sağlar `UpdateBalance` `CMyClass` .

```cpp
// cpp_attr_ref_synchronize.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module(name="SYNC")];

[coclass,
threading(both),
vi_progid("MyProject.MyClass"),
progid("MyProject.MyClass.1"),
uuid("7a7baa0d-59b8-4576-b754-79d07e1d1cc3")
]
class CMyClass {
   float m_nBalance;

   [synchronize]
   void UpdateBalance(float nAdjust) {
      m_nBalance += nAdjust;
   }
};
```

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Class yöntemi, yöntemi|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|Aşağıdakilerden biri veya daha fazlası: `coclass` , `progid` , veya `vi_progid` .|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[COM öznitelikleri](com-attributes.md)
