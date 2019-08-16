---
title: NotifyHandler
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- NotifyHandler function
ms.assetid: 5ff953ec-de35-42bc-8b3c-d384d636c139
ms.openlocfilehash: 16fb330d2da83ddfd013e33a2d4b688b2711103b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492299"
---
# <a name="notifyhandler"></a>NotifyHandler

İleti Haritalarınızın NOTIFY_HANDLER makrosunun üçüncü parametresi tarafından tanımlanan işlevin adı.

## <a name="syntax"></a>Sözdizimi

```cpp
LRESULT NotifyHandler(
    int idCtrl,
    LPNMHDR pnmh,
    BOOL& bHandled);
```

#### <a name="parameters"></a>Parametreler

*ıdctrl*<br/>
İletiyi gönderen denetimin tanımlayıcısı.

*PNMH*<br/>
Bildirim kodu ve ek bilgiler içeren bir [nmhdr](/windows/win32/api/richedit/ns-richedit-nmhdr) yapısının adresi. Bazı bildirim iletileri için, bu parametre, ilk üyesi olarak `NMHDR` yapısına sahip daha büyük bir yapıya işaret eder.

*Bişlenmiş*<br/>
Çağrılan ileti haritası, *NotifyHandler* çağrılmadan önce true değerine ayarlanır. *NotifyHandler* iletiyi tam olarak işlemezse, iletinin daha fazla işleme ihtiyacı olduğunu göstermek Için *Bişlenmiş* olarak **false** olarak ayarlanmalıdır.

## <a name="return-value"></a>Dönüş Değeri

İleti işlemenin sonucu. başarılı olursa 0.

## <a name="remarks"></a>Açıklamalar

Bu ileti işleyicisini bir ileti eşlemesinde kullanmanın bir örneği için bkz. [NOTIFY_HANDLER](reference/message-map-macros-atl.md#notify_handler)).

## <a name="see-also"></a>Ayrıca bkz.

[Pencere Uygulama](../atl/implementing-a-window.md)<br/>
[İleti haritaları](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/win32/controls/wm-notify)
