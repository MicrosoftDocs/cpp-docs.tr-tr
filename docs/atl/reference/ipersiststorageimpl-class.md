---
title: Ipersiststorageımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- storage, ATL
- IPersistStorageImpl class
ms.assetid: d652f02c-239c-47c7-9a50-3e9fc3014fff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7a337743ece9edfa71a052ee9d6e19728b0c051
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693722"
---
# <a name="ipersiststorageimpl-class"></a>Ipersiststorageımpl sınıfı
Bu sınıfın uyguladığı [IPersistStorage](/windows/desktop/api/objidl/nn-objidl-ipersiststorage) arabirimi.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>  
class ATL_NO_VTABLE IPersistStorageImpl : public IPersistStorage
```  
  
#### <a name="parameters"></a>Parametreler  
 *T*  
 Sınıfınız, türetilen `IPersistStorageImpl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IPersistStorageImpl::GetClassID](#getclassid)|Nesnenin CLSID alır.|  
|[IPersistStorageImpl::HandsOffStorage](#handsoffstorage)|Tüm depolama nesneleri serbest bırakma ve HandsOff moduna girmek için nesne bildirir. ATL uygulamasını S_OK döndürür.|  
|[IPersistStorageImpl::InitNew](#initnew)|Yeni bir depolama başlatır.|  
|[IPersistStorageImpl::IsDirty](#isdirty)|Nesne verileri son kez kaydedildiğinden beri değiştirilip değiştirilmediğini denetler.|  
|[IPersistStorageImpl::Load](#load)|Belirtilen depolama alanından nesnenin özelliklerini yükler.|  
|[IPersistStorageImpl::Save](#save)|Nesnenin özelliklerini belirtilen depolama alanına kaydeder.|  
|[IPersistStorageImpl::SaveCompleted](#savecompleted)|Kendi depolama nesnesine yazmak için Normal moda döndürebilen bir nesne bildirir. ATL uygulamasını S_OK döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 `IPersistStorageImpl` uygulayan [IPersistStorage](/windows/desktop/api/objidl/nn-objidl-ipersiststorage) arabirimi, nesnesi yük istemek üzere bir istemci sağlayan ve kalıcı verilerini bir depolama kullanarak kaydedin.  
  
 Bu sınıfın uygulaması sınıfı gerektirir `T` uygulaması yapmak için `IPersistStreamInit` arabirimi aracılığıyla kullanılabilir `QueryInterface`. Genellikle bu sınıfın başka bir deyişle `T` türetilmesi [Ipersiststreamınitımpl](../../atl/reference/ipersiststreaminitimpl-class.md), sağlamak için bir giriş `IPersistStreamInit` içinde [COM eşlemesi](com-map-macros.md)ve bir [özellik eşlemesi](property-map-macros.md) sınıfın kalıcı veriyi tanımlamak için.  
  
 **İle ilgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IPersistStorage`  
  
 `IPersistStorageImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="getclassid"></a>  IPersistStorageImpl::GetClassID  
 Nesnenin CLSID alır.  
  
```
STDMETHOD(GetClassID)(CLSID* pClassID);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPersist::GetClassID](/windows/desktop/api/objidl/nf-objidl-ipersist-getclassid) Windows SDK içinde.  
  
##  <a name="handsoffstorage"></a>  IPersistStorageImpl::HandsOffStorage  
 Tüm depolama nesneleri serbest bırakma ve HandsOff moduna girmek için nesne bildirir.  
  
```
STDMETHOD(HandsOffStorage)(void);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPersistStorage::HandsOffStorage](/windows/desktop/api/objidl/nf-objidl-ipersiststorage-handsoffstorage) Windows SDK içinde.  
  
##  <a name="initnew"></a>  IPersistStorageImpl::InitNew  
 Yeni bir depolama başlatır.  
  
```
STDMETHOD(InitNew)(IStorage*);
```  
  
### <a name="remarks"></a>Açıklamalar  
 ATL uygulamasını temsilciler için [IPersistStreamInit](/windows/desktop/api/ocidl/nn-ocidl-ipersiststreaminit) arabirimi.  
  
 Bkz: [IPersistStorage:InitNew](/windows/desktop/api/objidl/nf-objidl-ipersiststorage-initnew) Windows SDK içinde.  
  
##  <a name="isdirty"></a>  IPersistStorageImpl::IsDirty  
 Nesne verileri son kez kaydedildiğinden beri değiştirilip değiştirilmediğini denetler.  
  
```
STDMETHOD(IsDirty)(void);
```  
  
### <a name="remarks"></a>Açıklamalar  
 ATL uygulamasını temsilciler için [IPersistStreamInit](/windows/desktop/api/ocidl/nn-ocidl-ipersiststreaminit) arabirimi.  
  
 Bkz: [IPersistStorage:IsDirty](/windows/desktop/api/objidl/nf-objidl-ipersiststorage-isdirty) Windows SDK içinde.  
  
##  <a name="load"></a>  IPersistStorageImpl::Load  
 Belirtilen depolama alanından nesnenin özelliklerini yükler.  
  
```
STDMETHOD(Load)(IStorage* pStorage);
```  
  
### <a name="remarks"></a>Açıklamalar  
 ATL uygulamasını temsilciler için [IPersistStreamInit](/windows/desktop/api/ocidl/nn-ocidl-ipersiststreaminit) arabirimi. `Load` nesnenin veri almak için "İçerik" adlı bir akış'ı kullanır. [Kaydet](#save) yöntemi, başlangıçta bu akış oluşturur.  
  
 Bkz: [IPersistStorage:Load](/windows/desktop/api/objidl/nf-objidl-ipersiststorage-load) Windows SDK içinde.  
  
##  <a name="save"></a>  IPersistStorageImpl::Save  
 Nesnenin özelliklerini belirtilen depolama alanına kaydeder.  
  
```
STDMETHOD(Save)(IStorage* pStorage, BOOL fSameAsLoad);
```  
  
### <a name="remarks"></a>Açıklamalar  
 ATL uygulamasını temsilciler için [IPersistStreamInit](/windows/desktop/api/ocidl/nn-ocidl-ipersiststreaminit) arabirimi. Zaman `Save` ilk adlı, belirtilen depolama alanında "İçerik" adlı bir akış oluşturur. Bu akış ardından sonraki çağrılarda kullanılan `Save` ve [yük](#load).  
  
 Bkz: [IPersistStorage:Save](/windows/desktop/api/objidl/nf-objidl-ipersiststorage-save) Windows SDK içinde.  
  
##  <a name="savecompleted"></a>  IPersistStorageImpl::SaveCompleted  
 Kendi depolama nesnesine yazmak için Normal moda döndürebilen bir nesne bildirir.  
  
```
STDMETHOD(SaveCompleted)(IStorage*);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPersistStorage:SaveCompleted](/windows/desktop/api/objidl/nf-objidl-ipersiststorage-savecompleted) Windows SDK içinde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Depolar ve akışlar](/windows/desktop/Stg/storages-and-streams)   
 [Ipersiststreamınitımpl sınıfı](../../atl/reference/ipersiststreaminitimpl-class.md)   
 [Ipersistpropertybagımpl sınıfı](../../atl/reference/ipersistpropertybagimpl-class.md)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
