---
title: Geçersiz kılınabilir CWinApp üye işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CWinApp
dev_langs:
- C++
helpviewer_keywords:
- overriding [MFC], overridable functions in CWinApp
- application class [MFC]
- CWinApp class [MFC], overridables
ms.assetid: 07183d5e-734b-45d9-a8b6-9dde4adac0b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ced9d7d5f7f49df50e028a299f83ddebdc9fc2d1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46395140"
---
# <a name="overridable-cwinapp-member-functions"></a>Geçersiz Kılınabilir CWinApp Üye İşlevleri

[CWinApp](../mfc/reference/cwinapp-class.md) birkaç anahtar geçersiz kılınabilir üye işlevleri sağlar (`CWinApp` sınıfından bu üyeleri geçersiz kılar [CWinThread](../mfc/reference/cwinthread-class.md), içinden `CWinApp` türetilir):

- [InitInstance](../mfc/initinstance-member-function.md)

- [Çalıştırma](../mfc/run-member-function.md)

- [ExitInstance](../mfc/exitinstance-member-function.md)

- [ONIDLE](../mfc/onidle-member-function.md)

Yalnızca `CWinApp` geçersiz kılmanız gerekir üye işlevi olan `InitInstance`.

## <a name="see-also"></a>Ayrıca Bkz.

[CWinApp: Uygulama Sınıfı](../mfc/cwinapp-the-application-class.md)
