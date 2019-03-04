---
title: Kod Sihirbazları Olmadan Denetimlere Tür Kullanımı Uyumlu Erişim
ms.date: 11/04/2016
helpviewer_keywords:
- dialog boxes [MFC], accessing controls
- dialog box controls [MFC], accessing
ms.assetid: 325b4927-d49b-42b4-8e0b-fc84f31fb059
ms.openlocfilehash: 5b4b604bf42a327edf3ac7a83dcfc42a5e0d8c54
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57261121"
---
# <a name="type-safe-access-to-controls-without-code-wizards"></a>Kod Sihirbazları Olmadan Denetimlere Tür Kullanımı Uyumlu Erişim

Denetimlere tür kullanımı uyumlu erişim oluşturmanın ilk yaklaşım bir satır içi üye işlevi kullanan sınıf dönüş türüne dönüştürmeyi `CWnd`'s `GetDlgItem` üye işlevi bu örnekte olduğu gibi uygun C++ denetim türü için:

[!code-cpp[NVC_MFCControlLadenDialog#50](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_1.cpp)]

Ardından bu üye işlevi bir tür kullanımı uyumlu şekilde aşağıdakine benzer bir kod ile erişim denetimi için de kullanabilirsiniz:

[!code-cpp[NVC_MFCControlLadenDialog#51](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Bir İletişim Kutusundaki Denetimlere Tür Kullanımı Uyumlu Erişim](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)<br/>
[Kod Sihirbazları Kullanarak Denetimlere Tür Kullanımı Uyumlu Erişim](../mfc/type-safe-access-to-controls-with-code-wizards.md)
