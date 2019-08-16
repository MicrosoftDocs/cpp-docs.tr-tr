---
title: Genel Sık Kullanılan Tuşlar
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- CHotKeyCtrl class [MFC], global hot keys
- access keys [MFC], hot keys
- global hot keys [MFC]
ms.assetid: e0b95d14-c571-4c9a-9cd1-e7fc1f0e278d
ms.openlocfilehash: 59918648ea24fd1e2a86ca786de3081cd6cca2df
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69508563"
---
# <a name="global-hot-keys"></a>Genel Sık Kullanılan Tuşlar

Genel bir kısayol tuşu, belirli bir alt öğe olmayan pencere ile ilişkilendirilir. Kullanıcının pencereyi sistemin herhangi bir bölümünden etkinleştirmesine izin verir. Bir uygulama belirli bir pencere için genel bir kısayol tuşu ayarlar ve bu pencereye [wm_sethotkey](/windows/win32/inputdev/wm-sethotkey) iletisi gönderir. Örneğin, `m_HotKeyCtrl` [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) nesnesi ise ve `pMainWnd` kısayol tuşuna basıldığında etkinleştirilecek pencere için bir işaretçisiyse, denetimde belirtilen kısayol tuşunu tarafından işaret edilen pencereyle ilişkilendirmek için aşağıdaki kodu kullanabilirsiniz `pMainWnd`.

[!code-cpp[NVC_MFCControlLadenDialog#18](../mfc/codesnippet/cpp/global-hot-keys_1.cpp)]

Kullanıcı genel bir kısayol tuşuna bastığında, belirtilen pencere, komutun türü olarak **SC_HOTKEY** belirten bir [WM_SYSCOMMAND](/windows/win32/menurc/wm-syscommand) iletisi alır. Bu ileti ayrıca onu alan pencereyi etkinleştirir. Bu ileti, basılan kesin anahtar hakkında herhangi bir bilgi içermediğinden, bu yöntemin kullanılması aynı pencereye iliştirilebilecek farklı kısayol tuşları arasında ayrım yapmanıza izin vermez. Etkin anahtar, **wm_sethotkey** gönderen uygulamaya çıkılana kadar geçerli kalır.

## <a name="see-also"></a>Ayrıca bkz.

[CHotKeyCtrl Kullanma](../mfc/using-chotkeyctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
