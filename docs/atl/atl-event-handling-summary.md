---
title: ATL olay özeti işleme | Microsoft Docs
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
ms.openlocfilehash: a938bd072ea8df30e64cce28fbf0709f08547d28
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356529"
---
# <a name="atl-event-handling-summary"></a>ATL olay işleme özeti
Genel olarak, COM olayları işleme bir oldukça basit bir işlemdir. Üç ana adım vardır:  
  
-   Olay arabirimini nesnenize uygulayın.  
  
-   Olay kaynağı nesnenizin olayları almak istediği öneriyoruz.  
  
-   Olay kaynağı nesnenizin olaylarını almak artık ihtiyaç duyduğunda unadvise.  
  
## <a name="implementing-the-interface"></a>Arabirimi uygulama  
 ATL kullanarak arabirimi uygulama dört ana yolu vardır  
  
|Öğesinden türetilen|Arabirim türü için uygun|Tüm yöntemleri * uygulamak gerektirir|Çalışma zamanında bir tür kitaplığı gerektirir|  
|-----------------|---------------------------------|---------------------------------------------|-----------------------------------------|  
|Arabirimi|Vtable|Evet|Hayır|  
|[IDispatchImpl](../atl/reference/idispatchimpl-class.md)|Çift|Evet|Evet|  
|[IDispEventImpl](../atl/reference/idispeventimpl-class.md)|Görüntüleme arabirimi|Hayır|Evet|  
|[IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|Görüntüleme arabirimi|Hayır|Hayır|  
  
 \* ATL desteği sınıfları kullanırken, hiçbir zaman uygulamanız için gerekli **IUnknown** veya `IDispatch` yöntemlerini el ile.  
  
## <a name="advising-and-unadvising-the-event-source"></a>Bildiren ve olay kaynağı Unadvising  
 Bildiren ve ATL kullanan bir olay kaynağına unadvising üç ana yolu  
  
|Öneri işlevi|Unadvise işlevi|İle kullanmak için en uygun|Bir tanımlama bilgisi izlemek gerektirir|Açıklamalar|  
|---------------------|-----------------------|--------------------------------|---------------------------------------------|--------------|  

|[AtlAdvise](reference/connection-point-global-functions.md#atladvise), [CComPtrBase::Advise](../atl/reference/ccomptrbase-class.md#advise)|[AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise)| Vtable ya da çift arabirimler | Evet | `AtlAdvise` genel bir ATL işlevdir. `CComPtrBase::Advise` tarafından kullanılan [CComPtr](../atl/reference/ccomptr-class.md) ve [CComQIPtr](../atl/reference/ccomqiptr-class.md). |  

|[IDispEventSimpleImpl::DispEventAdvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise)|[IDispEventSimpleImpl::DispEventUnadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise)|[IDispEventImpl](../atl/reference/idispeventimpl-class.md) veya [ IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)| Hayır | Sayısından daha az sayıda parametre `AtlAdvise` temel sınıfı daha fazla iş olmadığından bu yana. |  
|[CComCompositeControl::AdviseSinkMap(TRUE)](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)|[CComCompositeControl::AdviseSinkMap(FALSE)](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)| Bileşik denetimler ActiveX denetimlerinde | Hayır | `CComCompositeControl::AdviseSinkMap` tüm girişleri olay eşlemesi havuzu önerir. Aynı işlevi girişleri unadvises. Bu yöntem tarafından otomatik olarak çağrılır `CComCompositeControl` sınıfı. |  
|[CAxDialogImpl::AdviseSinkMap(TRUE)](../atl/reference/caxdialogimpl-class.md#advisesinkmap)|[CAxDialogImpl::AdviseSinkMap(FALSE)](../atl/reference/caxdialogimpl-class.md#advisesinkmap)| Bir iletişim kutusu ActiveX denetimlerinde | Hayır | `CAxDialogImpl::AdviseSinkMap` öneren ve iletişim kutusu kaynağı tüm ActiveX denetimlerinde unadvises. Bu otomatik olarak sizin için yapılır. |  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Olay işleme](../atl/event-handling-and-atl.md)   
 [IDispEventImpl Destekleme](../atl/supporting-idispeventimpl.md)

