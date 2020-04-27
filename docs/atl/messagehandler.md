---
title: MessageHandler
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- MessageHandler function
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
ms.openlocfilehash: 65a8ce08e4f8606f168b101aa4daba23ef541051
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168676"
---
# <a name="messagehandler"></a>MessageHandler

`MessageHandler`, ileti Haritalarınızın MESSAGE_HANDLER makrosunun ikinci parametresi tarafından tanımlanan işlevin adıdır.

## <a name="syntax"></a>Sözdizimi

```cpp
LRESULT MessageHandler(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    BOOL& bHandled);
```

### <a name="parameters"></a>Parametreler

*uMsg*<br/>
İletiyi belirtir.

*wParam*<br/>
İletiye özgü ek bilgiler.

*lParam*<br/>
İletiye özgü ek bilgiler.

*Bişlenmiş*<br/>
Çağrılan ileti *eşleme kümeleri çağrılmadan* önce `MessageHandler` true olarak ayarlanır. `MessageHandler` İletiyi tam olarak işlemezse, iletinin daha fazla işleme ihtiyacı olduğunu göstermek Için *BIŞLENMIŞ* olarak false olarak ayarlanmalıdır.

## <a name="return-value"></a>Dönüş Değeri

İleti işlemenin sonucu. başarılı olursa 0.

## <a name="remarks"></a>Açıklamalar

Bu ileti işleyicisini bir ileti eşlemesinde kullanmanın bir örneği için bkz. [message_handler](reference/message-map-macros-atl.md#message_handler).

## <a name="see-also"></a>Ayrıca bkz.

[Pencere uygulama](../atl/implementing-a-window.md)<br/>
[İleti haritaları](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/win32/controls/wm-notify)
