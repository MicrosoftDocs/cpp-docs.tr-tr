---
description: 'Hakkında daha fazla bilgi edinin: kod sihirbazları olmadan denetimlere erişim Type-Safe'
title: Kod Sihirbazları Olmadan Denetimlere Tür Kullanımı Uyumlu Erişim
ms.date: 11/04/2016
helpviewer_keywords:
- dialog boxes [MFC], accessing controls
- dialog box controls [MFC], accessing
ms.assetid: 325b4927-d49b-42b4-8e0b-fc84f31fb059
ms.openlocfilehash: 1e59353a17f0d841cd69fa64f792dcc7cdbfa6ad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263783"
---
# <a name="type-safe-access-to-controls-without-code-wizards"></a>Kod Sihirbazları Olmadan Denetimlere Tür Kullanımı Uyumlu Erişim

Denetimlere tür kullanımı uyumlu erişim oluşturmaya yönelik ilk yaklaşım, `CWnd` `GetDlgItem` Bu örnekte olduğu gibi, sınıfın üye işlevinin dönüş türünü uygun C++ denetim türüne dönüştürmek için bir satır içi üye işlevi kullanır:

[!code-cpp[NVC_MFCControlLadenDialog#50](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_1.cpp)]

Daha sonra, aşağıdakine benzer kodla tür kullanımı güvenli bir şekilde denetime erişmek için bu üye işlevini kullanabilirsiniz:

[!code-cpp[NVC_MFCControlLadenDialog#51](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_2.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Iletişim kutusundaki denetimlere tür kullanımı uyumlu erişim](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)<br/>
[Kod sihirbazları Ile denetimlere tür kullanımı uyumlu erişim](../mfc/type-safe-access-to-controls-with-code-wizards.md)
