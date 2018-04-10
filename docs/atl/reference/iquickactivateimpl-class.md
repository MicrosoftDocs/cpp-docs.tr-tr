---
title: IQuickActivateImpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl::GetContentExtent
- ATLCTL/ATL::IQuickActivateImpl::QuickActivate
- ATLCTL/ATL::IQuickActivateImpl::SetContentExtent
dev_langs:
- C++
helpviewer_keywords:
- activating ATL controls
- controls [ATL], activating
- IQuickActivateImpl class
- IQuickActivate ATL implementation
ms.assetid: aa80c056-1041-494e-b21d-2acca7dc27ea
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7c6f5bc1798bc8ec40fb6f6d9d22f48c06b19745
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="iquickactivateimpl-class"></a>IQuickActivateImpl sınıfı
Bu sınıf kapsayıcıları denetim başlatma tek bir çağrı halinde birleştirir.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>  
class ATL_NO_VTABLE IQuickActivateImpl : public IQuickActivate
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `IQuickActivateImpl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IQuickActivateImpl::GetContentExtent](#getcontentextent)|Çalışan bir denetim için geçerli görüntü boyutunu alır.|  
|[IQuickActivateImpl::QuickActivate](#quickactivate)|Hızlı Başlatma yüklenen denetimleri gerçekleştirir.|  
|[IQuickActivateImpl::SetContentExtent](#setcontentextent)|Kapsayıcı atanmış ne kadar görüntü alanını denetim bildirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 [IQuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms690146) arabirimi denetimlerini tek bir çağrı başlatma birleştirerek yüklerken gecikmelerden kaçınmak kapsayıcıları yardımcı olur. `QuickActivate` Yöntemi için bir işaretçi geçirmek kapsayıcı sağlar bir [QACONTAINER](http://msdn.microsoft.com/library/windows/desktop/ms688630) işaretçileri denetimi için tüm arabirimler tutan yapısı gerekiyor. Getirisi, denetim için bir işaretçi geri geçirir bir [QACONTROL](http://msdn.microsoft.com/library/windows/desktop/ms693721) kapsayıcı tarafından kullanılan kendi arabirimlerine işaretçileri tutan yapısı. Sınıf `IQuickActivateImpl` bir varsayılan uygulamayı sağlar **IQuickActivate** ve uygulayan **IUnknown** aygıt hata ayıklama dökümü bilgileri göndererek oluşturur.  
  
 **İlgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [bir ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IQuickActivate`  
  
 `IQuickActivateImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlctl.h  
  
##  <a name="getcontentextent"></a>IQuickActivateImpl::GetContentExtent  
 Çalışan bir denetim için geçerli görüntü boyutunu alır.  
  
```
STDMETHOD(GetContentExtent)(LPSIZEL pSize);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Boyutu tam bir denetim işleme için ve HIMETRIC birimlerle belirtilir.  
  
 Bkz: [IQuickActivate::GetContentExtent](http://msdn.microsoft.com/library/windows/desktop/ms693792) Windows SDK.  
  
##  <a name="quickactivate"></a>IQuickActivateImpl::QuickActivate  
 Hızlı Başlatma yüklenen denetimleri gerçekleştirir.  
  
```
STDMETHOD(QuickActivate)(
    QACONTAINER* pQACont,
    QACONTROL* pQACtrl);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yapı denetimi ve bazı ortam özelliklerine değerler gerek duyduğu arabirimleri işaretçiler içerir. Return denetimi için bir işaretçi geçirir bir [QACONTROL](http://msdn.microsoft.com/library/windows/desktop/ms693721) kapsayıcı gerektirir kendi arabirimleri ve ek durum bilgileri işaretçileri içeren yapısı.  
  
 Bkz: [IQuickActivate::QuickActivate](http://msdn.microsoft.com/library/windows/desktop/ms682421) Windows SDK.  
  
##  <a name="setcontentextent"></a>IQuickActivateImpl::SetContentExtent  
 Kapsayıcı atanmış ne kadar görüntü alanını denetim bildirir.  
  
```
STDMETHOD(SetContentExtent)(LPSIZEL pSize);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Boyutu HIMETRIC birimler cinsinden belirtilir.  
  
 Bkz: [IQuickActivate::SetContentExtent](http://msdn.microsoft.com/library/windows/desktop/ms678806) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComControl sınıfı](../../atl/reference/ccomcontrol-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
