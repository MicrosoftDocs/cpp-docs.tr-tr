---
title: MessageHandler
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- MessageHandler function
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
ms.openlocfilehash: aa044ef88ba3c872c2652cd774ac50024e52c68c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492319"
---
# <a name="messagehandler"></a>MessageHandler

`MessageHandler`, ileti Haritalarınızın MESSAGE_HANDLER makrosunun ikinci parametresi tarafından tanımlanan işlevin adıdır.

## <a name="syntax"></a>Sözdizimi

```
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
Çağrılan ileti eşleme kümeleri çağrılmadan önce `MessageHandler` true olarak ayarlanır. İletiyi tam olarak işlemezse, iletinin daha fazla işleme ihtiyacı olduğunu göstermek için bişlenmiş olarak false olarak ayarlanmalıdır. `MessageHandler`

## <a name="return-value"></a>Dönüş Değeri

İleti işlemenin sonucu. başarılı olursa 0.

## <a name="remarks"></a>Açıklamalar

Bu ileti işleyicisini bir ileti eşlemesinde kullanmanın bir örneği için bkz. [message_handler](reference/message-map-macros-atl.md#message_handler).

## <a name="see-also"></a>Ayrıca bkz.

[Pencere Uygulama](../atl/implementing-a-window.md)<br/>
[İleti haritaları](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/win32/controls/wm-notify)
