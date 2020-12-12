---
description: 'Daha fazla bilgi: etkin anahtar ayarlama'
title: Sık Kullanılan Tuş Ayarlama
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts [MFC], hot keys
- access keys [MFC], hot keys
- CHotKeyCtrl class [MFC], setting hot key
ms.assetid: 6f3bc141-e346-4dce-9ca7-3e6b2c453f3f
ms.openlocfilehash: fa713be2d478eb18b11dca27558656e5e6993076
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217191"
---
# <a name="setting-a-hot-key"></a>Sık Kullanılan Tuş Ayarlama

Uygulamanız, etkin anahtar ([CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)) denetimi tarafından belirtilen bilgileri iki şekilde kullanabilir:

- Etkinleştirmek üzere pencereye bir [wm_sethotkey](/windows/win32/inputdev/wm-sethotkey) iletisi göndererek alt öğe olmayan bir pencerenin etkinleştirilmesi için genel bir sık kullanılan anahtar ayarlayın.

- [Registerkısayol](/windows/win32/api/winuser/nf-winuser-registerhotkey)Windows işlevini çağırarak iş parçacığına özgü bir etkin anahtar ayarlayın.

## <a name="see-also"></a>Ayrıca bkz.

[CHotKeyCtrl Kullanma](../mfc/using-chotkeyctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
