---
title: Pencere Yordamı Giriş Noktaları
ms.date: 11/04/2016
helpviewer_keywords:
- state management, window procedures
- MFC, managing state data
- window procedure entry points
- entry points, window procedures
ms.assetid: a6b46a7f-6e42-45f2-9ae6-82e19fc57148
ms.openlocfilehash: 6d91e2c432588afc5a84f7189fa87a7fc2531b1a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62372018"
---
# <a name="window-procedure-entry-points"></a>Pencere Yordamı Giriş Noktaları

MFC pencere yordamları, modülü statik bağlantılar, özel pencere yordamı uygulama korumak için. İle MFC modül bağlandığında bağlantı otomatik olarak gerçekleşir. Etkili Modül durumu düzgün bir şekilde ayarlamak için AFX_MANAGE_STATE makrosu Bu pencere yordamını kullanır ve ardından onu çağıran `AfxWndProc`, hangi sırayla temsilciler için `WindowProc` uygun üye işlevinin `CWnd`-türetilmiş bir nesneye.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Modüllerinin Durum Verisini Yönetme](../mfc/managing-the-state-data-of-mfc-modules.md)
