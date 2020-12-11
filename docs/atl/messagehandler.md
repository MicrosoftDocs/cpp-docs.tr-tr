---
description: ': MessageHandler hakkında daha fazla bilgi'
title: MessageHandler
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- MessageHandler function
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
ms.openlocfilehash: d369b94721e57eb4adc704570bc09d1aae184fe1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159511"
---
# <a name="messagehandler"></a>MessageHandler

`MessageHandler` , ileti Haritalarınızın MESSAGE_HANDLER makrosunun ikinci parametresi tarafından tanımlanan işlevin adıdır.

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
Çağrılan ileti *eşleme kümeleri* ÇAĞRıLMADAN önce true olarak ayarlanır `MessageHandler` . `MessageHandler`İletiyi tam olarak işlemezse, iletinin daha fazla işleme ihtiyacı olduğunu göstermek Için *BIŞLENMIŞ* olarak false olarak ayarlanmalıdır.

## <a name="return-value"></a>Dönüş Değeri

İleti işlemenin sonucu. başarılı olursa 0.

## <a name="remarks"></a>Açıklamalar

Bu ileti işleyicisini bir ileti eşlemesinde kullanmanın bir örneği için bkz. [message_handler](reference/message-map-macros-atl.md#message_handler).

## <a name="see-also"></a>Ayrıca bkz.

[Pencere uygulama](../atl/implementing-a-window.md)<br/>
[İleti haritaları](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/win32/controls/wm-notify)
