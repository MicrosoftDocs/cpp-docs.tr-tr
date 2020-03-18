---
title: Geçersiz Kılınabilir CWinApp Üye İşlevleri
ms.date: 11/04/2016
helpviewer_keywords:
- overriding [MFC], overridable functions in CWinApp
- application class [MFC]
- CWinApp class [MFC], overridables
ms.assetid: 07183d5e-734b-45d9-a8b6-9dde4adac0b4
ms.openlocfilehash: 28ba243bd755e25db5f2cb03d08013f082fbc918
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447256"
---
# <a name="overridable-cwinapp-member-functions"></a>Geçersiz Kılınabilir CWinApp Üye İşlevleri

[CWinApp](../mfc/reference/cwinapp-class.md) , birkaç geçersiz kılınabilir üye işlevi sağlar (`CWinApp`, bu üyeleri `CWinApp` türettiği, [CWinThread](../mfc/reference/cwinthread-class.md)sınıfından geçersiz kılar):

- [InitInstance](../mfc/initinstance-member-function.md)

- [Çalıştır](../mfc/run-member-function.md)

- [ExitInstance](../mfc/exitinstance-member-function.md)

- [OnIdle](../mfc/onidle-member-function.md)

Geçersiz kılmanız gereken tek `CWinApp` üye işlevi `InitInstance`.

## <a name="see-also"></a>Ayrıca bkz.

[CWinApp: Uygulama Sınıfı](../mfc/cwinapp-the-application-class.md)
