---
title: Pencere Yordamı Giriş Noktaları
ms.date: 11/04/2016
helpviewer_keywords:
- state management, window procedures
- MFC, managing state data
- window procedure entry points
- entry points, window procedures
ms.assetid: a6b46a7f-6e42-45f2-9ae6-82e19fc57148
ms.openlocfilehash: 9e395ff96d27476bc2869e23139cb2d1233f02ee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500925"
---
# <a name="window-procedure-entry-points"></a>Pencere Yordamı Giriş Noktaları

MFC pencere yordamları, modülü statik bağlantılar, özel pencere yordamı uygulama korumak için. İle MFC modül bağlandığında bağlantı otomatik olarak gerçekleşir. Etkili Modül durumu düzgün bir şekilde ayarlamak için AFX_MANAGE_STATE makrosu Bu pencere yordamını kullanır ve ardından onu çağıran `AfxWndProc`, hangi sırayla temsilciler için `WindowProc` uygun üye işlevinin `CWnd`-türetilmiş bir nesneye.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC Modüllerinin Durum Verisini Yönetme](../mfc/managing-the-state-data-of-mfc-modules.md)

