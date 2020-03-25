---
title: IDBInitializeImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL.IDBInitializeImpl<T>
- ATL::IDBInitializeImpl<T>
- IDBInitializeImpl
- ATL::IDBInitializeImpl
- ATL.IDBInitializeImpl
- IDBInitializeImpl.IDBInitializeImpl
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
helpviewer_keywords:
- IDBInitializeImpl class
- IDBInitializeImpl constructor
- Initialize method
- Uninitialize method
- m_dwStatus
- m_pCUtlPropInfo
ms.assetid: e4182f81-0443-44f5-a0d3-e7e075d6f883
ms.openlocfilehash: ff74ae93f01c7e8588a0eff1f48d3f6f0e6d5e81
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210775"
---
# <a name="idbinitializeimpl-class"></a>IDBInitializeImpl Sınıfı

[IDBInitialize](/previous-versions/windows/desktop/ms713706(v=vs.85)) arabirimi için bir uygulama sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
class ATL_NO_VTABLE IDBInitializeImpl : public IDBInitialize
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Sınıfınız `IDBInitializeImpl`türetilir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[IDBInitializeImpl](#idbinitializeimpl)|Oluşturucu.|

### <a name="interface-methods"></a>Arabirim yöntemleri

|||
|-|-|
|[Initialize](#initialize)|Sağlayıcıyı başlatır.|
|[Uninitialize](#uninitialize)|Sağlayıcıyı sonlandırır.|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|[m_dwStatus](#dwstatus)|Veri kaynağı bayrakları.|
|[m_pCUtlPropInfo](#pcutlpropinfo)|DB özellikleri bilgilerini uygulamaya yönelik bir işaretçi.|

## <a name="remarks"></a>Açıklamalar

Veri kaynağı nesnelerinde zorunlu arabirim ve numaralandırıcılara yönelik isteğe bağlı arabirim.

## <a name="idbinitializeimplidbinitializeimpl"></a><a name="idbinitializeimpl"></a>IDBInitializeImpl:: IDBInitializeImpl

Oluşturucu.

### <a name="syntax"></a>Sözdizimi

```cpp
IDBInitializeImpl();
```

### <a name="remarks"></a>Açıklamalar

Tüm veri üyelerini başlatır.

## <a name="idbinitializeimplinitialize"></a><a name="initialize"></a>Idbinitializeımpl:: Initialize

Özellik desteğini hazırlarken veri kaynağı nesnesini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(Initialize)(void);
```

### <a name="remarks"></a>Açıklamalar

*OLE DB Programcı başvurusunda* [ıdbınitiınitialize:: Initialize](/previous-versions/windows/desktop/ms718026(v=vs.85)) öğesine bakın.

## <a name="idbinitializeimpluninitialize"></a><a name="uninitialize"></a>IDBInitializeImpl:: Uninitialize

Özellik desteği gibi iç kaynakları boşaltarak veri kaynağı nesnesini başlatılmamış bir duruma koyar.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(Uninitialize)(void);
```

### <a name="remarks"></a>Açıklamalar

*OLE DB Programcı başvurusunda* [ıdbınitiınitialize:: Uninitialize](/previous-versions/windows/desktop/ms719648(v=vs.85)) konusuna bakın.

## <a name="idbinitializeimplm_dwstatus"></a><a name="dwstatus"></a>IDBInitializeImpl:: m_dwStatus

Veri kaynağı bayrakları.

### <a name="syntax"></a>Sözdizimi

```cpp
DWORD m_dwStatus;
```

### <a name="remarks"></a>Açıklamalar

Bu bayraklar veri kaynağı nesnesi için çeşitli özniteliklerin durumunu belirtir veya belirtir. Aşağıdaki **enum** değerlerinden bir veya daha fazlasını içerir:

```cpp
enum DATASOURCE_FLAGS {
    DSF_MASK_INIT     = 0xFFFFF00F,
    DSF_PERSIST_DIRTY = 0x00000001,
    DSF_INITIALIZED   = 0x00000010,
};
```

|||
|-|-|
|`DSF_MASK_INIT`|Başlatılmamış durumun geri yüklenmesini sağlayan bir maske.|
|`DSF_PERSIST_DIRTY`|Veri kaynağı nesnesi kalıcılığı gerektiriyorsa (yani değişiklikler varsa) ayarlayın.|
|`DSF_INITIALIZED`|Veri kaynağı başlatılmışsa ayarlanır.|

## <a name="idbinitializeimplm_pcutlpropinfo"></a><a name="pcutlpropinfo"></a>IDBInitializeImpl:: m_pCUtlPropInfo

DB özellikleri bilgileri için uygulama nesnesi işaretçisi.

### <a name="syntax"></a>Sözdizimi

```cpp
CUtlPropInfo< T >* m_pCUtlPropInfo;
```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
