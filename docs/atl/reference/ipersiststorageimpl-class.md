---
description: ': IPersistStorageImpl sınıfı hakkında daha fazla bilgi'
title: IPersistStorageImpl sınıfı
ms.date: 11/04/2016
f1_keywords:
- IPersistStorageImpl
- ATLCOM/ATL::IPersistStorageImpl
- ATLCOM/ATL::IPersistStorageImpl::GetClassID
- ATLCOM/ATL::IPersistStorageImpl::HandsOffStorage
- ATLCOM/ATL::IPersistStorageImpl::InitNew
- ATLCOM/ATL::IPersistStorageImpl::IsDirty
- ATLCOM/ATL::IPersistStorageImpl::Load
- ATLCOM/ATL::IPersistStorageImpl::Save
- ATLCOM/ATL::IPersistStorageImpl::SaveCompleted
helpviewer_keywords:
- storage, ATL
- IPersistStorageImpl class
ms.assetid: d652f02c-239c-47c7-9a50-3e9fc3014fff
ms.openlocfilehash: 1d3d996886b587c25988139eed62e409650b5d4e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139340"
---
# <a name="ipersiststorageimpl-class"></a>IPersistStorageImpl sınıfı

Bu sınıf, [IPersistStorage](/windows/win32/api/objidl/nn-objidl-ipersiststorage) arabirimini uygular.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class ATL_NO_VTABLE IPersistStorageImpl : public IPersistStorage
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, öğesinden türetilir `IPersistStorageImpl` .

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IPersistStorageImpl:: GetClassID](#getclassid)|Nesnenin CLSID 'sini alır.|
|[IPersistStorageImpl:: HandsOffStorage](#handsoffstorage)|Nesneye tüm depolama nesnelerini serbest bırakmasını ve HandsOff modunu girmelerini söyler. ATL uygulama S_OK döndürür.|
|[IPersistStorageImpl:: InitNew](#initnew)|Yeni bir depolama alanı başlatır.|
|[IPersistStorageImpl:: IsDirty](#isdirty)|Nesnenin verilerinin son kaydedilmesinden bu yana değişip değişmediğini denetler.|
|[IPersistStorageImpl:: Load](#load)|Nesnenin özelliklerini belirtilen depolamadan yükler.|
|[IPersistStorageImpl:: Save](#save)|Nesnenin özelliklerini belirtilen depolamaya kaydeder.|
|[IPersistStorageImpl:: SaveCompleted](#savecompleted)|Bir nesneye, kendi depolama nesnesine yazmak için normal moda dönebildii bildirir. ATL uygulama S_OK döndürür.|

## <a name="remarks"></a>Açıklamalar

`IPersistStorageImpl` bir istemcinin, nesne yükleme ve kalıcı verilerini depolama kullanarak kaydetmesine izin veren [IPersistStorage](/windows/win32/api/objidl/nn-objidl-ipersiststorage) arabirimini uygular.

Bu sınıfın uygulanması, `T` ile kullanılabilir arabirimin bir uygulamasını oluşturmak için sınıfını gerektirir `IPersistStreamInit` `QueryInterface` . Genellikle bu `T` , sınıfın [ıpersiststreaminimpl](../../atl/reference/ipersiststreaminitimpl-class.md)öğesinden türetilmesi, com haritasında için bir giriş sağlamasıdır `IPersistStreamInit` ve [](com-map-macros.md)sınıfın kalıcı verilerini anlatmak için bir [özellik eşlemesi](property-map-macros.md) kullanmanız anlamına gelir.

**Ilgili makaleler** [ATL öğreticisi](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IPersistStorage`

`IPersistStorageImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="ipersiststorageimplgetclassid"></a><a name="getclassid"></a> IPersistStorageImpl:: GetClassID

Nesnenin CLSID 'sini alır.

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [IPersist:: GetClassID](/windows/win32/api/objidl/nf-objidl-ipersist-getclassid) .

## <a name="ipersiststorageimplhandsoffstorage"></a><a name="handsoffstorage"></a> IPersistStorageImpl:: HandsOffStorage

Nesneye tüm depolama nesnelerini serbest bırakmasını ve HandsOff modunu girmelerini söyler.

```
STDMETHOD(HandsOffStorage)(void);
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK bkz. [IPersistStorage:: HandsOffStorage](/windows/win32/api/objidl/nf-objidl-ipersiststorage-handsoffstorage) .

## <a name="ipersiststorageimplinitnew"></a><a name="initnew"></a> IPersistStorageImpl:: InitNew

Yeni bir depolama alanı başlatır.

```
STDMETHOD(InitNew)(IStorage*);
```

### <a name="remarks"></a>Açıklamalar

ATL uygulaması [ıpersiststreaminit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) arabirimine temsilci seçer.

Windows SDK [IPersistStorage: InitNew](/windows/win32/api/objidl/nf-objidl-ipersiststorage-initnew) öğesine bakın.

## <a name="ipersiststorageimplisdirty"></a><a name="isdirty"></a> IPersistStorageImpl:: IsDirty

Nesnenin verilerinin son kaydedilmesinden bu yana değişip değişmediğini denetler.

```
STDMETHOD(IsDirty)(void);
```

### <a name="remarks"></a>Açıklamalar

ATL uygulaması [ıpersiststreaminit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) arabirimine temsilci seçer.

Bkz. [IPersistStorage: Windows SDK IsDirty](/windows/win32/api/objidl/nf-objidl-ipersiststorage-isdirty) .

## <a name="ipersiststorageimplload"></a><a name="load"></a> IPersistStorageImpl:: Load

Nesnenin özelliklerini belirtilen depolamadan yükler.

```
STDMETHOD(Load)(IStorage* pStorage);
```

### <a name="remarks"></a>Açıklamalar

ATL uygulaması [ıpersiststreaminit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) arabirimine temsilci seçer. `Load` nesnenin verilerini almak için "Contents" adlı bir akış kullanır. [Kaydet](#save) yöntemi başlangıçta bu akışı oluşturur.

Bkz. [IPersistStorage: Windows SDK yükleme](/windows/win32/api/objidl/nf-objidl-ipersiststorage-load) .

## <a name="ipersiststorageimplsave"></a><a name="save"></a> IPersistStorageImpl:: Save

Nesnenin özelliklerini belirtilen depolamaya kaydeder.

```
STDMETHOD(Save)(IStorage* pStorage, BOOL fSameAsLoad);
```

### <a name="remarks"></a>Açıklamalar

ATL uygulaması [ıpersiststreaminit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) arabirimine temsilci seçer. `Save`İlk kez çağrıldığında, belirtilen depolamada "Contents" adlı bir akış oluşturur. Bu akış daha sonra `Save` [yüklemek](#load)için çağrılarında ve çağrılarına daha sonra kullanılır.

Bkz. [IPersistStorage: Windows SDK kaydetme](/windows/win32/api/objidl/nf-objidl-ipersiststorage-save) .

## <a name="ipersiststorageimplsavecompleted"></a><a name="savecompleted"></a> IPersistStorageImpl:: SaveCompleted

Bir nesneye, kendi depolama nesnesine yazmak için normal moda dönebildii bildirir.

```
STDMETHOD(SaveCompleted)(IStorage*);
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK [IPersistStorage: SaveCompleted](/windows/win32/api/objidl/nf-objidl-ipersiststorage-savecompleted) öğesine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Storages ve akışlar](/windows/win32/Stg/storages-and-streams)<br/>
[Ipersiststreaminimpl sınıfı](../../atl/reference/ipersiststreaminitimpl-class.md)<br/>
[Ipersistpropertybagimpl sınıfı](../../atl/reference/ipersistpropertybagimpl-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
