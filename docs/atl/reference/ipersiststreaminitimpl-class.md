---
title: IPersistStreamInitImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- IPersistStreamInitImpl
- ATLCOM/ATL::IPersistStreamInitImpl
- ATLCOM/ATL::IPersistStreamInitImpl::GetClassID
- ATLCOM/ATL::IPersistStreamInitImpl::GetSizeMax
- ATLCOM/ATL::IPersistStreamInitImpl::InitNew
- ATLCOM/ATL::IPersistStreamInitImpl::IsDirty
- ATLCOM/ATL::IPersistStreamInitImpl::Load
- ATLCOM/ATL::IPersistStreamInitImpl::Save
helpviewer_keywords:
- IPersistStreamInit ATL implementation
- IPersistStreamInitImpl class
- streams, ATL
ms.assetid: ef217c3c-020f-4cf8-871e-ef68e57865b8
ms.openlocfilehash: 0d6ac4639ac0cfb97416ca80b7a2ec3903d7b8e6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326454"
---
# <a name="ipersiststreaminitimpl-class"></a>IPersistStreamInitImpl Sınıfı

Bu `IUnknown` [sınıf, IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) arabiriminin varsayılan uygulamasını uygular ve sağlar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class ATL_NO_VTABLE IPersistStreamInitImpl
   : public IPersistStreamInit
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `IPersistStreamInitImpl`türetilmiştir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IPersistStreamInitImpl::GetClassID](#getclassid)|Nesnenin CLSID'sini alır.|
|[IPersistStreamInitImpl::GetSizeMax](#getsizemax)|Nesnenin verilerini kaydetmek için gereken akışı n boyutunu alır. ATL uygulaması E_NOTIMPL döndürür.|
|[IpersistStreamInitImpl::InitNew](#initnew)|Yeni oluşturulan bir nesneyi başharfe ait hale leştirir.|
|[IPersistStreamInitImpl::Kirli](#isdirty)|Nesnenin verilerinin son kaydedildiği tarihten bu yana değişip değişmediğini denetler.|
|[IPersistStreamInitImpl::Yük](#load)|Nesnenin özelliklerini belirtilen akıştan yükler.|
|[IPersistStreamInitImpl::Kaydet](#save)|Nesnenin özelliklerini belirtilen akışa kaydeder.|

## <a name="remarks"></a>Açıklamalar

[IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) arabirimi, istemcinin nesnenizin kalıcı verilerini tek bir akışa yüklemesini ve kaydetmesini istemesine olanak tanır. Sınıf `IPersistStreamInitImpl` bu arabirimin varsayılan bir `IUnknown` uygulamasını sağlar ve hata ayıklama oluştururda dökümü aygıtına bilgi göndererek uygular.

**İlgili Makaleler** [ATL Tutorial](../../atl/active-template-library-atl-tutorial.md), [ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IPersistStreamInit`

`IPersistStreamInitImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="ipersiststreaminitimplgetclassid"></a><a name="getclassid"></a>IPersistStreamInitImpl::GetClassID

Nesnenin CLSID'sini alır.

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>Açıklamalar

Bkz. IPersist::Windows SDK'da [ClassID'yi alın.](/windows/win32/api/objidl/nf-objidl-ipersist-getclassid)

## <a name="ipersiststreaminitimplgetsizemax"></a><a name="getsizemax"></a>IPersistStreamInitImpl::GetSizeMax

Nesnenin verilerini kaydetmek için gereken akışı n boyutunu alır.

```
STDMETHOD(GetSizeMax)(ULARGE_INTEGER FAR* pcbSize);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IPersistStreamInit::Windows](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-getsizemax) SDK'da GetSizeMax.

## <a name="ipersiststreaminitimplinitnew"></a><a name="initnew"></a>IpersistStreamInitImpl::InitNew

Yeni oluşturulan bir nesneyi başharfe ait hale leştirir.

```
STDMETHOD(InitNew)();
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IPersistStreamInit::Windows](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-initnew) SDK'da Yeni.

## <a name="ipersiststreaminitimplisdirty"></a><a name="isdirty"></a>IPersistStreamInitImpl::Kirli

Nesnenin verilerinin son kaydedildiği tarihten bu yana değişip değişmediğini denetler.

```
STDMETHOD(IsDirty)();
```

### <a name="remarks"></a>Açıklamalar

Bkz. [IPersistStreamInit::Windows](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-isdirty) SDK'da Kirli.

## <a name="ipersiststreaminitimplload"></a><a name="load"></a>IPersistStreamInitImpl::Yük

Nesnenin özelliklerini belirtilen akıştan yükler.

```
STDMETHOD(Load)(LPSTREAM pStm);
```

### <a name="remarks"></a>Açıklamalar

ATL bu bilgileri almak için nesnenin özellik eşlemi kullanır.

Bkz. [IPersistStreamInit::Windows](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-load) SDK'da yükleyin.

## <a name="ipersiststreaminitimplsave"></a><a name="save"></a>IPersistStreamInitImpl::Kaydet

Nesnenin özelliklerini belirtilen akışa kaydeder.

```
STDMETHOD(Save)(LPSTREAM pStm, BOOL fClearDirty);
```

### <a name="remarks"></a>Açıklamalar

ATL, bu bilgileri depolamak için nesnenin özellik eşlesini kullanır.

Bkz. [IPersistStreamInit::Windows](/windows/win32/api/ocidl/nf-ocidl-ipersiststreaminit-save) SDK'da kaydedin.

## <a name="see-also"></a>Ayrıca bkz.

[Depolama ve Akışlar](/windows/win32/Stg/storages-and-streams)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
