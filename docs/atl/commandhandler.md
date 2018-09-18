---
title: CommandHandler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CommandHandler
dev_langs:
- C++
helpviewer_keywords:
- CommandHandler function
ms.assetid: 662bc7bf-4a10-42b3-986d-d8bae4f63551
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f5a4d4c359fb4a90bfd25801f7c73f5bc4d7d501
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019477"
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
[WM_NOTIFY](https://msdn.microsoft.com/library/windows/desktop/bb775583)

