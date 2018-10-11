---
title: Idbınitializeımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IDBInitializeImpl<T>
- ATL::IDBInitializeImpl<T>
- IDBInitializeImpl
- ATL::IDBInitializeImpl
- ATL.IDBInitializeImpl
- IDBInitializeImpl.IDBInitializeImpl
- IDBInitializeImpl
- IDBInitializeImpl::IDBInitializeImpl
- Initialize
- IDBInitializeImpl::Initialize
- IDBInitializeImpl.Initialize
- IDBInitializeImpl.Uninitialize
- Uninitialize
- IDBInitializeImpl::Uninitialize
- ATL::IDBInitializeImpl::m_dwStatus
- IDBInitializeImpl.m_dwStatus
- ATL.IDBInitializeImpl.m_dwStatus
- IDBInitializeImpl::m_dwStatus
- IDBInitializeImpl<T>::m_dwStatus
- ATL.IDBInitializeImpl<T>.m_dwStatus
- ATL::IDBInitializeImpl<T>::m_dwStatus
- m_dwStatus
- ATL::IDBInitializeImpl<T>::m_pCUtlPropInfo
- m_pCUtlPropInfo
- IDBInitializeImpl::m_pCUtlPropInfo
- ATL.IDBInitializeImpl.m_pCUtlPropInfo
- IDBInitializeImpl<T>::m_pCUtlPropInfo
- IDBInitializeImpl.m_pCUtlPropInfo
- ATL::IDBInitializeImpl::m_pCUtlPropInfo
dev_langs:
- C++
helpviewer_keywords:
- IDBInitializeImpl class
- IDBInitializeImpl constructor
- Initialize method
- Uninitialize method
- m_dwStatus
- m_pCUtlPropInfo
ms.assetid: e4182f81-0443-44f5-a0d3-e7e075d6f883
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b799b0383316c212ff2d2cd12ccac9b2b14dce0b
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/11/2018
ms.locfileid: "49082598"
---
# <a name="idbinitializeimpl-class"></a>IDBInitializeImpl Sınıfı

Bir uygulamasını sağlar [IDBInitialize](/previous-versions/windows/desktop/ms713706) arabirimi.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>  
class ATL_NO_VTABLE IDBInitializeImpl : public IDBInitialize  
```  
  
### <a name="parameters"></a>Parametreler  

*T*<br/>
Sınıfınız, türetilen `IDBInitializeImpl`.  

## <a name="requirements"></a>Gereksinimler  

**Başlık:** atldb.h  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[Idbınitializeımpl](#idbinitializeimpl)|Oluşturucu.|  
  
### <a name="interface-methods"></a>Arabirim yöntemleri  
  
|||  
|-|-|  
|[Initialize](#initialize)|Sağlayıcıyı başlatır.|  
|[Geri alınıyor](#uninitialize)|Sağlayıcı durdurur.|  
  
### <a name="data-members"></a>Veri üyeleri  
  
|||  
|-|-|  
|[m_dwStatus](#dwstatus)|Veri kaynağı bayraklar.|  
|[m_pCUtlPropInfo](#pcutlpropinfo)|DB özellikleri bilgileri, uygulama için bir işaretçi.|  
  
## <a name="remarks"></a>Açıklamalar  

Veri kaynağı nesneleri ve isteğe bağlı bir arabirim numaralandırıcılar üzerinde zorunlu bir arabirim.  

## <a name="idbinitializeimpl"></a> Idbınitializeımpl::ıdbınitializeımpl

Oluşturucu.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
IDBInitializeImpl();  
```  
  
### <a name="remarks"></a>Açıklamalar  

Tüm veri üyeleri başlatır. 
  
## <a name="initialize"></a> Idbınitializeımpl::Initialize

Veri kaynağı nesnesinin özellik desteğini hazırlayarak başlatır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
STDMETHOD(Initialize)(void);  
```  
  
### <a name="remarks"></a>Açıklamalar  

Bkz: [IDBInitialize::Initialize](/previous-versions/windows/desktop/ms718026) içinde *OLE DB Programcının Başvurusu*. 

## <a name="uninitialize"></a> Idbınitializeımpl::Uninitialize

Basamak veri özelliği desteği gibi iç kaynaklara azaltarak başlatılmamış durumda nesne kaynağı.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
STDMETHOD(Uninitialize)(void);  
```  
  
### <a name="remarks"></a>Açıklamalar  

Bkz: [IDBInitialize::Uninitialize](/previous-versions/windows/desktop/ms719648) içinde *OLE DB Programcının Başvurusu*.

## <a name="dwstatus"></a> Idbınitializeımpl::m_dwstatus

Veri kaynağı bayraklar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
DWORD m_dwStatus;  
```  
  
### <a name="remarks"></a>Açıklamalar  

Bu bayraklar belirtin veya veri kaynağı nesnesi için çeşitli öznitelikler durumunu gösterir. Bir veya daha fazlasını içeren **enum** değerleri:  
  
```cpp  
enum DATASOURCE_FLAGS {  
    DSF_MASK_INIT     = 0xFFFFF00F,  
    DSF_PERSIST_DIRTY = 0x00000001,  
    DSF_INITIALIZED   = 0x00000010,  
};  
```  
  
|||  
|-|-|  
|`DSF_MASK_INIT`|Başlatılmamış duruma geri etkinleştirmek için bir maske.|  
|`DSF_PERSIST_DIRTY`|Veri kaynağı nesnesi Kalıcılık gerektiriyorsa (diğer bir deyişle, olduğunda değişiklikler) ayarlayın.|  
|`DSF_INITIALIZED`|Veri kaynağı başlatılmışsa ayarlayın.|  

## <a name="pcutlpropinfo"></a> Idbınitializeımpl::m_pcutlpropınfo

DB özellikleri bilgileri uygulama nesnesi için bir işaretçi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
CUtlPropInfo< T >* m_pCUtlPropInfo;  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)