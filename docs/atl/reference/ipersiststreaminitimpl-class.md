---
title: IPersistStreamInitImpl sınıfı | Microsoft Docs
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
ms.openlocfilehash: a51dd5e198a86b7bb17a6182c1edb098f23a8e47
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ipersiststreaminitimpl-class"></a>IPersistStreamInitImpl sınıfı
Bu sınıf uygulayan **IUnknown** ve bir varsayılan uygulamayı sağlar [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) arabirimi.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>  
class ATL_NO_VTABLE IPersistStreamInitImpl 
   : public IPersistStreamInit
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `IPersistStreamInitImpl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IPersistStreamInitImpl::GetClassID](#getclassid)|Nesnenin CLSID alır.|  
|[IPersistStreamInitImpl::GetSizeMax](#getsizemax)|Nesnenin verileri kaydetmek için gereken akış boyutunun alır. ATL uygulamasını döndürür **E_NOTIMPL**.|  
|[IPersistStreamInitImpl::InitNew](#initnew)|Yeni oluşturulan nesnesini başlatır.|  
|[IPersistStreamInitImpl::IsDirty](#isdirty)|Son kaydedilişinden nesnenin veri değişip değişmediğini denetler.|  
|[IPersistStreamInitImpl::Load](#load)|Nesnenin özelliklerini belirtilen akıştan yükler.|  
|[IPersistStreamInitImpl::Save](#save)|Nesnenin özelliklerini belirtilen akışa kaydeder.|  
  
## <a name="remarks"></a>Açıklamalar  
 [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) arabirimi nesnenizin yükler ve kalıcı verilerini tek bir akışa kaydeder istemek bir istemci izin verir. Sınıf `IPersistStreamInitImpl` bu arabirimin varsayılan uygulamasını sağlar ve uygulayan **IUnknown** aygıt hata ayıklama dökümü bilgileri göndererek oluşturur.  
  
 **İlgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [bir ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)  
  
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
 Bkz: [IPersist::GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) Windows SDK.  
  
##  <a name="getsizemax"></a>  IPersistStreamInitImpl::GetSizeMax  
 Nesnenin verileri kaydetmek için gereken akış boyutunun alır.  
  
```
STDMETHOD(GetSizeMax)(ULARGE_INTEGER FAR* pcbSize);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **E_NOTIMPL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPersistStreamInit::GetSizeMax](http://msdn.microsoft.com/library/windows/desktop/ms687287) Windows SDK.  
  
##  <a name="initnew"></a>  IPersistStreamInitImpl::InitNew  
 Yeni oluşturulan nesnesini başlatır.  
  
```
STDMETHOD(InitNew)();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPersistStreamInit::InitNew](http://msdn.microsoft.com/library/windows/desktop/ms690234) Windows SDK.  
  
##  <a name="isdirty"></a>  IPersistStreamInitImpl::IsDirty  
 Son kaydedilişinden nesnenin veri değişip değişmediğini denetler.  
  
```
STDMETHOD(IsDirty)();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPersistStreamInit::IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms680092) Windows SDK.  
  
##  <a name="load"></a>  IPersistStreamInitImpl::Load  
 Nesnenin özelliklerini belirtilen akıştan yükler.  
  
```
STDMETHOD(Load)(LPSTREAM pStm);
```  
  
### <a name="remarks"></a>Açıklamalar  
 ATL nesnenin özellik eşlemesi bu bilgileri almak için kullanır.  
  
 Bkz: [IPersistStreamInit::Load](http://msdn.microsoft.com/library/windows/desktop/ms680730) Windows SDK.  
  
##  <a name="save"></a>  IPersistStreamInitImpl::Save  
 Nesnenin özelliklerini belirtilen akışa kaydeder.  
  
```
STDMETHOD(Save)(LPSTREAM pStm, BOOL fClearDirty);
```  
  
### <a name="remarks"></a>Açıklamalar  
 ATL nesnenin özellik eşlemesi bu bilgileri depolamak için kullanır.  
  
 Bkz: [IPersistStreamInit::Save](http://msdn.microsoft.com/library/windows/desktop/ms694439) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Depolar ve akışlar](http://msdn.microsoft.com/library/windows/desktop/aa380352)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
