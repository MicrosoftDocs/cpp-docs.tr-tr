---
title: Kod sihirbazları olmadan denetimlere tür kullanımı uyumlu erişim | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [MFC], accessing controls
- dialog box controls [MFC], accessing
ms.assetid: 325b4927-d49b-42b4-8e0b-fc84f31fb059
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2685c946b9ee1c738ee83f9413b7fd955857febb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438346"
---
# <a name="type-safe-access-to-controls-without-code-wizards"></a>Kod Sihirbazları Olmadan Denetimlere Tür Kullanımı Uyumlu Erişim

Denetimlere tür kullanımı uyumlu erişim oluşturmanın ilk yaklaşım bir satır içi üye işlevi kullanan sınıf dönüş türüne dönüştürmeyi `CWnd`'s `GetDlgItem` üye işlevi bu örnekte olduğu gibi uygun C++ denetim türü için:

[!code-cpp[NVC_MFCControlLadenDialog#50](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_1.cpp)]

Ardından bu üye işlevi bir tür kullanımı uyumlu şekilde aşağıdakine benzer bir kod ile erişim denetimi için de kullanabilirsiniz:

[!code-cpp[NVC_MFCControlLadenDialog#51](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_2.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[Bir İletişim Kutusundaki Denetimlere Tür Kullanımı Uyumlu Erişim](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)<br/>
[Kod Sihirbazları Kullanarak Denetimlere Tür Kullanımı Uyumlu Erişim](../mfc/type-safe-access-to-controls-with-code-wizards.md)

