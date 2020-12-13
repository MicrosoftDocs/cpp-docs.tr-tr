---
description: ': CommandHandler hakkında daha fazla bilgi'
title: CommandHandler
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- CommandHandler function
ms.assetid: 662bc7bf-4a10-42b3-986d-d8bae4f63551
ms.openlocfilehash: 746048dd83088cac8316cf6e0140644956c21b4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153292"
---
# <a name="commandhandler"></a>CommandHandler

`CommandHandler` , ileti Haritalarınızın COMMAND_HANDLER makrosunun üçüncü parametresi tarafından tanımlanan işlevdir.

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

*WID*<br/>
Menü öğesinin, denetimin veya hızlandırıcının tanımlayıcısı.

*hWndCtl*<br/>
Pencere denetimine yönelik bir tanıtıcı.

*Bişlenmiş*<br/>
Çağrılan ileti *eşleme kümeleri* ÇAĞRıLMADAN önce true olarak ayarlanır `CommandHandler` . `CommandHandler`İletiyi tam olarak işlemezse, iletinin daha fazla işleme ihtiyacı olduğunu göstermek Için *BIŞLENMIŞ* olarak false olarak ayarlanmalıdır.

## <a name="return-value"></a>Dönüş Değeri

İleti işlemenin sonucu. başarılı olursa 0.

## <a name="remarks"></a>Açıklamalar

Bu ileti işleyicisini bir ileti eşlemesinde kullanmanın bir örneği için bkz. [COMMAND_HANDLER](reference/message-map-macros-atl.md#command_handler).

## <a name="see-also"></a>Ayrıca bkz.

[Pencere uygulama](../atl/implementing-a-window.md)<br/>
[İleti haritaları](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/win32/controls/wm-notify)
