---
description: 'Şu konuda daha fazla bilgi edinin: Cloakediıd yapısı'
title: CloakedIid Yapısı
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::CloakedIid
helpviewer_keywords:
- CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
ms.openlocfilehash: 06bddded27882ae1216064aafc311364a8d2fd9f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338785"
---
# <a name="cloakediid-structure"></a>CloakedIid Yapısı

`RuntimeClass`, `Implements` Ve ' nin, `ChainInterfaces` belirtilen arabirime IID listesinde erişilebilir olmadığını gösterir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T>
struct CloakedIid : T;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Gizli (gizlenmiş) arabirim.

## <a name="remarks"></a>Açıklamalar

Aşağıda, **CloakedIid** 'ın nasıl kullanıldığına ilişkin bir örnek verilmiştir: `struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}` .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`T`

`CloakedIid`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** uygular. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL ad alanı](microsoft-wrl-namespace.md)
