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
ms.openlocfilehash: b862d6b0fc99184232621432ec1c2a1027f8a9d5
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37881509"
---
# <a name="ipersiststreaminitimpl-class"></a>Ipersiststreamınitımpl sınıfı
Bu sınıfın uyguladığı `IUnknown` ve varsayılan bir uygulama sağlar [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) arabirimi.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>  
class ATL_NO_VTABLE IPersistStreamInitImpl 
   : public IPersistStreamInit
```  
  
#### <a name="parameters"></a>Parametreler  
 *T*  
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
 [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) nesnenizin yükler ve kalıcı verilerini tek bir akışın kaydeder istemek bir istemci arabirimi sağlar. Sınıf `IPersistStreamInitImpl` bu arabirimin bir varsayılan uygulamasını sağlar ve uygulayan `IUnknown` dökümünü almak için bilgi göndererek hata ayıklama cihazı oluşturur.  
  
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
 Bkz: [IPersist::GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) Windows SDK içinde.  
  
##  <a name="getsizemax"></a>  IPersistStreamInitImpl::GetSizeMax  
 Nesnenin veri kaydetmek için gereken akışı VHD'nin boyutunu alır.  
  
```
STDMETHOD(GetSizeMax)(ULARGE_INTEGER FAR* pcbSize);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 E_NOTIMPL döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPersistStreamInit::GetSizeMax](http://msdn.microsoft.com/library/windows/desktop/ms687287) Windows SDK içinde.  
  
##  <a name="initnew"></a>  IPersistStreamInitImpl::InitNew  
 Yeni oluşturulan nesneyi başlatır.  
  
```
STDMETHOD(InitNew)();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPersistStreamInit::InitNew](http://msdn.microsoft.com/library/windows/desktop/ms690234) Windows SDK içinde.  
  
##  <a name="isdirty"></a>  IPersistStreamInitImpl::IsDirty  
 Nesne verileri son kez kaydedildiğinden beri değiştirilip değiştirilmediğini denetler.  
  
```
STDMETHOD(IsDirty)();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPersistStreamInit::IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms680092) Windows SDK içinde.  
  
##  <a name="load"></a>  IPersistStreamInitImpl::Load  
 Nesnenin özelliklerini belirtilen akışından yükler.  
  
```
STDMETHOD(Load)(LPSTREAM pStm);
```  
  
### <a name="remarks"></a>Açıklamalar  
 ATL, bu bilgileri almak için nesnenin özellik eşlemesi kullanır.  
  
 Bkz: [IPersistStreamInit::Load](http://msdn.microsoft.com/library/windows/desktop/ms680730) Windows SDK içinde.  
  
##  <a name="save"></a>  IPersistStreamInitImpl::Save  
 Nesnenin özelliklerini, belirtilen akışa kaydeder.  
  
```
STDMETHOD(Save)(LPSTREAM pStm, BOOL fClearDirty);
```  
  
### <a name="remarks"></a>Açıklamalar  
 ATL nesnenin özellik eşlemesi bu bilgileri depolamak için kullanır.  
  
 Bkz: [IPersistStreamInit::Save](http://msdn.microsoft.com/library/windows/desktop/ms694439) Windows SDK içinde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Depolar ve akışlar](http://msdn.microsoft.com/library/windows/desktop/aa380352)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
