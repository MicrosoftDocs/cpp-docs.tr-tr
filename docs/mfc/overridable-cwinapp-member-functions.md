---
title: Geçersiz Kılınabilir CWinApp Üye İşlevleri
ms.date: 11/04/2016
f1_keywords:
- CWinApp
helpviewer_keywords:
- overriding [MFC], overridable functions in CWinApp
- application class [MFC]
- CWinApp class [MFC], overridables
ms.assetid: 07183d5e-734b-45d9-a8b6-9dde4adac0b4
ms.openlocfilehash: 9f1098e305606df9463e308466b7864b019d5a00
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50459286"
---
# <a name="overridable-cwinapp-member-functions"></a>Geçersiz Kılınabilir CWinApp Üye İşlevleri

[CWinApp](../mfc/reference/cwinapp-class.md) birkaç anahtar geçersiz kılınabilir üye işlevleri sağlar (`CWinApp` sınıfından bu üyeleri geçersiz kılar [CWinThread](../mfc/reference/cwinthread-class.md), içinden `CWinApp` türetilir):

- [InitInstance](../mfc/initinstance-member-function.md)

- [Çalıştır](../mfc/run-member-function.md)

- [ExitInstance](../mfc/exitinstance-member-function.md)

- [ONIDLE](../mfc/onidle-member-function.md)

Yalnızca `CWinApp` geçersiz kılmanız gerekir üye işlevi olan `InitInstance`.

## <a name="see-also"></a>Ayrıca Bkz.

[CWinApp: Uygulama Sınıfı](../mfc/cwinapp-the-application-class.md)
