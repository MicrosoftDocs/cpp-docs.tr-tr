---
title: MessageHandler
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- MessageHandler
helpviewer_keywords:
- MessageHandler function
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
ms.openlocfilehash: deb217e2f889d30ab5c4caa7d9812d5e612dcb62
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299354"
---
# <a name="messagehandler"></a>MessageHandler

`MessageHandler` ikinci parametresi, ileti eşlemesi MESSAGE_HANDLER makro ile tanımlanan işlev adıdır.

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

*bHandled*<br/>
İleti eşleme kümeleri *bHandled* önce true `MessageHandler` çağrılır. Varsa `MessageHandler` tam iletiyi işlemez ayarlamanız gerekir *bHandled* ihtiyaç daha fazla işleme belirtmek için false.

## <a name="return-value"></a>Dönüş Değeri

İleti işleme sonucu. başarılıysa 0.

## <a name="remarks"></a>Açıklamalar

Bu ileti işleyicisi bir ileti eşlemede kullanma örneği için bkz: [MESSAGE_HANDLER](reference/message-map-macros-atl.md#message_handler).

## <a name="see-also"></a>Ayrıca bkz.

[Pencere Uygulama](../atl/implementing-a-window.md)<br/>
[İleti eşlemeleri](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/desktop/controls/wm-notify)
