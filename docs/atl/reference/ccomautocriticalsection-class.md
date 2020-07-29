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
ms.openlocfilehash: 26b43fa4adc40993a44318c67be990c781b5cdf6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226639"
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

`CComAutoCriticalSection`, kurucudaki kritik bölüm nesnesini otomatik olarak başlatan sınıf [Ccomcriticalhandle bölümüne](../../atl/reference/ccomcriticalsection-class.md)benzerdir `CComAutoCriticalSection` .

Genellikle, `CComAutoCriticalSection` **`typedef`** ad [oto](ccommultithreadmodel-class.md#autocriticalsection)adı ' nı kullanırsınız. Bu ad `CComAutoCriticalSection` , [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) kullanılırken başvuruda bulunur.

`Init` `Term` [Ccomcriticalhandle bölümündeki](../../atl/reference/ccomcriticalsection-class.md) ve yöntemleri bu sınıf kullanılırken kullanılamaz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Ccomcriticalhandle bölümü](../../atl/reference/ccomcriticalsection-class.md)

`CComAutoCriticalSection`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcore. h

## <a name="ccomautocriticalsectionccomautocriticalsection"></a><a name="ccomautocriticalsection"></a>Ccomautocriticalhandle bölümü:: Ccomautocriticalhandle bölümü

Oluşturucu.

```
CComAutoCriticalSection();
```

### <a name="remarks"></a>Açıklamalar

Kritik bölüm nesnesini başlatan [InitializeCriticalSection](/windows/win32/api/synchapi/nf-synchapi-initializecriticalsection)Win32 işlevini çağırır.

## <a name="ccomautocriticalsectionccomautocriticalsection"></a><a name="dtor"></a>Ccomautocriticalhandle bölümü:: ~ Ccomautocriticalhandle bölümü

Yok edicisi.

```
~CComAutoCriticalSection() throw();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı, kritik bölüm nesnesi tarafından kullanılan tüm sistem kaynaklarını serbest bırakarak [Deletecriticalhandle bölümünü](/windows/win32/api/synchapi/nf-synchapi-deletecriticalsection)çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[CComFakeCriticalSection sınıfı](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Ccomcriticalhandle bölüm sınıfı](../../atl/reference/ccomcriticalsection-class.md)
