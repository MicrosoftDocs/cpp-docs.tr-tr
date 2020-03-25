---
title: CloakedIid Yapısı
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::CloakedIid
helpviewer_keywords:
- CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
ms.openlocfilehash: 1cc9e79384bbf4aae44199c2f35331e3afd8fd8f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214116"
---
# <a name="cloakediid-structure"></a>CloakedIid Yapısı

`RuntimeClass`, `Implements` ve `ChainInterfaces` şablonlarına, belirtilen arabirimin IID listesinde erişilebilir olmadığını gösterir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T>
struct CloakedIid : T;
```

#### <a name="parameters"></a>Parametreler

*Şı*<br/>
Gizli (gizlenmiş) arabirim.

## <a name="remarks"></a>Açıklamalar

Aşağıda, **CloakedIid** 'ın nasıl kullanıldığına ilişkin bir örnek verilmiştir: `struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}`.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`T`

`CloakedIid`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** uygular. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)
