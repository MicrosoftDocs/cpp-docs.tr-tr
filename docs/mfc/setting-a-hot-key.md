---
title: Sık Kullanılan Tuş Ayarlama
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- access keys [MFC], hot keys
- CHotKeyCtrl class [MFC], setting hot key
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
ms.openlocfilehash: 7b49f24039b130f74693e7567f5287476126f225
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511212"
---
# <a name="setting-a-hot-key"></a>Sık Kullanılan Tuş Ayarlama

Uygulamanız, etkin anahtar ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) denetimi tarafından belirtilen bilgileri iki şekilde kullanabilir:

- Etkinleştirmek üzere pencereye bir [wm_sethotkey](/windows/win32/inputdev/wm-sethotkey) iletisi göndererek alt öğe olmayan bir pencerenin etkinleştirilmesi için genel bir sık kullanılan anahtar ayarlayın.

- [Registerkısayol](/windows/win32/api/winuser/nf-winuser-registerhotkey)Windows işlevini çağırarak iş parçacığına özgü bir etkin anahtar ayarlayın.

## <a name="see-also"></a>Ayrıca bkz.

[CHotKeyCtrl Kullanma](../mfc/using-chotkeyctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
