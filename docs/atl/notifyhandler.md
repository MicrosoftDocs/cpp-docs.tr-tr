---
title: NotifyHandler
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- NotifyHandler
helpviewer_keywords:
- NotifyHandler function
ms.assetid: 5ff953ec-de35-42bc-8b3c-d384d636c139
ms.openlocfilehash: 9c669d856db895be7a9d0dafd0fda21879e7ff2e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644658"
---
# <a name="notifyhandler"></a>NotifyHandler

İleti haritanızı NOTIFY_HANDLER makroda'öğesinin üçüncü parametresi tarafından belirtilen işlevin adı.

## <a name="syntax"></a>Sözdizimi

```cpp
LRESULT NotifyHandler(
    int idCtrl,
    LPNMHDR pnmh,
    BOOL& bHandled);
```

#### <a name="parameters"></a>Parametreler

*idCtrl*<br/>
İletiyi gönderen denetim tanımlayıcısı.

*pnmh*<br/>
Adresi bir [NMHDR](/windows/desktop/api/richedit/ns-richedit-_nmhdr) bildirimi kodunu ve ek bilgiler içeren yapısı. Bazı bildirim iletileri için bu parametreyi olan daha büyük bir yapısına işaret `NMHDR` yapısı olarak kendi ilk üyesi.

*bHandled*<br/>
İleti eşleme kümeleri *bHandled* önce true *NotifyHandler* çağrılır. Varsa *NotifyHandler* tam iletiyi işlemez ayarlamanız gerekir *bHandled* için **FALSE** ihtiyaç daha fazla işleme belirtmek için.

## <a name="return-value"></a>Dönüş Değeri

İleti işleme sonucu. başarılıysa 0.

## <a name="remarks"></a>Açıklamalar

Bu ileti işleyicisi bir ileti eşlemede kullanma örneği için bkz: [NOTIFY_HANDLER](reference/message-map-macros-atl.md#notify_handler)).

## <a name="see-also"></a>Ayrıca Bkz.

[Pencere Uygulama](../atl/implementing-a-window.md)<br/>
[İleti eşlemeleri](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](https://msdn.microsoft.com/library/windows/desktop/bb775583)
