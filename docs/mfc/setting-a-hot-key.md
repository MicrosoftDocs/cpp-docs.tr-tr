---
title: Sık Kullanılan Tuş Ayarlama
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- access keys [MFC], hot keys
- CHotKeyCtrl class [MFC], setting hot key
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
ms.openlocfilehash: a77aad4881acd04c6dabb6dce90acc01be2cfbc8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307789"
---
# <a name="setting-a-hot-key"></a>Sık Kullanılan Tuş Ayarlama

Uygulamanız bir kısayol tuşu tarafından sağlanan bilgileri kullanabilir ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) iki yoldan biriyle denetimi:

- Göndererek nonchild penceresi etkinleştirdiğiniz için genel sık kullanılan tuş ayarlama bir [WM_SETHOTKEY](/windows/desktop/inputdev/wm-sethotkey) etkinleştirilmesi için ileti penceresine.

- Windows işlevini çağırarak iş parçacığına özgü sık kullanılan tuş ayarlamak [RegisterHotKey](/windows/desktop/api/winuser/nf-winuser-registerhotkey).

## <a name="see-also"></a>Ayrıca bkz.

[CHotKeyCtrl Kullanma](../mfc/using-chotkeyctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
