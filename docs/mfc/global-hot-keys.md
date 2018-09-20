---
title: Genel kısayol tuşları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- CHotKeyCtrl class [MFC], global hot keys
- access keys [MFC], hot keys
- global hot keys [MFC]
ms.assetid: e0b95d14-c571-4c9a-9cd1-e7fc1f0e278d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d749fad0fabf8ae99bba129caee399e3f93ff9af
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443858"
---
# <a name="global-hot-keys"></a>Genel Sık Kullanılan Tuşlar

Genel sık kullanılan tuş belirli nonchild penceresiyle ilişkilidir. Bu sistemin herhangi bir bölümünden penceresini etkinleştir izin verir. Bir uygulama belirli bir pencere için genel bir kısayol tuşu göndererek ayarlar [WM_SETHOTKEY](/windows/desktop/inputdev/wm-sethotkey) bu penceresine ileti. Örneğin, varsa `m_HotKeyCtrl` olan [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) nesne ve `pMainWnd` gösteren bir işaretçidir penceresine kısayol tuşuna basıldığında etkinleştirilmesi için sık kullanılan tuş denetimi ile belirtilen ilişkilendirmek için aşağıdaki kodu kullanabilirsiniz pencere tarafından işaret edilen `pMainWnd`.

[!code-cpp[NVC_MFCControlLadenDialog#18](../mfc/codesnippet/cpp/global-hot-keys_1.cpp)]

Genel sık kullanılan tuş kullanıcı olduğunda, belirtilen pencere alır bir [WM_SYSCOMMAND](/windows/desktop/menurc/wm-syscommand) belirten bir ileti **SC_HOTKEY** komut türü. Bu iletiyi aldıktan sonra penceresi de etkinleştirir. Bu ileti basıldığını tam anahtar herhangi bir bilgi içermediği için bu yöntemi kullanarak aynı pencere için eklenen farklı bir kısayol tuşları arasında ayrım izin vermez. Kısayol tuşu gönderilen uygulama kadar geçerli kalır **WM_SETHOTKEY** çıkar.

## <a name="see-also"></a>Ayrıca Bkz.

[CHotKeyCtrl Kullanma](../mfc/using-chotkeyctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

