---
title: "IPersistPropertyBagImpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl::GetClassID
- ATLCOM/ATL::IPersistPropertyBagImpl::InitNew
- ATLCOM/ATL::IPersistPropertyBagImpl::Load
- ATLCOM/ATL::IPersistPropertyBagImpl::Save
dev_langs: C++
helpviewer_keywords: IPersistPropertyBagImpl class
ms.assetid: 712af24d-99f8-40f2-9811-53b3ff6e5b19
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1854f4c078bb6c8ce6a987961dc75444e104278c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ipersistpropertybagimpl-class"></a>IPersistPropertyBagImpl sınıfı
Bu sınıf uygulayan **IUnknown** ve bir istemci tarafından sağlanan özellik paketi özelliklerini kaydetmek bir nesne sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>  
class ATL_NO_VTABLE IPersistPropertyBagImpl : public IPersistPropertyBag
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `IPersistPropertyBagImpl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IPersistPropertyBagImpl::GetClassID](#getclassid)|Nesnenin CLSID alır.|  
|[IPersistPropertyBagImpl::InitNew](#initnew)|Yeni oluşturulan nesnesini başlatır. ATL uygulamasını döndürür `S_OK`.|  
|[IPersistPropertyBagImpl::Load](#load)|Nesnenin özelliklerini bir istemci tarafından sağlanan özellik paketi yükler.|  
|[IPersistPropertyBagImpl::Save](#save)|Nesnenin özelliklerini bir istemci tarafından sağlanan özellik paketi kaydeder.|  
  
## <a name="remarks"></a>Açıklamalar  
 [IPersistPropertyBag](https://msdn.microsoft.com/library/aa768205.aspx) arabirimi özelliklerini bir istemci tarafından sağlanan özellik paketi kaydetmek için bir nesneyi sağlar. Sınıf `IPersistPropertyBagImpl` bu arabirimin varsayılan uygulamasını sağlar ve uygulayan **IUnknown** aygıt hata ayıklama dökümü bilgileri göndererek oluşturur.  
  
 **IPersistPropertyBag** birlikte çalışır [IPropertyBag](https://msdn.microsoft.com/library/aa768196.aspx) ve [IErrorLog](https://msdn.microsoft.com/library/aa768231.aspx). Bu ikinci iki arabirim istemci tarafından uygulanmalıdır. Aracılığıyla `IPropertyBag`, istemci kaydeder ve nesnenin özellikler yükler. Aracılığıyla **IErrorLog**, hem nesnenin hem de istemci karşılaşılan hataları bildirebilirsiniz.  
  
 **İlgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [bir ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IPersistPropertyBag`  
  
 `IPersistPropertyBagImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="getclassid"></a>IPersistPropertyBagImpl::GetClassID  
 Nesnenin CLSID alır.  
  
```
STDMETHOD(GetClassID)(CLSID* pClassID);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPersist::GetClassID](http://msdn.microsoft.com/library/windows/desktop/ms688664) Windows SDK.  
  
##  <a name="initnew"></a>IPersistPropertyBagImpl::InitNew  
 Yeni oluşturulan nesnesini başlatır.  
  
```
STDMETHOD(InitNew)();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPersistPropertyBag::InitNew](https://msdn.microsoft.com/library/aa768204.aspx) Windows SDK.  
  
##  <a name="load"></a>IPersistPropertyBagImpl::Load  
 Nesnenin özelliklerini bir istemci tarafından sağlanan özellik paketi yükler.  
  
```
STDMETHOD(Load)(LPPROPERTYBAG pPropBag, LPERRORLOG pErrorLog);
```  
  
### <a name="remarks"></a>Açıklamalar  
 ATL nesnenin özellik eşlemesi bu bilgileri almak için kullanır.  
  
 Bkz: [IPersistPropertyBag::Load](https://msdn.microsoft.com/library/aa768206.aspx) Windows SDK.  
  
##  <a name="save"></a>IPersistPropertyBagImpl::Save  
 Nesnenin özelliklerini bir istemci tarafından sağlanan özellik paketi kaydeder.  
  
```
STDMETHOD(Save)(
    LPPROPERTYBAG pPropBag,
    BOOL fClearDirty,
    BOOL fSaveAllProperties);
```  
  
### <a name="remarks"></a>Açıklamalar  
 ATL nesnenin özellik eşlemesi bu bilgileri depolamak için kullanır. Varsayılan olarak, bu yöntem değerini bakılmaksızın tüm özellikleri kaydeder *fSaveAllProperties*.  
  
 Bkz: [IPersistPropertyBag::Save](https://msdn.microsoft.com/library/aa768207.aspx) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [BEGIN_PROP_MAP](property-map-macros.md#begin_prop_map)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
