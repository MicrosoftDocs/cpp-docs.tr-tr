---
title: CommandHandler
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- CommandHandler function
ms.assetid: 662bc7bf-4a10-42b3-986d-d8bae4f63551
ms.openlocfilehash: 99a95228f6036e5f391395be367cdef39ca3dc3b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492464"
---
# <a name="commandhandler"></a>CommandHandler

`CommandHandler`, ileti Haritalarınızın COMMAND_HANDLER makrosunun üçüncü parametresi tarafından tanımlanan işlevdir.

## <a name="syntax"></a>Sözdizimi

```cpp
LRESULT CommandHandler(
    WORD wNotifyCode,
    WORD wID,
    HWND hWndCtl,
    BOOL& bHandled);
```

#### <a name="parameters"></a>Parametreler

*wNotifyCode*<br/>
Bildirim kodu.

*wID*<br/>
Menü öğesinin, denetimin veya hızlandırıcının tanımlayıcısı.

*hWndCtl*<br/>
Pencere denetimine yönelik bir tanıtıcı.

*Bişlenmiş*<br/>
Çağrılan ileti eşleme kümeleri çağrılmadan önce `CommandHandler` true olarak ayarlanır. İletiyi tam olarak işlemezse, iletinin daha fazla işleme ihtiyacı olduğunu göstermek için bişlenmiş olarak false olarak ayarlanmalıdır. `CommandHandler`

## <a name="return-value"></a>Dönüş Değeri

İleti işlemenin sonucu. başarılı olursa 0.

## <a name="remarks"></a>Açıklamalar

Bu ileti işleyicisini bir ileti eşlemesinde kullanmanın bir örneği için bkz. [COMMAND_HANDLER](reference/message-map-macros-atl.md#command_handler).

## <a name="see-also"></a>Ayrıca bkz.

[Pencere Uygulama](../atl/implementing-a-window.md)<br/>
[İleti haritaları](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/win32/controls/wm-notify)
