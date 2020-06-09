---
title: Geçersiz Kılınabilir CWinApp Üye İşlevleri
ms.date: 11/04/2016
helpviewer_keywords:
- overriding [MFC], overridable functions in CWinApp
- application class [MFC]
- CWinApp class [MFC], overridables
ms.assetid: 07183d5e-734b-45d9-a8b6-9dde4adac0b4
ms.openlocfilehash: 7ae72a52c37582f8398ebc03f404ff105fe14650
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624007"
---
# <a name="overridable-cwinapp-member-functions"></a>Geçersiz Kılınabilir CWinApp Üye İşlevleri

[CWinApp](reference/cwinapp-class.md) , birden fazla geçersiz kılınabilir üye işlevi sağlar ( `CWinApp` Bu üyeleri türetilmiş sınıfından bu üyeleri geçersiz kılar [CWinThread](reference/cwinthread-class.md) `CWinApp` ):

- [InitInstance](initinstance-member-function.md)

- [Çalıştır](run-member-function.md)

- [ExitInstance](exitinstance-member-function.md)

- [OnIdle](onidle-member-function.md)

`CWinApp`Geçersiz kılmanız gereken tek üye işlevi `InitInstance` .

## <a name="see-also"></a>Ayrıca bkz.

[CWinApp: Uygulama Sınıfı](cwinapp-the-application-class.md)
