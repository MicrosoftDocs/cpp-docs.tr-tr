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
ms.openlocfilehash: 35db009f86a0cb984f70a349a3ecdd93bfefb0f0
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57261251"
---
# <a name="overridable-cwinapp-member-functions"></a>Geçersiz Kılınabilir CWinApp Üye İşlevleri

[CWinApp](../mfc/reference/cwinapp-class.md) birkaç anahtar geçersiz kılınabilir üye işlevleri sağlar (`CWinApp` sınıfından bu üyeleri geçersiz kılar [CWinThread](../mfc/reference/cwinthread-class.md), içinden `CWinApp` türetilir):

- [InitInstance](../mfc/initinstance-member-function.md)

- [Çalıştır](../mfc/run-member-function.md)

- [ExitInstance](../mfc/exitinstance-member-function.md)

- [ONIDLE](../mfc/onidle-member-function.md)

Yalnızca `CWinApp` geçersiz kılmanız gerekir üye işlevi olan `InitInstance`.

## <a name="see-also"></a>Ayrıca bkz.

[CWinApp: Uygulama sınıfı](../mfc/cwinapp-the-application-class.md)
