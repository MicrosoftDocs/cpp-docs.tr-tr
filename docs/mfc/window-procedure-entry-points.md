---
description: 'Daha fazla bilgi edinin: pencere yordamı giriş noktaları'
title: Pencere Yordamı Giriş Noktaları
ms.date: 11/04/2016
helpviewer_keywords:
- state management, window procedures
- MFC, managing state data
- window procedure entry points
- entry points, window procedures
ms.assetid: a6b46a7f-6e42-45f2-9ae6-82e19fc57148
ms.openlocfilehash: 2c2e5dc5d37a2e6f187e694d39205c4cd95b3810
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214487"
---
# <a name="window-procedure-entry-points"></a>Pencere Yordamı Giriş Noktaları

MFC pencere yordamlarını korumak için bir modül statik bir pencere yordam uygulamasıyla bağlantı sağlar. Modül MFC ile bağlandığında bağlantı otomatik olarak gerçekleşir. Bu pencere yordamı, etkin modül durumunu düzgün bir şekilde ayarlamak için AFX_MANAGE_STATE makrosunu kullanır ve ardından `AfxWndProc` , `WindowProc` uygun türetilmiş nesnenin üye işlevine devreder `CWnd` .

## <a name="see-also"></a>Ayrıca bkz.

[MFC modüllerinin durum verilerini yönetme](../mfc/managing-the-state-data-of-mfc-modules.md)
