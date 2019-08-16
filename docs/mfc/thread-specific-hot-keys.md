---
title: İş Parçacığına Özgü Sık Kullanılan Tuşlar
ms.date: 11/04/2016
helpviewer_keywords:
- CHotKeyCtrl class [MFC], thread-specific hot keys
- keyboard shortcuts [MFC], hot keys
- threading [MFC], hot keys in CHotKeyCtrl
- access keys [MFC], hot keys
ms.assetid: b6021274-1498-483f-bcbf-ba5723547cc8
ms.openlocfilehash: 49bac6ac357924c26f131bbd8e1092cd74514167
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511144"
---
# <a name="thread-specific-hot-keys"></a>İş Parçacığına Özgü Sık Kullanılan Tuşlar

Uygulama, Windows `RegisterHotKey` işlevini kullanarak iş parçacığına özgü bir etkin anahtar ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) ayarlar. Kullanıcı, iş parçacığına özgü bir kısayol tuşuna bastığında Windows, belirli bir iş parçacığının ileti sırasının başlangıcına bir [wm_hotkey](/windows/win32/inputdev/wm-hotkey) iletisi gönderir. WM_HOTKEY iletisi, basılan belirli bir anahtar için sanal anahtar kodu, kaydırma durumu ve Kullanıcı tanımlı KIMLIĞI içerir. Standart sanal anahtar kodlarının listesi için bkz. Winuser. h. Bu yöntem hakkında daha fazla bilgi için bkz. [Registerkısayol](/windows/win32/api/winuser/nf-winuser-registerhotkey).

Çağrısında `RegisterHotKey` kullanılan SHIFT durum bayraklarının [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) üye işlevi tarafından döndürülen olanlarla aynı olmadığına unutmayın; çağrılmadan `RegisterHotKey`önce Bu bayrakları çevirmeniz gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[CHotKeyCtrl Kullanma](../mfc/using-chotkeyctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
