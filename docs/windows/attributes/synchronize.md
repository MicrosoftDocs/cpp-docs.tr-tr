---
title: synchronize (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.synchronize
dev_langs:
- C++
helpviewer_keywords:
- synchronize attribute
ms.assetid: 15fc8544-955d-4765-b3d5-0f619c8b3f40
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 740d99bfbc0da4c290a09a95f5d4f8f227a11fc8
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789877"
---
# <a name="synchronize"></a>eşitle

Hedef yöntemin erişimi eşitler.

## <a name="syntax"></a>Sözdizimi

```cpp
[synchronize]
```

## <a name="remarks"></a>Açıklamalar

**Eşitleme** C++ özniteliği hedef yöntemin bir nesnenin eşitlemek için destek uygular. Hedef yöntemin erişim denetleyerek ortak bir kaynak (örneğin, bir sınıfın yöntemini) kullanmak birden çok nesne eşitlenmesine izin verir.

Bu öznitelik tarafından eklenen kod uygun çağırır `Lock` hedef yöntemin başında yöntemi (iş parçacığı modeli tarafından belirlenir). Yönteminden çıkıldı, `Unlock` otomatik olarak çağrılır. Bu işlevler hakkında daha fazla bilgi için bkz. [CComAutoThreadModule::Lock](../../atl/reference/ccomautothreadmodule-class.md#lock)

Bu öznitelik gerektiren [coclass'ı](coclass.md), [ProgID](progid.md), veya [vi_progid](vi-progid.md) özniteliği (ya da bunlardan birini anlamına gelir. başka bir öznitelik) da uygulanabilir aynı öğeye. Herhangi bir tek öznitelik kullandıysanız, diğer iki otomatik olarak uygulanır. Örneğin, varsa `progid` uygulanan `vi_progid` ve `coclass` de uygulanır.

## <a name="example"></a>Örnek

Eşitleme için aşağıdaki kodu sağlar `UpdateBalance` yöntemi `CMyClass` nesne.

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

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|Sınıf yöntemi yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Bir veya daha fazlasını: `coclass`, `progid`, veya `vi_progid`.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[COM Öznitelikleri](com-attributes.md)  