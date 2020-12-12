---
description: 'Daha fazla bilgi edinin: genel sık kullanılan anahtarlar'
title: Genel Sık Kullanılan Tuşlar
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- CHotKeyCtrl class [MFC], global hot keys
- access keys [MFC], hot keys
- global hot keys [MFC]
ms.assetid: e0b95d14-c571-4c9a-9cd1-e7fc1f0e278d
ms.openlocfilehash: 3d481c637ec20ed7b9ec3f45a916bd39470ffb5e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189281"
---
# <a name="global-hot-keys"></a>Genel Sık Kullanılan Tuşlar

Genel bir kısayol tuşu, belirli bir alt öğe olmayan pencere ile ilişkilendirilir. Kullanıcının pencereyi sistemin herhangi bir bölümünden etkinleştirmesine izin verir. Bir uygulama belirli bir pencere için bir genel kısayol tuşu belirler [wm_sethotkey](/windows/win32/inputdev/wm-sethotkey) iletisini bu pencereye gönderir. Örneğin, `m_HotKeyCtrl` [CHotKeyCtrl](reference/chotkeyctrl-class.md) nesnesi ise ve `pMainWnd` kısayol tuşuna basıldığında etkinleştirilecek pencere için bir işaretçisiyse, denetimde belirtilen kısayol tuşunu tarafından işaret edilen pencereyle ilişkilendirmek için aşağıdaki kodu kullanabilirsiniz `pMainWnd` .

[!code-cpp[NVC_MFCControlLadenDialog#18](codesnippet/cpp/global-hot-keys_1.cpp)]

Kullanıcı genel bir kısayol tuşuna bastığında, belirtilen pencere komutun türü olarak **SC_HOTKEY** belirten [WM_SYSCOMMAND](/windows/win32/menurc/wm-syscommand) bir ileti alır. Bu ileti ayrıca onu alan pencereyi etkinleştirir. Bu ileti, basılan kesin anahtar hakkında herhangi bir bilgi içermediğinden, bu yöntemin kullanılması aynı pencereye iliştirilebilecek farklı kısayol tuşları arasında ayrım yapmanıza izin vermez. Etkin anahtar, **wm_sethotkey** gönderen uygulamaya çıkılana kadar geçerli kalır.

## <a name="see-also"></a>Ayrıca bkz.

[CHotKeyCtrl Kullanma](using-chotkeyctrl.md)<br/>
[Denetimler](controls-mfc.md)
