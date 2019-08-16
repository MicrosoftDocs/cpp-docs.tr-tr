---
title: Ccomautocriticalhandle bölüm sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection::CComAutoCriticalSection
helpviewer_keywords:
- CComAutoCriticalSection class
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
ms.openlocfilehash: 116c550f45bf622e7620b3a6f552339b4bcc24a7
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497926"
---
# <a name="ccomautocriticalsection-class"></a>Ccomautocriticalhandle bölüm sınıfı

`CComAutoCriticalSection`kritik bölüm nesnesinin sahipliğini almak ve serbest bırakmak için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CComAutoCriticalSection : public CComCriticalSection
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Ccomautocriticalhandle bölümü:: Ccomautocriticalhandle bölümü](#ccomautocriticalsection)|Oluşturucu.|
|[Ccomautocriticalhandle bölümü:: ~ Ccomautocriticalhandle bölümü](#dtor)|Yok edicisi.|

## <a name="remarks"></a>Açıklamalar

`CComAutoCriticalSection`,`CComAutoCriticalSection` kurucudaki kritik bölüm nesnesini otomatik olarak başlatan sınıf [ccomcriticalhandle bölümüne](../../atl/reference/ccomcriticalsection-class.md)benzerdir.

Genellikle, `CComAutoCriticalSection` `typedef` ad [oto](ccommultithreadmodel-class.md#autocriticalsection)adı ' nı kullanırsınız. Bu ad, `CComAutoCriticalSection` [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) kullanılırken başvuruda bulunur.

[Ccomcriticalhandle bölümündeki](../../atl/reference/ccomcriticalsection-class.md) `Term` veyöntemleribusınıfkullanılırkenkullanılamaz.`Init`

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

`CComAutoCriticalSection`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcore. h

##  <a name="ccomautocriticalsection"></a>Ccomautocriticalhandle bölümü:: Ccomautocriticalhandle bölümü

Oluşturucu.

```
CComAutoCriticalSection();
```

### <a name="remarks"></a>Açıklamalar

Kritik bölüm nesnesini başlatan [InitializeCriticalSection](/windows/win32/api/synchapi/nf-synchapi-initializecriticalsection)Win32 işlevini çağırır.

##  <a name="dtor"></a>Ccomautocriticalhandle bölümü:: ~ Ccomautocriticalhandle bölümü

Yok edicisi.

```
~CComAutoCriticalSection() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı, kritik bölüm nesnesi tarafından kullanılan tüm sistem kaynaklarını serbest bırakarak [Deletecriticalhandle bölümünü](/windows/win32/api/synchapi/nf-synchapi-deletecriticalsection)çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[CComFakeCriticalSection Sınıfı](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[CComCriticalSection Sınıfı](../../atl/reference/ccomcriticalsection-class.md)
