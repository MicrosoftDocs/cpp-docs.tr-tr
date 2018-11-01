---
title: İş Parçacığına Özgü Sık Kullanılan Tuşlar
ms.date: 11/04/2016
helpviewer_keywords:
- CHotKeyCtrl class [MFC], thread-specific hot keys
- keyboard shortcuts [MFC], hot keys
- threading [MFC], hot keys in CHotKeyCtrl
- access keys [MFC], hot keys
ms.assetid: b6021274-1498-483f-bcbf-ba5723547cc8
ms.openlocfilehash: 4b393fe1af060a4b235162ce8cdfd94a1a391085
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594161"
---
# <a name="thread-specific-hot-keys"></a>İş Parçacığına Özgü Sık Kullanılan Tuşlar

Bir uygulama bir iş parçacığına özgü sık kullanılan tuş ayarlar ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) kullanarak Windows `RegisterHotKey` işlevi. Kullanıcı bir iş parçacığına özgü kısayol tuşuna bastığında Windows yazılarını bir [WM_HOTKEY](/windows/desktop/inputdev/wm-hotkey) başlangıcına bir belirli iş parçacığının ileti kuyruğu iletisi. Sanal anahtar kodu, kaydırma durumu ve kullanıcı tanımlı Kimliğini basıldığını belirli bir kısayol tuşu WM_HOTKEY ileti içerir. Winuser.h standart sanal anahtar kodlarının listesi için bkz. Bu yöntem hakkında daha fazla bilgi için bkz. [RegisterHotKey](https://msdn.microsoft.com/library/windows/desktop/ms646309).

Kaydırma durumu bayrakları çağrısında kullanılan Not `RegisterHotKey` olanlar tarafından döndürülen aynı değildir [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) ; üye işlevini çağırmadan önce bu bayraklar çevirmek zorunda kalırsınız `RegisterHotKey`.

## <a name="see-also"></a>Ayrıca Bkz.

[CHotKeyCtrl Kullanma](../mfc/using-chotkeyctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

