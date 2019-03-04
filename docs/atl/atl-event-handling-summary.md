---
title: ATL olay işleme özeti
ms.date: 11/04/2016
helpviewer_keywords:
- event handling, implementing
ms.assetid: e8b47ef0-0bdc-47ff-9dd6-34df11dde9a2
ms.openlocfilehash: 0e3a47719e3160170ed1bfa64b315415ddc7a1c8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265359"
---
# <a name="atl-event-handling-summary"></a>ATL olay işleme özeti

Genel olarak, COM olayları işleme göreceli olarak basit bir işlemdir. Üç ana adım vardır:

- Nesneniz üzerinde olay arabirimini uygulayın.

- Olay kaynağı, nesnenizin olayları almak istediğini önerin.

- Olay kaynağı, nesnenizin artık olayları almaya gerektiğinde eşlemesindeki.

## <a name="implementing-the-interface"></a>Arabirimi uygulama

ATL kullanarak arabirimi uygulama dört ana yolu vardır.

|Öğesinden türetilen|Arabirim türü için uygun|Tüm yöntemleri * uygulamak gerektirir|Çalışma zamanında bir tür kitaplığı gerektirir|
|-----------------|---------------------------------|---------------------------------------------|-----------------------------------------|
|Arabirimi|Vtable|Evet|Hayır|
|[Idispatchımpl](../atl/reference/idispatchimpl-class.md)|Çift|Evet|Evet|
|[IDispEventImpl](../atl/reference/idispeventimpl-class.md)|Dispinterface|Hayır|Evet|
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

## <a name="see-also"></a>Ayrıca bkz.

[Olay İşleme](../atl/event-handling-and-atl.md)<br/>
[IDispEventImpl Destekleme](../atl/supporting-idispeventimpl.md)
