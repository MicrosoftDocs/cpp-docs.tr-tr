---
title: Ipersiststreamınitımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IPersistStreamInitImpl
- ATLCOM/ATL::IPersistStreamInitImpl
- ATLCOM/ATL::IPersistStreamInitImpl::GetClassID
- ATLCOM/ATL::IPersistStreamInitImpl::GetSizeMax
- ATLCOM/ATL::IPersistStreamInitImpl::InitNew
- ATLCOM/ATL::IPersistStreamInitImpl::IsDirty
- ATLCOM/ATL::IPersistStreamInitImpl::Load
- ATLCOM/ATL::IPersistStreamInitImpl::Save
dev_langs:
- C++
helpviewer_keywords:
- IPersistStreamInit ATL implementation
- IPersistStreamInitImpl class
- streams, ATL
ms.assetid: ef217c3c-020f-4cf8-871e-ef68e57865b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0deea6b4657b4b116b79c8472724f7c9d34dade8
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50075612"
---
# <a name="ipersiststreaminitimpl-class"></a>Ipersiststreamınitımpl sınıfı

Bu sınıfın uyguladığı `IUnknown` ve varsayılan bir uygulama sağlar [IPersistStreamInit](/windows/desktop/api/ocidl/nn-ocidl-ipersiststreaminit) arabirimi.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class ATL_NO_VTABLE IPersistStreamInitImpl
   : public IPersistStreamInit
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, türetilen `IPersistStreamInitImpl`.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IPersistStreamInitImpl::GetClassID](#getclassid)|Nesnenin CLSID alır.|
|[IPersistStreamInitImpl::GetSizeMax](#getsizemax)|Nesnenin veri kaydetmek için gereken akışı VHD'nin boyutunu alır. ATL uygulamasını E_NOTIMPL döndürür.|
|[IPersistStreamInitImpl::InitNew](#initnew)|Yeni oluşturulan nesneyi başlatır.|
|[IPersistStreamInitImpl::IsDirty](#isdirty)|Nesne verileri son kez kaydedildiğinden beri değiştirilip değiştirilmediğini denetler.|
|[IPersistStreamInitImpl::Load](#load)|Nesnenin özelliklerini belirtilen akışından yükler.|
|[IPersistStreamInitImpl::Save](#save)|Nesnenin özelliklerini, belirtilen akışa kaydeder.|

## <a name="remarks"></a>Açıklamalar

[IPersistStreamInit](/windows/desktop/api/ocidl/nn-ocidl-ipersiststreaminit) nesnenizin yükler ve kalıcı verilerini tek bir akışın kaydeder istemek bir istemci arabirimi sağlar. Sınıf `IPersistStreamInitImpl` bu arabirimin bir varsayılan uygulamasını sağlar ve uygulayan `IUnknown` dökümünü almak için bilgi göndererek hata ayıklama cihazı oluşturur.

**İle ilgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IPersistStreamInit`

`IPersistStreamInitImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="getclassid"></a>  IPersistStreamInitImpl::GetClassID

Nesnenin CLSID alır.

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IPersist::GetClassID](/windows/desktop/api/objidl/nf-objidl-ipersist-getclassid) Windows SDK içinde.

##  <a name="getsizemax"></a>  IPersistStreamInitImpl::GetSizeMax

Nesnenin veri kaydetmek için gereken akışı VHD'nin boyutunu alır.

```
STDMETHOD(GetSizeMax)(ULARGE_INTEGER FAR* pcbSize);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz: [IPersistStreamInit::GetSizeMax](/windows/desktop/api/ocidl/nf-ocidl-ipersiststreaminit-getsizemax) Windows SDK içinde.

##  <a name="initnew"></a>  IPersistStreamInitImpl::InitNew

Yeni oluşturulan nesneyi başlatır.

```
STDMETHOD(InitNew)();
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IPersistStreamInit::InitNew](/windows/desktop/api/ocidl/nf-ocidl-ipersiststreaminit-initnew) Windows SDK içinde.

##  <a name="isdirty"></a>  IPersistStreamInitImpl::IsDirty

Nesne verileri son kez kaydedildiğinden beri değiştirilip değiştirilmediğini denetler.

```
STDMETHOD(IsDirty)();
```

### <a name="remarks"></a>Açıklamalar

Bkz: [IPersistStreamInit::IsDirty](/windows/desktop/api/ocidl/nf-ocidl-ipersiststreaminit-isdirty) Windows SDK içinde.

##  <a name="load"></a>  IPersistStreamInitImpl::Load

Nesnenin özelliklerini belirtilen akışından yükler.

```
STDMETHOD(Load)(LPSTREAM pStm);
```

### <a name="remarks"></a>Açıklamalar

ATL, bu bilgileri almak için nesnenin özellik eşlemesi kullanır.

Bkz: [IPersistStreamInit::Load](/windows/desktop/api/ocidl/nf-ocidl-ipersiststreaminit-load) Windows SDK içinde.

##  <a name="save"></a>  IPersistStreamInitImpl::Save

Nesnenin özelliklerini, belirtilen akışa kaydeder.

```
STDMETHOD(Save)(LPSTREAM pStm, BOOL fClearDirty);
```

### <a name="remarks"></a>Açıklamalar

ATL nesnenin özellik eşlemesi bu bilgileri depolamak için kullanır.

Bkz: [IPersistStreamInit::Save](/windows/desktop/api/ocidl/nf-ocidl-ipersiststreaminit-save) Windows SDK içinde.

## <a name="see-also"></a>Ayrıca Bkz.

[Depolar ve akışlar](/windows/desktop/Stg/storages-and-streams)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
