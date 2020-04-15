---
title: IPersistStorageImpl Sınıfı
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
ms.openlocfilehash: b235b190f237293932705e4d290ac963088722f3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326478"
---
# <a name="ipersiststorageimpl-class"></a>IPersistStorageImpl Sınıfı

Bu sınıf [IPersistStorage](/windows/win32/api/objidl/nn-objidl-ipersiststorage) arabirimini uygular.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class ATL_NO_VTABLE IPersistStorageImpl : public IPersistStorage
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `IPersistStorageImpl`türetilmiştir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IPersistStorageImpl::GetClassID](#getclassid)|Nesnenin CLSID'sini alır.|
|[IPersistStorageImpl::HandsOffStorage](#handsoffstorage)|Nesneye tüm depolama nesnelerini serbest bırakmasını ve HandsOff moduna girmesini bildirir. ATL uygulaması S_OK döndürür.|
|[IPersistStorageImpl::InitNew](#initnew)|Yeni bir deponun başlatılmasını sağlar.|
|[IPersistStorageImpl::IsDirty](#isdirty)|Nesnenin verilerinin son kaydedildiği tarihten bu yana değişip değişmediğini denetler.|
|[IPersistStorageImpl::Yük](#load)|Nesnenin özelliklerini belirtilen depolamadan yükler.|
|[IPersistStorageImpl::Kaydet](#save)|Nesnenin özelliklerini belirtilen depolama alanına kaydeder.|
|[IPersistStorageImpl::SaveCompleted](#savecompleted)|Bir nesneyi depolama nesnesine yazmak için Normal modda dönebileceğini belirtir. ATL uygulaması S_OK döndürür.|

## <a name="remarks"></a>Açıklamalar

`IPersistStorageImpl`bir istemcinin nesneyükünüzü yüklemesini ve kalıcı verilerini bir depolama kullanarak kaydetmesini istemesine olanak tanıyan [IPersistStorage](/windows/win32/api/objidl/nn-objidl-ipersiststorage) arabirimini uygular.

Bu sınıfın uygulanması, `T` `IPersistStreamInit` sınıfın arabirimin bir uygulamasını `QueryInterface`kullanılabilir hale getirmesini gerektirir. Genellikle bu, sınıfın `T` [IPersistStreamInitImpl'den](../../atl/reference/ipersiststreaminitimpl-class.md)türemesi, `IPersistStreamInit` COM [haritasında](com-map-macros.md)bir giriş sağlaması ve sınıfın kalıcı verilerini açıklamak için bir [özellik eşlemesi](property-map-macros.md) kullanması gerektiği anlamına gelir.

**İlgili Makaleler** [ATL Tutorial](../../atl/active-template-library-atl-tutorial.md), [ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IPersistStorage`

`IPersistStorageImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="ipersiststorageimplgetclassid"></a><a name="getclassid"></a>IPersistStorageImpl::GetClassID

Nesnenin CLSID'sini alır.

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>Açıklamalar

Bkz. IPersist::Windows SDK'da [ClassID'yi alın.](/windows/win32/api/objidl/nf-objidl-ipersist-getclassid)

## <a name="ipersiststorageimplhandsoffstorage"></a><a name="handsoffstorage"></a>IPersistStorageImpl::HandsOffStorage

Nesneye tüm depolama nesnelerini serbest bırakmasını ve HandsOff moduna girmesini bildirir.

```
STDMETHOD(HandsOffStorage)(void);
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IPersistStorage::HandsOffStorage](/windows/win32/api/objidl/nf-objidl-ipersiststorage-handsoffstorage) Windows SDK içinde.

## <a name="ipersiststorageimplinitnew"></a><a name="initnew"></a>IPersistStorageImpl::InitNew

Yeni bir deponun başlatılmasını sağlar.

```
STDMETHOD(InitNew)(IStorage*);
```

### <a name="remarks"></a>Açıklamalar

ATL uygulama temsilcileri [IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) arabirimine bağlanır.

Bkz. [IPersistStorage:InitNew](/windows/win32/api/objidl/nf-objidl-ipersiststorage-initnew) in the Windows SDK.

## <a name="ipersiststorageimplisdirty"></a><a name="isdirty"></a>IPersistStorageImpl::IsDirty

Nesnenin verilerinin son kaydedildiği tarihten bu yana değişip değişmediğini denetler.

```
STDMETHOD(IsDirty)(void);
```

### <a name="remarks"></a>Açıklamalar

ATL uygulama temsilcileri [IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) arabirimine bağlanır.

Bkz. [IPersistStorage:Windows](/windows/win32/api/objidl/nf-objidl-ipersiststorage-isdirty) SDK'da Kirli.

## <a name="ipersiststorageimplload"></a><a name="load"></a>IPersistStorageImpl::Yük

Nesnenin özelliklerini belirtilen depolamadan yükler.

```
STDMETHOD(Load)(IStorage* pStorage);
```

### <a name="remarks"></a>Açıklamalar

ATL uygulama temsilcileri [IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) arabirimine bağlanır. `Load`nesnenin verilerini almak için "İçerik" adlı bir akış kullanır. [Kaydet](#save) yöntemi özgün olarak bu akışı oluşturur.

Bkz. [IPersistStorage:Windows](/windows/win32/api/objidl/nf-objidl-ipersiststorage-load) SDK'da yükleyin.

## <a name="ipersiststorageimplsave"></a><a name="save"></a>IPersistStorageImpl::Kaydet

Nesnenin özelliklerini belirtilen depolama alanına kaydeder.

```
STDMETHOD(Save)(IStorage* pStorage, BOOL fSameAsLoad);
```

### <a name="remarks"></a>Açıklamalar

ATL uygulama temsilcileri [IPersistStreamInit](/windows/win32/api/ocidl/nn-ocidl-ipersiststreaminit) arabirimine bağlanır. İlk `Save` çağrıldığında, belirtilen depolama üzerinde "İçerik" adlı bir akış oluşturur. Bu akış daha sonra yük `Save` aramalarında ve [Yükleme](#load)aramalarında kullanılır.

Bkz. [IPersistStorage:Windows](/windows/win32/api/objidl/nf-objidl-ipersiststorage-save) SDK'da kaydedin.

## <a name="ipersiststorageimplsavecompleted"></a><a name="savecompleted"></a>IPersistStorageImpl::SaveCompleted

Bir nesneyi depolama nesnesine yazmak için Normal modda dönebileceğini belirtir.

```
STDMETHOD(SaveCompleted)(IStorage*);
```

### <a name="return-value"></a>Dönüş Değeri

S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IPersistStorage:Windows](/windows/win32/api/objidl/nf-objidl-ipersiststorage-savecompleted) SDK'da Tamamlandı.

## <a name="see-also"></a>Ayrıca bkz.

[Depolama ve Akışlar](/windows/win32/Stg/storages-and-streams)<br/>
[IPersistStreamInitImpl Sınıfı](../../atl/reference/ipersiststreaminitimpl-class.md)<br/>
[IPersistPropertyBagImpl Sınıfı](../../atl/reference/ipersistpropertybagimpl-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
