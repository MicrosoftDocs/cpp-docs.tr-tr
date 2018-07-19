---
title: Iregistrar arabirimi | Microsoft Docs
ms.custom: ''
ms.date: 2/1/2017
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IRegistrar
- ATLIFASE/ATL::IRegistrar
- ATLIFASE/ATL::IRegistrar::ResourceRegisterSz
- ATLIFASE/ATL::IRegistrar::ResourceUnregisterSz
- ATLIFASE/ATL::IRegistrar::FileRegister
- ATLIFASE/ATL::IRegistrar::FileUnregister
- ATLIFASE/ATL::IRegistrar::StringRegister
- ATLIFASE/ATL::IRegistrar::StringUnregister
- ATLIFASE/ATL::IRegistrar::ResourceRegister
- ATLIFASE/ATL::IRegistrar::ResourceUnregister
dev_langs:
- C++
helpviewer_keywords:
- Iregistrar Interface
ms.assetid: e88c04b7-0c93-4ae8-aeb9-ecd78f87421e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b6720ef830563e24d887071e1ee1e4a8c31df05c
ms.sourcegitcommit: bb4488366e4581c561ca1e573a2b99b71d4c6288
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2018
ms.locfileid: "38993574"
---
# <a name="iregistrar-interface"></a>Iregistrar arabirimi
Bu arabirim atliface.h içinde tanımlanır ve CAtlModule üye işlevleri tarafından dahili olarak gibi kullanılan [UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced).   
  
## <a name="syntax"></a>Sözdizimi  
  
```
typedef interface IRegistrar IRegistrar;
```  
## <a name="remarks"></a>Açıklamalar
Konusuna [değiştirilebilir parametreler kullanma (kaydedicinin ön işlemcisi)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) daha fazla ayrıntı için.  

## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IRegistrar::ResourceRegisterSz](#resourceregistersz)|Kaynak kaydeder. |  
|[IRegistrar::ResourceUnregisterSz](#resourceunregistersz)| Kaynak kaydını siler.|  
|[IRegistrar::FileRegister](#fileregister)|Dosyayı kaydeder.|  
|[IRegistrar::FileUnregister](#fileunregister)|Dosya kaydını siler.|  
|[IRegistrar::StringRegister](#stringregister)|Dize kaydeder.|  
|[IRegistrar::StringUnregister](#stringunregister)|Dize kaydını siler|  
|[IRegistrar::ResourceRegister](#resourceregister)|Kaynak kaydeder.|  
|[IRegistrar::ResourceUnregister](#resourceunregister)|Kaynak kaydını siler.| 
  

 
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlifase.h  
  
##  <a name="resourceregistersz"></a>  IRegistrar::ResourceRegisterSz 
 Kaynak kaydeder.  
  
```
virtual HRESULT STDMETHODCALLTYPE ResourceRegisterSz( 
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```  
  
 
  
##  <a name="resourceunregistersz"></a>  IRegistrar::ResourceUnregisterSz  
 Kaynak kaydını siler.
  
```
virtual HRESULT STDMETHODCALLTYPE ResourceUnregisterSz( 
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```  
  
  
##  <a name="fileregister"></a>  IRegistrar::FileRegister  
Dosyayı kaydeder.
  
```
virtual HRESULT STDMETHODCALLTYPE FileRegister( 
    /* [in] */ _In_z_ LPCOLESTR fileName) = 0;
```  
  
  
##  <a name="fileunregister"></a>  IRegistrar::FileUnregister  
Dosya kaydını siler.

```
virtual HRESULT STDMETHODCALLTYPE FileUnregister( 
    */ _In_z_ LPCOLESTR fileName) = 0;
```  
  
 
##  <a name="stringregister"></a>  IRegistrar::StringRegister  
  Belirtilen dize verilerini kaydeder.
```
virtual HRESULT STDMETHODCALLTYPE StringRegister( 
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```  
  
##  <a name="stringunregister"></a>  IRegistrar::StringUnregister
 Belirtilen dize verileri kaydını siler.  
  
```
virtualHRESULT STDMETHODCALLTYPE StringUnregister( 
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```  

  
##  <a name="resourceregister"></a>  IRegistrar::ResourceRegister  
 Kaynak kaydeder.  
  
```
virtual HRESULT STDMETHODCALLTYPE ResourceRegister( 
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```  
   
  
##  <a name="resourceunregister"></a>  IRegistrar::ResourceUnregister  
 Kaynak kaydını siler.  
  
```
virtualHRESULT STDMETHODCALLTYPE ResourceUnregister( 
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0; 
```  
 
## <a name="see-also"></a>Ayrıca Bkz.  
 [Değiştirilebilir Parametreler Kullanma (Kaydedicinin Ön İşlemcisi)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)  
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)   
 [Modül sınıfları](../../atl/atl-module-classes.md)   
 [Kayıt defteri bileşeni (Kaydedici)](../../atl/atl-registry-component-registrar.md)  
