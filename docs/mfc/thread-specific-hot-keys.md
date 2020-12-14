---
description: 'Daha fazla bilgi edinin: Thread-Specific kısayol tuşları'
title: İş Parçacığına Özgü Sık Kullanılan Tuşlar
ms.date: 11/04/2016
helpviewer_keywords:
- CHotKeyCtrl class [MFC], thread-specific hot keys
- keyboard shortcuts [MFC], hot keys
- threading [MFC], hot keys in CHotKeyCtrl
- access keys [MFC], hot keys
ms.assetid: b6021274-1498-483f-bcbf-ba5723547cc8
ms.openlocfilehash: 352d39b801d7e6dcecfbf27d841d6977d3666138
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216125"
---
# <a name="thread-specific-hot-keys"></a>İş Parçacığına Özgü Sık Kullanılan Tuşlar

Uygulama, Windows işlevini kullanarak iş parçacığına özgü bir etkin anahtar ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) ayarlar `RegisterHotKey` . Kullanıcı, iş parçacığına özgü bir kısayol tuşuna bastığında Windows, belirli bir iş parçacığının ileti sırasının başlangıcına bir [wm_hotkey](/windows/win32/inputdev/wm-hotkey) iletisi gönderir. WM_HOTKEY ileti, basılan belirli bir anahtar için sanal anahtar kodu, kaydırma durumu ve Kullanıcı tanımlı KIMLIĞI içerir. Standart sanal anahtar kodlarının listesi için bkz. Winuser. h. Bu yöntem hakkında daha fazla bilgi için bkz. [Registerkısayol](/windows/win32/api/winuser/nf-winuser-registerhotkey).

Çağrısında kullanılan SHIFT durum bayraklarının `RegisterHotKey` [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) üye işlevi tarafından döndürülen olanlarla aynı olmadığına unutmayın; çağrılmadan önce Bu bayrakları çevirmeniz gerekir `RegisterHotKey` .

## <a name="see-also"></a>Ayrıca bkz.

[CHotKeyCtrl Kullanma](../mfc/using-chotkeyctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
