---
title: İş Parçacığına Özgü Sık Kullanılan Tuşlar
ms.date: 11/04/2016
helpviewer_keywords:
- CHotKeyCtrl class [MFC], thread-specific hot keys
- keyboard shortcuts [MFC], hot keys
- threading [MFC], hot keys in CHotKeyCtrl
- access keys [MFC], hot keys
ms.assetid: b6021274-1498-483f-bcbf-ba5723547cc8
ms.openlocfilehash: 68c50ec5f29dab271f9af9abc50eb72ec15157e7
ms.sourcegitcommit: c85c8a1226d8fbbaa29f4691ed719f8e6cc6575c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/24/2019
ms.locfileid: "54893333"
---
# <a name="thread-specific-hot-keys"></a>İş Parçacığına Özgü Sık Kullanılan Tuşlar

Bir uygulama bir iş parçacığına özgü sık kullanılan tuş ayarlar ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) kullanarak Windows `RegisterHotKey` işlevi. Kullanıcı bir iş parçacığına özgü kısayol tuşuna bastığında Windows yazılarını bir [WM_HOTKEY](/windows/desktop/inputdev/wm-hotkey) başlangıcına bir belirli iş parçacığının ileti kuyruğu iletisi. Sanal anahtar kodu, kaydırma durumu ve kullanıcı tanımlı Kimliğini basıldığını belirli bir kısayol tuşu WM_HOTKEY ileti içerir. Winuser.h standart sanal anahtar kodlarının listesi için bkz. Bu yöntem hakkında daha fazla bilgi için bkz. [RegisterHotKey](/windows/desktop/api/winuser/nf-winuser-registerhotkey).

Kaydırma durumu bayrakları çağrısında kullanılan Not `RegisterHotKey` olanlar tarafından döndürülen aynı değildir [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) ; üye işlevini çağırmadan önce bu bayraklar çevirmek zorunda kalırsınız `RegisterHotKey`.

## <a name="see-also"></a>Ayrıca Bkz.

[CHotKeyCtrl Kullanma](../mfc/using-chotkeyctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

