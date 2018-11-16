---
title: CommandHandler
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CommandHandler
helpviewer_keywords:
- CommandHandler function
ms.assetid: 662bc7bf-4a10-42b3-986d-d8bae4f63551
ms.openlocfilehash: 8259dfe8ead608876b3637d1dca9c3e808bb419d
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51694640"
---
# <a name="commandhandler"></a>CommandHandler

`CommandHandler` işlevi, ileti eşlemesi COMMAND_HANDLER makroda'öğesinin üçüncü parametresi tarafından tanımlanır.

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
Uyarı kodu.

*wID*<br/>
Menü öğesi, denetim ya da Hızlandırıcı tanımlayıcısı.

*hWndCtl*<br/>
Bir pencere denetimi için bir tanıtıcı.

*bHandled*<br/>
İleti eşleme kümeleri *bHandled* önce true `CommandHandler` çağrılır. Varsa `CommandHandler` tam iletiyi işlemez ayarlamanız gerekir *bHandled* ihtiyaç daha fazla işleme belirtmek için false.

## <a name="return-value"></a>Dönüş Değeri

İleti işleme sonucu. başarılıysa 0.

## <a name="remarks"></a>Açıklamalar

Bu ileti işleyicisi bir ileti eşlemede kullanma örneği için bkz: [COMMAND_HANDLER](reference/message-map-macros-atl.md#command_handler).

## <a name="see-also"></a>Ayrıca Bkz.

[Pencere Uygulama](../atl/implementing-a-window.md)<br/>
[İleti eşlemeleri](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/desktop/controls/wm-notify)

