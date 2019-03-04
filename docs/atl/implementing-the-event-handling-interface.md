---
title: Olay işleme arabirimini uygulama
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, event handling
- event handling, ATL
- interfaces, event and event sink
ms.assetid: eb2a5b33-88dc-4ce3-bee0-c5c38ea050d7
ms.openlocfilehash: d977b59907266a2e0141defa8c496b1e7bc66a6c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57273419"
---
# <a name="implementing-the-event-handling-interface"></a>Olay işleme arabirimini uygulama

ATL yardımcı olur, olayları işlemek için gerekli tüm üç öğelerle: olay arabirimi uygulayan, olay kaynağı bildiren ve olay kaynağı unadvising. Gerçekleştirilecek ihtiyacınız olacak doğru adımlar olay arabirimini ve uygulamanızın performans gereksinimlerini türüne bağlıdır.

ATL kullanarak arabirimi uygulama ile ilgili en yaygın yöntemler şunlardır:

- Özel bir arabirimden doğrudan türetme.

- Öğesinden türetme [Idispatchımpl](../atl/reference/idispatchimpl-class.md) tür kitaplığında tanımlanan ikili arabirimler için.

- Öğesinden türetme [Idispeventımpl](../atl/reference/idispeventimpl-class.md) tanımlanan bir tür kitaplığındaki görüntü arabirimlerinde için.

- Öğesinden türetme [Idispeventsimpleımpl](../atl/reference/idispeventsimpleimpl-class.md) için bir tür kitaplığı veya çalışma zamanında tür bilgilerini yüklenmemesi verimliliğini artırmak istediğiniz zaman açıklanmayan görüntüleme.

Özel veya çift arabirim uyguluyorsanız çağırarak olay kaynağı öneri [AtlAdvise](reference/connection-point-global-functions.md#atladvise) veya [CComPtrBase::Advise](../atl/reference/ccomptrbase-class.md#advise). Kendiniz çağrı tarafından döndürülen tanımlama bilgisi izlemek gerekir. Çağrı [AtlUnadvise](reference/connection-point-global-functions.md#atlunadvise) bağlantıyı kesmek için.

Bir dispinterface kullanarak uyguluyorsanız `IDispEventImpl` veya `IDispEventSimpleImpl`, olay kaynağı çağırarak öneri [IDispEventSimpleImpl::DispEventAdvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventadvise). Çağrı [IDispEventSimpleImpl::DispEventUnadvise](../atl/reference/idispeventsimpleimpl-class.md#dispeventunadvise) bağlantıyı kesmek için.

Kullanıyorsanız `IDispEventImpl` bileşik denetim temel sınıf olarak listelenen havuz haritada olay kaynakları tavsiye edilir ve unadvised kullanılarak otomatik olarak olacaktır [CComCompositeControl::AdviseSinkMap](../atl/reference/ccomcompositecontrol-class.md#advisesinkmap).

`IDispEventImpl` Ve `IDispEventSimpleImpl` sınıfları, tanımlama bilgisi yönetin.

## <a name="see-also"></a>Ayrıca bkz.

[Olay İşleme](../atl/event-handling-and-atl.md)
