---
title: Sık Kullanılan Tuş Ayarlama
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- access keys [MFC], hot keys
- CHotKeyCtrl class [MFC], setting hot key
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
ms.openlocfilehash: a5dc885767137a4e53d1ea0d066944d5f276c38c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508803"
---
# <a name="setting-a-hot-key"></a>Sık Kullanılan Tuş Ayarlama

Uygulamanız bir kısayol tuşu tarafından sağlanan bilgileri kullanabilir ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) iki yoldan biriyle denetimi:

- Göndererek nonchild penceresi etkinleştirdiğiniz için genel sık kullanılan tuş ayarlama bir [WM_SETHOTKEY](/windows/desktop/inputdev/wm-sethotkey) etkinleştirilmesi için ileti penceresine.

- Windows işlevini çağırarak iş parçacığına özgü sık kullanılan tuş ayarlamak [RegisterHotKey](https://msdn.microsoft.com/library/windows/desktop/ms646309).

## <a name="see-also"></a>Ayrıca Bkz.

[CHotKeyCtrl Kullanma](../mfc/using-chotkeyctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

