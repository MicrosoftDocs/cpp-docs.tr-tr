---
title: "IPersistStorageImpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
helpviewer_keywords:
- storage, ATL
- IPersistStorageImpl class
ms.assetid: d652f02c-239c-47c7-9a50-3e9fc3014fff
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0bb02425c906a9d468d53691469dd7e418afcad3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ipersiststorageimpl-class"></a>IPersistStorageImpl sınıfı
Bu sınıf uygulayan [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) arabirimi.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>  
class ATL_NO_VTABLE IPersistStorageImpl : public IPersistStorage
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `IPersistStorageImpl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IPersistStorageImpl::GetClassID](#getclassid)|Nesnenin CLSID alır.|  
|[IPersistStorageImpl::HandsOffStorage](#handsoffstorage)|Tüm depolama nesneleri serbest bırakır ve HandsOff moduna nesnesine bildirir. ATL uygulamasını döndürür `S_OK`.|  
|[IPersistStorageImpl::InitNew](#initnew)|Yeni bir depolama birimi başlatır.|  
|[IPersistStorageImpl::IsDirty](#isdirty)|Son kaydedilişinden nesnenin veri değişip değişmediğini denetler.|  
|[IPersistStorageImpl::Load](#load)|Belirtilen depolama biriminden nesnenin özelliklerini yükler.|  
|[IPersistStorageImpl::Save](#save)|Nesnenin özelliklerini belirtilen depolama alanına kaydeder.|  
|[IPersistStorageImpl::SaveCompleted](#savecompleted)|Kendi depolama nesnesi yazmak için Normal moduna geri dönebilirsiniz nesneyi bildirir. ATL uygulamasını döndürür `S_OK`.|  
  
## <a name="remarks"></a>Açıklamalar  
 `IPersistStorageImpl`uygulayan [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) arabirimi, nesne yük istemek üzere bir istemci sağlayan ve bir depolama kullanarak kendi kalıcı veri kaydedin.  
  
 Bu sınıfın sınıfı gerektirir `T` uygulaması yapmak için `IPersistStreamInit` arabirimi aracılığıyla kullanılabilen `QueryInterface`. Genellikle bu o sınıfın gelir `T` öğesinden türetilmelidir [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md), için bir girdi sağlayın `IPersistStreamInit` içinde [COM eşlemesi](http://msdn.microsoft.com/library/ead2a1e3-334d-44ad-bb1f-b94bb14c2333)ve bir [özellik eşlemesi](http://msdn.microsoft.com/library/bfe30be6-62c3-4dc2-bd49-21ef96f15427) sınıfının kalıcı veri açıklamak için.  
  
 **İlgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [bir ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IPersistStorage`  
  
 `IPersistStorageImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="getclassid"></a>IPersistStorageImpl::GetClassID  
 Nesnenin CLSID alır.  
  
```
STDMETHOD(GetClassID)(CLSID* pClassID);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPersist::GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) Windows SDK.  
  
##  <a name="handsoffstorage"></a>IPersistStorageImpl::HandsOffStorage  
 Tüm depolama nesneleri serbest bırakır ve HandsOff moduna nesnesine bildirir.  
  
```
STDMETHOD(HandsOffStorage)(void);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPersistStorage::HandsOffStorage](http://msdn.microsoft.com/library/windows/desktop/ms679742) Windows SDK.  
  
##  <a name="initnew"></a>IPersistStorageImpl::InitNew  
 Yeni bir depolama birimi başlatır.  
  
```
STDMETHOD(InitNew)(IStorage*);
```  
  
### <a name="remarks"></a>Açıklamalar  
 ATL uygulamasını temsilci için [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) arabirimi.  
  
 Bkz: [IPersistStorage:InitNew](http://msdn.microsoft.com/library/windows/desktop/ms687194) Windows SDK.  
  
##  <a name="isdirty"></a>IPersistStorageImpl::IsDirty  
 Son kaydedilişinden nesnenin veri değişip değişmediğini denetler.  
  
```
STDMETHOD(IsDirty)(void);
```  
  
### <a name="remarks"></a>Açıklamalar  
 ATL uygulamasını temsilci için [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) arabirimi.  
  
 Bkz: [IPersistStorage:IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms683910) Windows SDK.  
  
##  <a name="load"></a>IPersistStorageImpl::Load  
 Belirtilen depolama biriminden nesnenin özelliklerini yükler.  
  
```
STDMETHOD(Load)(IStorage* pStorage);
```  
  
### <a name="remarks"></a>Açıklamalar  
 ATL uygulamasını temsilci için [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) arabirimi. **Yük** "İçerik" adlı bir akış nesnenin veri almak için kullanır. [Kaydetmek](#save) yöntemi ilk olarak, bu akış oluşturur.  
  
 Bkz: [IPersistStorage:Load](http://msdn.microsoft.com/library/windows/desktop/ms680557) Windows SDK.  
  
##  <a name="save"></a>IPersistStorageImpl::Save  
 Nesnenin özelliklerini belirtilen depolama alanına kaydeder.  
  
```
STDMETHOD(Save)(IStorage* pStorage, BOOL fSameAsLoad);
```  
  
### <a name="remarks"></a>Açıklamalar  
 ATL uygulamasını temsilci için [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) arabirimi. Zaman **kaydetmek** ilk adlı, belirtilen depolama "İçerik" adlı bir akış oluşturur. Bu akış ardından sonraki çağrılarında kullanılan **kaydetmek** ve [yük](#load).  
  
 Bkz: [IPersistStorage:Save](http://msdn.microsoft.com/library/windows/desktop/ms680680) Windows SDK.  
  
##  <a name="savecompleted"></a>IPersistStorageImpl::SaveCompleted  
 Kendi depolama nesnesi yazmak için Normal moduna geri dönebilirsiniz nesneyi bildirir.  
  
```
STDMETHOD(SaveCompleted)(IStorage*);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPersistStorage:SaveCompleted](http://msdn.microsoft.com/library/windows/desktop/ms679713) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Depolar ve akışlar](http://msdn.microsoft.com/library/windows/desktop/aa380352)   
 [IPersistStreamInitImpl sınıfı](../../atl/reference/ipersiststreaminitimpl-class.md)   
 [IPersistPropertyBagImpl sınıfı](../../atl/reference/ipersistpropertybagimpl-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
