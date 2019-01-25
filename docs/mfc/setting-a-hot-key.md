---
title: Sık Kullanılan Tuş Ayarlama
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- access keys [MFC], hot keys
- CHotKeyCtrl class [MFC], setting hot key
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
ms.openlocfilehash: ebaddb4a64a4d9d47b82fd36f118c74527554e53
ms.sourcegitcommit: c85c8a1226d8fbbaa29f4691ed719f8e6cc6575c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/24/2019
ms.locfileid: "54893230"
---
# <a name="setting-a-hot-key"></a>Sık Kullanılan Tuş Ayarlama

Uygulamanız bir kısayol tuşu tarafından sağlanan bilgileri kullanabilir ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) iki yoldan biriyle denetimi:

- Göndererek nonchild penceresi etkinleştirdiğiniz için genel sık kullanılan tuş ayarlama bir [WM_SETHOTKEY](/windows/desktop/inputdev/wm-sethotkey) etkinleştirilmesi için ileti penceresine.

- Windows işlevini çağırarak iş parçacığına özgü sık kullanılan tuş ayarlamak [RegisterHotKey](/windows/desktop/api/winuser/nf-winuser-registerhotkey).

## <a name="see-also"></a>Ayrıca Bkz.

[CHotKeyCtrl Kullanma](../mfc/using-chotkeyctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

