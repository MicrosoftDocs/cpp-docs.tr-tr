---
title: ATL olay işleme özeti | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- event handling, implementing
ms.assetid: e8b47ef0-0bdc-47ff-9dd6-34df11dde9a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 743939683d212de529816a165907e12063df03be
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027199"
---
# <a name="atl-event-handling-summary"></a>ATL olay işleme özeti
Genel olarak, COM olayları işleme göreceli olarak basit bir işlemdir. Üç ana adım vardır:  
  
-   Nesneniz üzerinde olay arabirimini uygulayın.  
  
-   Olay kaynağı, nesnenizin olayları almak istediğini önerin.  
  
-   Olay kaynağı, nesnenizin artık olayları almaya gerektiğinde eşlemesindeki.  
  
## <a name="implementing-the-interface"></a>Arabirimi uygulama  
 ATL kullanarak arabirimi uygulama dört ana yolu vardır.  
  
|Öğesinden türetilen|Arabirim türü için uygun|Tüm yöntemleri * uygulamak gerektirir|Çalışma zamanında bir tür kitaplığı gerektirir|  
|-----------------|---------------------------------|---------------------------------------------|-----------------------------------------|  
|Arabirimi|Vtable|Evet|Hayır|  
|[Idispatchımpl](../atl/reference/idispatchimpl-class.md)|Çift|Evet|Evet|  
|[Idispeventımpl](../atl/reference/idispeventimpl-class.md)|Dispinterface|Hayır|Evet|  
|[IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|Dispinterface|Hayır|Hayır|  
  
 \* ATL desteği sınıfları kullanırken, hiçbir zaman uygulamak için gerekli `IUnknown` veya `IDispatch` yöntemleri el ile.  
  
## <a name="advising-and-unadvising-the-event-source"></a>Bildiren ve olay kaynağı Unadvising  
 Bildiren ve ATL kullanarak bir olay kaynağı unadvising başlıca üç yolu vardır.  
  
|Öneri işlevi|Eşlemesindeki işlevi|İle kullanmak için en uygun|Bir tanımlama bilgisi izlemek gerektirir|Açıklamalar|  
|---------------------|-----------------------|--------------------------------|---------------------------------------------|--------------|
|[AtlAdvise](reference/connection-point-global-functions.md#atladvise), [CComPtrBase::Advise](../atl/reference/ccomptrbase-class.md#advise)|[AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise)|Vtable veya ikili arabirimler|Evet|`AtlAdvise` Genel bir ATL işlevdir. `CComPtrBase::Advise` tarafından kullanılan [CComPtr](../atl/reference/ccomptr-class.md) ve [CComQIPtr](../atl/reference/ccomqiptr-class.md).|  
|[IDispEventSimpleImpl::DispEventAdvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise)|[IDispEventSimpleImpl::DispEventUnadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise)|[Idispeventımpl](../atl/reference/idispeventimpl-class.md) veya [Idispeventsimpleımpl](../atl/reference/idispeventsimpleimpl-class.md)|Hayır|Daha az parametre `AtlAdvise` olduğundan daha fazla işi temel sınıf yapar.|  
|[CComCompositeControl::AdviseSinkMap(TRUE)](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)|[CComCompositeControl::AdviseSinkMap(FALSE)](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)|Bileşik denetimler ActiveX denetimlerinde|Hayır|`CComCompositeControl::AdviseSinkMap` tüm girişleri olay eşlemesi havuz önerir. Aynı işlevin girişleri unadvises. Bu yöntem tarafından otomatik olarak çağrılır `CComCompositeControl` sınıfı.|  
|[CAxDialogImpl::AdviseSinkMap(TRUE)](../atl/reference/caxdialogimpl-class.md#advisesinkmap)|[CAxDialogImpl::AdviseSinkMap(FALSE)](../atl/reference/caxdialogimpl-class.md#advisesinkmap)|Bir iletişim kutusuna ActiveX denetimleri|Hayır|`CAxDialogImpl::AdviseSinkMap` öneren ve iletişim kutusu kaynağı tüm ActiveX denetimlerinde unadvises. Bu otomatik olarak sizin yerinize gerçekleştirilir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Olay işleme](../atl/event-handling-and-atl.md)   
 [IDispEventImpl Destekleme](../atl/supporting-idispeventimpl.md)

