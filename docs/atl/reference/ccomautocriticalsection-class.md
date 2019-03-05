---
title: CComAutoCriticalSection sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection::CComAutoCriticalSection
helpviewer_keywords:
- CComAutoCriticalSection class
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
ms.openlocfilehash: 613440eceb71f0277f4cc5de2af89fe263772797
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301616"
---
# <a name="ccomautocriticalsection-class"></a>CComAutoCriticalSection sınıfı

`CComAutoCriticalSection` kritik bölüm nesnenin sahipliğini serbest bırakma ve alma için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CComAutoCriticalSection : public CComCriticalSection
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComAutoCriticalSection::CComAutoCriticalSection](#ccomautocriticalsection)|Oluşturucu.|
|[CComAutoCriticalSection:: ~ CComAutoCriticalSection](#dtor)|Yıkıcı.|

## <a name="remarks"></a>Açıklamalar

`CComAutoCriticalSection` sınıfına benzer [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md), dışında `CComAutoCriticalSection` kritik bölüm nesneye otomatik olarak başlatır.

Genellikle, kullandığınız `CComAutoCriticalSection` aracılığıyla `typedef` adı [AutoCriticalSection](ccommultithreadmodel-class.md#autocriticalsection). Bu ada başvuran `CComAutoCriticalSection` olduğunda [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) kullanılıyor.

`Init` Ve `Term` yöntemlerinden [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) Bu sınıf kullanırken kullanılamaz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

`CComAutoCriticalSection`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcore.h

##  <a name="ccomautocriticalsection"></a>  CComAutoCriticalSection::CComAutoCriticalSection

Oluşturucu.

```
CComAutoCriticalSection();
```

### <a name="remarks"></a>Açıklamalar

Win32 işlevini çağırır [InitializeCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsection), kritik bölüm nesnesi başlatır.

##  <a name="dtor"></a>  CComAutoCriticalSection:: ~ CComAutoCriticalSection

Yıkıcı.

```
~CComAutoCriticalSection() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı çağrıları [DeleteCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-deletecriticalsection), kritik bölüm nesne tarafından kullanılan tüm sistem kaynakları serbest bırakır.

## <a name="see-also"></a>Ayrıca bkz.

[CComFakeCriticalSection Sınıfı](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[CComCriticalSection Sınıfı](../../atl/reference/ccomcriticalsection-class.md)
