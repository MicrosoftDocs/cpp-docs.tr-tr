---
title: CloakedIid Yapısı
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::CloakedIid
helpviewer_keywords:
- CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
ms.openlocfilehash: a47b9e5fdb4a6e7f49b9704244b4e62e3647a04e
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787825"
---
# <a name="cloakediid-structure"></a>CloakedIid Yapısı

Gösterir `RuntimeClass`, `Implements` ve `ChainInterfaces` şablonları belirtilen arabirim IID'si listesinde erişilebilir değil.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T>
struct CloakedIid : T;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
(Gizlenmiş) gizlenen arabirim.

## <a name="remarks"></a>Açıklamalar

İlişkin bir örnek verilmiştir **Cloakedıid** kullanılır: `struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}`.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`T`

`CloakedIid`

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)