---
title: Genel Sık Kullanılan Tuşlar
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- CHotKeyCtrl class [MFC], global hot keys
- access keys [MFC], hot keys
- global hot keys [MFC]
ms.assetid: e0b95d14-c571-4c9a-9cd1-e7fc1f0e278d
ms.openlocfilehash: 4cafee311f71d8165380b3fb7e192e7032b7941c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529941"
---
# <a name="global-hot-keys"></a>Genel Sık Kullanılan Tuşlar

Genel sık kullanılan tuş belirli nonchild penceresiyle ilişkilidir. Bu sistemin herhangi bir bölümünden penceresini etkinleştir izin verir. Bir uygulama belirli bir pencere için genel bir kısayol tuşu göndererek ayarlar [WM_SETHOTKEY](/windows/desktop/inputdev/wm-sethotkey) bu penceresine ileti. Örneğin, varsa `m_HotKeyCtrl` olan [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) nesne ve `pMainWnd` gösteren bir işaretçidir penceresine kısayol tuşuna basıldığında etkinleştirilmesi için sık kullanılan tuş denetimi ile belirtilen ilişkilendirmek için aşağıdaki kodu kullanabilirsiniz pencere tarafından işaret edilen `pMainWnd`.

[!code-cpp[NVC_MFCControlLadenDialog#18](../mfc/codesnippet/cpp/global-hot-keys_1.cpp)]

Genel sık kullanılan tuş kullanıcı olduğunda, belirtilen pencere alır bir [WM_SYSCOMMAND](/windows/desktop/menurc/wm-syscommand) belirten bir ileti **SC_HOTKEY** komut türü. Bu iletiyi aldıktan sonra penceresi de etkinleştirir. Bu ileti basıldığını tam anahtar herhangi bir bilgi içermediği için bu yöntemi kullanarak aynı pencere için eklenen farklı bir kısayol tuşları arasında ayrım izin vermez. Kısayol tuşu gönderilen uygulama kadar geçerli kalır **WM_SETHOTKEY** çıkar.

## <a name="see-also"></a>Ayrıca Bkz.

[CHotKeyCtrl Kullanma](../mfc/using-chotkeyctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

