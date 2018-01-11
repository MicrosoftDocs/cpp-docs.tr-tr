---
title: "IObjectSafetyImpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl::GetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::SetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::m_dwCurrentSafety
dev_langs: C++
helpviewer_keywords:
- controls [ATL], safe
- safe for scripting and initialization (controls)
- IObjectSafety, ATL implementation
- IObjectSafetyImpl class
ms.assetid: 64e32082-d910-4a8a-a5bf-ebed9145359d
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aa7813b694cfea614bc80946d91c8f1bd977e627
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="iobjectsafetyimpl-class"></a>IObjectSafetyImpl sınıfı
Bu sınıf, bir varsayılan uygulamasını sağlar `IObjectSafety` almak ve bir nesnenin güvenlik düzeylerini ayarlamak bir istemci izin vermek için arabirim.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T,DWORD dwSupportedSafety>  
class IObjectSafetyImpl
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `IObjectSafetyImpl`.  
  
 *dwSupportedSafety*  
 Denetim için desteklenen güvenlik seçeneklerini belirtir. Aşağıdaki değerlerden biri olabilir:  
  
- **INTERFACESAFE_FOR_UNTRUSTED_CALLER** tarafından tanımlanan arabirimi [SetInterfaceSafetyOptions](#setinterfacesafetyoptions) parametresi `riid` komut dosyası için güvenli olarak yapılmalıdır.  
  
- **INTERFACESAFE_FOR_UNTRUSTED_DATA** tarafından tanımlanan arabirimi `SetInterfaceSafetyOptions` parametresi `riid` başlatma sırasında güvenilmeyen verileri güvenli olarak yapılmalıdır.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IObjectSafetyImpl::GetInterfaceSafetyOptions](#getinterfacesafetyoptions)|Şu anda nesne için ayarlanan güvenlik seçenekleri yanı sıra, nesne tarafından desteklenen güvenlik seçeneklerini alır.|  
|[IObjectSafetyImpl::SetInterfaceSafetyOptions](#setinterfacesafetyoptions)|Nesne başlatma veya komut dosyası için güvenli hale getirir.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IObjectSafetyImpl::m_dwCurrentSafety](#m_dwcurrentsafety)|Nesnenin geçerli güvenlik düzeyi depolar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıf `IObjectSafetyImpl` bir varsayılan uygulamayı sağlar `IObjectSafety`. `IObjectSafety` Arabirimi almak ve bir nesnenin güvenlik düzeylerini ayarlamak bir istemci izin verir. Örneğin, bir web tarayıcısı çağırabilirsiniz **IObjectSafety::SetInterfaceSafetyOptions** denetim başlatma için güvenli veya komut dosyası için güvenli hale getirmek için.  
  
 Bu kullanarak Not [IMPLEMENTED_CATEGORY](category-macros.md#implemented_category) makro **CATID_SafeForScripting** ve **CATID_SafeForInitializing** bileşen kategorileri alternatif sağlar bir bileşenin güvenli olduğunu belirten bir yolu.  
  
 **İlgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [bir ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IObjectSafety`  
  
 `IObjectSafetyImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlctl.h  
  
##  <a name="getinterfacesafetyoptions"></a>IObjectSafetyImpl::GetInterfaceSafetyOptions  
 Şu anda nesne için ayarlanan güvenlik seçenekleri yanı sıra, nesne tarafından desteklenen güvenlik seçeneklerini alır.  
  
```
HRESULT GetInterfaceSafetyOptions(  
    REFIID riid,
    DWORD* pdwSupportedOptions,
    DWORD* pdwEnabledOptions);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulama nesnesinin uygulama tarafından desteklenen herhangi bir arabirim için uygun değerleri döndürür **IUnknown::QueryInterface**.  
  
> [!IMPORTANT]
>  Destekleyen herhangi bir nesne `IObjectSafety` kendi güvenlik ve, onu temsilciler herhangi bir nesne için sorumludur. Programcı gerekir kullanıcının bağlamında bir kod çalıştırmasını doğan hesabı sorunlarını içine alın, siteler arası komut dosyası ve uygun alan denetimi gerçekleştirin.  
  
 Bkz: [IObjectSafety::GetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768223.aspx) Windows SDK.  
  
##  <a name="m_dwcurrentsafety"></a>IObjectSafetyImpl::m_dwCurrentSafety  
 Nesnenin geçerli güvenlik düzeyi depolar.  
  
```
DWORD m_dwCurrentSafety;
```  
  
##  <a name="setinterfacesafetyoptions"></a>IObjectSafetyImpl::SetInterfaceSafetyOptions  
 Nesne başlatma veya ayarlayarak komut dosyası için güvenli hale getirir [m_dwCurrentSafety](#m_dwcurrentsafety) uygun değere üye.  
  
```
HRESULT SetInterfaceSafetyOptions(  
    REFIID riid,
    DWORD dwOptionsSetMask,
    DWORD dwEnabledOptions);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulama döndürür **E_NOINTERFACE** nesnenin uygulaması tarafından desteklenmeyen herhangi bir arabirim için **IUnknown::QueryInterface**.  
  
> [!IMPORTANT]
>  Destekleyen herhangi bir nesne `IObjectSafety` kendi güvenlik ve, onu temsilciler herhangi bir nesne için sorumludur. Programcı gerekir kullanıcının bağlamında bir kod çalıştırmasını doğan hesabı sorunlarını içine alın, siteler arası komut dosyası ve uygun alan denetimi gerçekleştirin.  
  
 Bkz: [IObjectSafety::SetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768225.aspx) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IObjectSafety arabirimi](https://msdn.microsoft.com/library/aa768224.aspx)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
