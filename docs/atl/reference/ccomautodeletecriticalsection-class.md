---
description: 'Daha fazla bilgi edinin: Ccomautodeletekritiksection sınıfı'
title: Ccomautodeletekritiksection sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComAutoDeleteCriticalSection
- atlcore/ATL::CComAutoDeleteCriticalSection
helpviewer_keywords:
- CComAutoDeleteCriticalSection class
ms.assetid: 2396dbea-1c60-4841-b50e-c4e18af311a3
ms.openlocfilehash: 3c65108917b28b9e4e17210afc54eab6814302b7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152340"
---
# <a name="ccomautodeletecriticalsection-class"></a>Ccomautodeletekritiksection sınıfı

Bu sınıf, kritik bir bölüm nesnesinin sahipliğini almak ve serbest bırakmak için yöntemler sağlar.

## <a name="syntax"></a>Syntax

```
class CComAutoDeleteCriticalSection : public CComSafeDeleteCriticalSection
```

## <a name="remarks"></a>Açıklamalar

`CComAutoDeleteCriticalSection`[Ccomsafedeletekritiksection](../../atl/reference/ccomsafedeletecriticalsection-class.md)sınıfından türetilir. Bununla birlikte, `CComAutoDeleteCriticalSection` [](ccomsafedeletecriticalsection-class.md#term) **`private`** yalnızca bu sınıfın örnekleri kapsam dışına çıktığında veya bellekten açıkça siliniyorsa, iç bellek temizlemeyi zorlayan, erişim için terim yöntemini geçersiz kılar.

Bu sınıf, temel sınıfı üzerinde ek yöntem içermez. Kritik bölüm yardımcı sınıfları hakkında daha fazla bilgi için bkz. [Ccomsafedeletecriticalhandle bölümü](../../atl/reference/ccomsafedeletecriticalsection-class.md) ve [ccomcriticalhandle bölümü](../../atl/reference/ccomcriticalsection-class.md) .

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Ccomcriticalhandle bölümü](../../atl/reference/ccomcriticalsection-class.md)

[Ccomsafedeletecriticalhandle bölümü](../../atl/reference/ccomsafedeletecriticalsection-class.md)

`CComAutoDeleteCriticalSection`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcore. h

## <a name="see-also"></a>Ayrıca bkz.

[Ccomsafedeletekritiksection sınıfı](../../atl/reference/ccomsafedeletecriticalsection-class.md)<br/>
[Ccomcriticalhandle bölüm sınıfı](../../atl/reference/ccomcriticalsection-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
