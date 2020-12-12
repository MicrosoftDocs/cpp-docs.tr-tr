---
description: 'Daha fazla bilgi edinin: ATL olay Işleme Özeti'
title: ATL olay Işleme Özeti
ms.date: 11/04/2016
helpviewer_keywords:
- event handling, implementing
ms.assetid: e8b47ef0-0bdc-47ff-9dd6-34df11dde9a2
ms.openlocfilehash: c041de6cbd0e0852d5ce0e51d892c21c7d9a23d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148661"
---
# <a name="atl-event-handling-summary"></a>ATL olay Işleme Özeti

Genel olarak, COM olaylarını işlemek görece basit bir işlemdir. Üç ana adım vardır:

- Nesneniz üzerinde olay arabirimini uygulayın.

- Olay kaynağını, nesnenizin olayları almak istediğini tavsiye edin.

- Nesnenizin artık olayları alması gerekmiyorsa olay kaynağını geri alın.

## <a name="implementing-the-interface"></a>Arabirimi uygulama

ATL kullanarak arabirim uygulama kullanmanın dört ana yolu vardır.

|Türet|Arabirim türü için uygun|Tüm yöntemleri uygulamanız gerekir *|Çalışma zamanında bir tür kitaplığı gerektirir|
|-----------------|---------------------------------|---------------------------------------------|-----------------------------------------|
|Arabirim|Vtable|Evet|Hayır|
|[IDispatchImpl](../atl/reference/idispatchimpl-class.md)|İkili|Evet|Evet|
|[IDispEventImpl](../atl/reference/idispeventimpl-class.md)|Dispinterface|Hayır|Evet|
|[IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|Dispinterface|Hayır|Hayır|

\* ATL destek sınıfları kullanılırken, `IUnknown` veya `IDispatch` yöntemlerini el ile uygulamanız gerekmez.

## <a name="advising-and-unadvising-the-event-source"></a>Olay kaynağını danışmanlama ve geri Temizleme

ATL kullanarak bir olay kaynağını sağlamanın ve geri almanın üç ana yolu vardır.

|Advise işlevi|Unadvise işlevi|İle kullanım için en uygun|Bir tanımlama bilgisinin izlenmesini gerektirir|Yorumlar|
|---------------------|-----------------------|--------------------------------|---------------------------------------------|--------------|
|[AtlAdvise](reference/connection-point-global-functions.md#atladvise), [CComPtrBase:: Advise](../atl/reference/ccomptrbase-class.md#advise)|[AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise)|Vtable veya çift arabirimler|Evet|`AtlAdvise` , genel bir ATL işlevidir. `CComPtrBase::Advise` , [CComPtr](../atl/reference/ccomptr-class.md) ve [CComQIPtr](../atl/reference/ccomqiptr-class.md)tarafından kullanılır.|
|[IDispEventSimpleImpl::D ıspeventadmenlik](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise)|[IDispEventSimpleImpl::D ispEventUnadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise)|[IDispEventImpl](../atl/reference/idispeventimpl-class.md) veya [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|Hayır|`AtlAdvise`Temel sınıfın daha fazla iş yaptığından daha az parametre.|
|[CComCompositeControl:: Advisesınkmap (TRUE)](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)|[CComCompositeControl:: Advisesınkmap (FALSE)](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap)|Bileşik denetimlerde ActiveX denetimleri|Hayır|`CComCompositeControl::AdviseSinkMap` olay havuzu haritadaki tüm girdileri önerir. Aynı işlev, girişlerin bir öneren olduğunu kaldırır. Bu yöntem, sınıfı tarafından otomatik olarak çağrılır `CComCompositeControl` .|
|[CAxDialogImpl:: Advisesınkmap (TRUE)](../atl/reference/caxdialogimpl-class.md#advisesinkmap)|[CAxDialogImpl:: Advisesınkmap (FALSE)](../atl/reference/caxdialogimpl-class.md#advisesinkmap)|İletişim kutusunda ActiveX denetimleri|Hayır|`CAxDialogImpl::AdviseSinkMap` iletişim kaynağındaki tüm ActiveX denetimlerini önerir ve bu denetimlerin karşılangeri vermez. Bu sizin için otomatik olarak yapılır.|

## <a name="see-also"></a>Ayrıca bkz.

[Olay Işleme](../atl/event-handling-and-atl.md)<br/>
[IDispEventImpl desteği](../atl/supporting-idispeventimpl.md)
