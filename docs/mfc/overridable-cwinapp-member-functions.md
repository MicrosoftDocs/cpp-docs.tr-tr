---
description: 'Daha fazla bilgi edinin: geçersiz kılınabilir CWinApp Üye Işlevleri'
title: Geçersiz Kılınabilir CWinApp Üye İşlevleri
ms.date: 11/04/2016
helpviewer_keywords:
- overriding [MFC], overridable functions in CWinApp
- application class [MFC]
- CWinApp class [MFC], overridables
ms.assetid: 07183d5e-734b-45d9-a8b6-9dde4adac0b4
ms.openlocfilehash: 3958ad0edc1fbdb77e1f6ce3252fd03d7595344a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330103"
---
# <a name="overridable-cwinapp-member-functions"></a>Geçersiz Kılınabilir CWinApp Üye İşlevleri

[CWinApp](reference/cwinapp-class.md) , birden fazla geçersiz kılınabilir üye işlevi sağlar ( `CWinApp` Bu üyeleri türetilmiş sınıfından bu üyeleri geçersiz kılar [](reference/cwinthread-class.md) `CWinApp` ):

- [InitInstance](initinstance-member-function.md)

- [Çalıştır](run-member-function.md)

- [ExitInstance](exitinstance-member-function.md)

- [OnIdle](onidle-member-function.md)

`CWinApp`Geçersiz kılmanız gereken tek üye işlevi `InitInstance` .

## <a name="see-also"></a>Ayrıca bkz.

[CWinApp: uygulama sınıfı](cwinapp-the-application-class.md)
