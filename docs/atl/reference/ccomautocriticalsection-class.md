---
title: CComAutoCriticalSection Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection::CComAutoCriticalSection
helpviewer_keywords:
- CComAutoCriticalSection class
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
ms.openlocfilehash: 8cbf08082fd24ef2cf0e8794e2944a799baec084
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321086"
---
# <a name="ccomautocriticalsection-class"></a>CComAutoCriticalSection Sınıfı

`CComAutoCriticalSection`kritik bir bölüm nesnesinin sahipliğini elde etmek ve serbest bırakmak için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CComAutoCriticalSection : public CComCriticalSection
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Kcomautocriticalsection::kcomautocriticalsection](#ccomautocriticalsection)|Oluşturucu.|
|[Kcomautocriticalsection::~ccomautocriticalsection](#dtor)|Yıkıcı.|

## <a name="remarks"></a>Açıklamalar

`CComAutoCriticalSection`[cComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)sınıfına benzer, `CComAutoCriticalSection` ancak otomatik olarak oluşturucudaki kritik bölüm nesnesini başharfe ait hale getirmek.

Genellikle, `CComAutoCriticalSection` `typedef` [AutoCriticalSection](ccommultithreadmodel-class.md#autocriticalsection)adı ile kullanın. `CComAutoCriticalSection` [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) kullanılırken bu ad başvurur.

`Init` `Term` [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) ve yöntemleri bu sınıfı kullanırken kullanılamaz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Ccomcriticalsection](../../atl/reference/ccomcriticalsection-class.md)

`CComAutoCriticalSection`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcore.h

## <a name="ccomautocriticalsectionccomautocriticalsection"></a><a name="ccomautocriticalsection"></a>Kcomautocriticalsection::kcomautocriticalsection

Oluşturucu.

```
CComAutoCriticalSection();
```

### <a name="remarks"></a>Açıklamalar

Win32 işlevini çağırır [InitializeCriticalSection](/windows/win32/api/synchapi/nf-synchapi-initializecriticalsection), kritik bölüm nesnesini başharfe getirir.

## <a name="ccomautocriticalsectionccomautocriticalsection"></a><a name="dtor"></a>Kcomautocriticalsection::~ccomautocriticalsection

Yıkıcı.

```
~CComAutoCriticalSection() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı [DeleteCriticalSection](/windows/win32/api/synchapi/nf-synchapi-deletecriticalsection)çağırır , kritik bölüm nesnesi tarafından kullanılan tüm sistem kaynaklarını bültenleri.

## <a name="see-also"></a>Ayrıca bkz.

[CComFakeCriticalSection Sınıfı](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[CComCriticalSection Sınıfı](../../atl/reference/ccomcriticalsection-class.md)
