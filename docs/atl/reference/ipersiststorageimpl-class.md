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
ms.openlocfilehash: 634a7a7373f6686ad36b645a73613a4ae350bbab
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884707"
---
# <a name="ipersiststorageimpl-class"></a>Ipersiststorageımpl sınıfı
Bu sınıfın uyguladığı [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) arabirimi.  
  
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
 `IPersistStorageImpl` uygulayan [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) arabirimi, nesnesi yük istemek üzere bir istemci sağlayan ve kalıcı verilerini bir depolama kullanarak kaydedin.  
  
 Bu sınıfın uygulaması sınıfı gerektirir `T` uygulaması yapmak için `IPersistStreamInit` arabirimi aracılığıyla kullanılabilir `QueryInterface`. Genellikle bu sınıfın başka bir deyişle `T` türetilmesi [Ipersiststreamınitımpl](../../atl/reference/ipersiststreaminitimpl-class.md), sağlamak için bir giriş `IPersistStreamInit` içinde [COM eşlemesi](http://msdn.microsoft.com/library/ead2a1e3-334d-44ad-bb1f-b94bb14c2333)ve bir [özellik eşlemesi](http://msdn.microsoft.com/library/bfe30be6-62c3-4dc2-bd49-21ef96f15427) sınıfın kalıcı veriyi tanımlamak için.  
  
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
 Bkz: [IPersist::GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) Windows SDK içinde.  
  
##  <a name="handsoffstorage"></a>  IPersistStorageImpl::HandsOffStorage  
 Tüm depolama nesneleri serbest bırakma ve HandsOff moduna girmek için nesne bildirir.  
  
```
STDMETHOD(HandsOffStorage)(void);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPersistStorage::HandsOffStorage](http://msdn.microsoft.com/library/windows/desktop/ms679742) Windows SDK içinde.  
  
##  <a name="initnew"></a>  IPersistStorageImpl::InitNew  
 Yeni bir depolama başlatır.  
  
```
STDMETHOD(InitNew)(IStorage*);
```  
  
### <a name="remarks"></a>Açıklamalar  
 ATL uygulamasını temsilciler için [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) arabirimi.  
  
 Bkz: [IPersistStorage:InitNew](http://msdn.microsoft.com/library/windows/desktop/ms687194) Windows SDK içinde.  
  
##  <a name="isdirty"></a>  IPersistStorageImpl::IsDirty  
 Nesne verileri son kez kaydedildiğinden beri değiştirilip değiştirilmediğini denetler.  
  
```
STDMETHOD(IsDirty)(void);
```  
  
### <a name="remarks"></a>Açıklamalar  
 ATL uygulamasını temsilciler için [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) arabirimi.  
  
 Bkz: [IPersistStorage:IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms683910) Windows SDK içinde.  
  
##  <a name="load"></a>  IPersistStorageImpl::Load  
 Belirtilen depolama alanından nesnenin özelliklerini yükler.  
  
```
STDMETHOD(Load)(IStorage* pStorage);
```  
  
### <a name="remarks"></a>Açıklamalar  
 ATL uygulamasını temsilciler için [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) arabirimi. `Load` nesnenin veri almak için "İçerik" adlı bir akış'ı kullanır. [Kaydet](#save) yöntemi, başlangıçta bu akış oluşturur.  
  
 Bkz: [IPersistStorage:Load](http://msdn.microsoft.com/library/windows/desktop/ms680557) Windows SDK içinde.  
  
##  <a name="save"></a>  IPersistStorageImpl::Save  
 Nesnenin özelliklerini belirtilen depolama alanına kaydeder.  
  
```
STDMETHOD(Save)(IStorage* pStorage, BOOL fSameAsLoad);
```  
  
### <a name="remarks"></a>Açıklamalar  
 ATL uygulamasını temsilciler için [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) arabirimi. Zaman `Save` ilk adlı, belirtilen depolama alanında "İçerik" adlı bir akış oluşturur. Bu akış ardından sonraki çağrılarda kullanılan `Save` ve [yük](#load).  
  
 Bkz: [IPersistStorage:Save](http://msdn.microsoft.com/library/windows/desktop/ms680680) Windows SDK içinde.  
  
##  <a name="savecompleted"></a>  IPersistStorageImpl::SaveCompleted  
 Kendi depolama nesnesine yazmak için Normal moda döndürebilen bir nesne bildirir.  
  
```
STDMETHOD(SaveCompleted)(IStorage*);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPersistStorage:SaveCompleted](http://msdn.microsoft.com/library/windows/desktop/ms679713) Windows SDK içinde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Depolar ve akışlar](http://msdn.microsoft.com/library/windows/desktop/aa380352)   
 [Ipersiststreamınitımpl sınıfı](../../atl/reference/ipersiststreaminitimpl-class.md)   
 [Ipersistpropertybagımpl sınıfı](../../atl/reference/ipersistpropertybagimpl-class.md)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
