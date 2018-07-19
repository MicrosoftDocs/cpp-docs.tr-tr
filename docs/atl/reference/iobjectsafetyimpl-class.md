---
title: Iobjectsafetyımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl::GetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::SetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::m_dwCurrentSafety
dev_langs:
- C++
helpviewer_keywords:
- controls [ATL], safe
- safe for scripting and initialization (controls)
- IObjectSafety, ATL implementation
- IObjectSafetyImpl class
ms.assetid: 64e32082-d910-4a8a-a5bf-ebed9145359d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3f474c73a63c7eaeb7452e88812180a24d1321df
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37881194"
---
# <a name="iobjectsafetyimpl-class"></a>Iobjectsafetyımpl sınıfı
Bu sınıfın bir varsayılan uygulamayı sağlar `IObjectSafety` almak ve bir nesnenin güvenlik düzeylerini ayarlamak bir istemci izin vermek için arabirim.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T,DWORD dwSupportedSafety>  
class IObjectSafetyImpl
```  
  
#### <a name="parameters"></a>Parametreler  
 *T*  
 Sınıfınız, türetilen `IObjectSafetyImpl`.  
  
 *dwSupportedSafety*  
 Denetim için desteklenen güvenlik seçeneklerini belirtir. Aşağıdaki değerlerden biri olabilir:  
  
- INTERFACESAFE_FOR_UNTRUSTED_CALLER tarafından tanımlanan arabirimi [SetInterfaceSafetyOptions](#setinterfacesafetyoptions) parametre `riid` komut dosyası için güvenli olarak yapılmalıdır.  
  
- INTERFACESAFE_FOR_UNTRUSTED_DATA tarafından tanımlanan arabirimi `SetInterfaceSafetyOptions` parametre `riid` başlatma sırasında için güvenilir olmayan verileri güvenli olarak yapılmalıdır.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IObjectSafetyImpl::GetInterfaceSafetyOptions](#getinterfacesafetyoptions)|Nesne için ayarlanmış güvenlik seçenekleri yanı sıra, nesne tarafından desteklenen güvenlik seçeneklerini alır.|  
|[IObjectSafetyImpl::SetInterfaceSafetyOptions](#setinterfacesafetyoptions)|Nesne başlatma veya komut dosyası için güvenli hale getirir.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IObjectSafetyImpl::m_dwCurrentSafety](#m_dwcurrentsafety)|Nesnenin geçerli güvenlik düzeyi depolar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıf `IObjectSafetyImpl` bir varsayılan uygulamayı sağlar `IObjectSafety`. `IObjectSafety` Almak ve bir nesnenin güvenlik düzeylerini ayarlamak bir istemci arabirimi sağlar. Örneğin, bir web tarayıcısı çağırabilirsiniz `IObjectSafety::SetInterfaceSafetyOptions` başlatma için güvenli veya komut dosyası için güvenli bir denetim yapmak için.  
  
 Bu Not [IMPLEMENTED_CATEGORY](category-macros.md#implemented_category) makrosu CATID_SafeForScripting ve CATID_SafeForInitializing bileşen kategorileri ile bir bileşeni güvenli olduğunu belirtmek için alternatif bir yol sağlar.  
  
 **İle ilgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IObjectSafety`  
  
 `IObjectSafetyImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlctl.h  
  
##  <a name="getinterfacesafetyoptions"></a>  IObjectSafetyImpl::GetInterfaceSafetyOptions  
 Nesne için ayarlanmış güvenlik seçenekleri yanı sıra, nesne tarafından desteklenen güvenlik seçeneklerini alır.  
  
```
HRESULT GetInterfaceSafetyOptions(  
    REFIID riid,
    DWORD* pdwSupportedOptions,
    DWORD* pdwEnabledOptions);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Uygulama nesnesinin uygulama tarafından desteklenen herhangi bir arabirimde için uygun değerleri döndürür `IUnknown::QueryInterface`.  
  
> [!IMPORTANT]
>  Destekleyen herhangi bir nesne `IObjectSafety` kendi güvenlik ve, herhangi bir nesnenin, temsilciler için sorumludur. Programcı gerekir kullanıcının bağlamında bir kod çalıştırmasını doğan hesabı sorunlarla alın, siteler arası betik oluşturma ve uygun alan denetimi gerçekleştirin.  
  
 Bkz: [IObjectSafety::GetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768223.aspx) Windows SDK içinde.  
  
##  <a name="m_dwcurrentsafety"></a>  IObjectSafetyImpl::m_dwCurrentSafety  
 Nesnenin geçerli güvenlik düzeyi depolar.  
  
```
DWORD m_dwCurrentSafety;
```  
  
##  <a name="setinterfacesafetyoptions"></a>  IObjectSafetyImpl::SetInterfaceSafetyOptions  
 Nesne başlatma veya ayarlayarak komut dosyası için güvenli hale getirir [m_dwCurrentSafety](#m_dwcurrentsafety) uygun değere üyesi.  
  
```
HRESULT SetInterfaceSafetyOptions(  
    REFIID riid,
    DWORD dwOptionsSetMask,
    DWORD dwEnabledOptions);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Nesnenin uygulaması tarafından desteklenmeyen herhangi bir arabirim için e_noınterface uygulamasını döndürür `IUnknown::QueryInterface`.  
  
> [!IMPORTANT]
>  Destekleyen herhangi bir nesne `IObjectSafety` kendi güvenlik ve, herhangi bir nesnenin, temsilciler için sorumludur. Programcı gerekir kullanıcının bağlamında bir kod çalıştırmasını doğan hesabı sorunlarla alın, siteler arası betik oluşturma ve uygun alan denetimi gerçekleştirin.  
  
 Bkz: [IObjectSafety::SetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768225.aspx) Windows SDK içinde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IObjectSafety arabirimi](https://msdn.microsoft.com/library/aa768224.aspx)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
