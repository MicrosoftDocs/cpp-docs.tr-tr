---
title: Pencere yordamı giriş noktaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- state management, window procedures
- MFC, managing state data
- window procedure entry points
- entry points, window procedures
ms.assetid: a6b46a7f-6e42-45f2-9ae6-82e19fc57148
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c3226df51d2a83484de78d0d76c9af67e150e8eb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46403194"
---
# <a name="window-procedure-entry-points"></a>Pencere Yordamı Giriş Noktaları

MFC pencere yordamları, modülü statik bağlantılar, özel pencere yordamı uygulama korumak için. İle MFC modül bağlandığında bağlantı otomatik olarak gerçekleşir. Etkili Modül durumu düzgün bir şekilde ayarlamak için AFX_MANAGE_STATE makrosu Bu pencere yordamını kullanır ve ardından onu çağıran `AfxWndProc`, hangi sırayla temsilciler için `WindowProc` uygun üye işlevinin `CWnd`-türetilmiş bir nesneye.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC Modüllerinin Durum Verisini Yönetme](../mfc/managing-the-state-data-of-mfc-modules.md)

