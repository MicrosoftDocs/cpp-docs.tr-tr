---
title: Kullanıcı Arabirimi Nesneleri ve Komut Kimlikleri
ms.date: 11/04/2016
helpviewer_keywords:
- keyboard shortcuts, associating with IDs
- MFC, command routing
- toolbar controls [MFC], command ID
- menu items, associating with IDs
- user interface objects [MFC], associating with IDs
- command IDs, user interface objects
- command routing [MFC], MFC
- command handling [MFC], user-interface objects
ms.assetid: 4ea19e9b-ed1e-452e-bd33-7f509107a45b
ms.openlocfilehash: 508e7076797d48e0940b509afa3b94a7b766ebf3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615364"
---
# <a name="user-interface-objects-and-command-ids"></a>Kullanıcı Arabirimi Nesneleri ve Komut Kimlikleri

Menü öğeleri, araç çubuğu düğmeleri ve kısayol tuşları olan "kullanıcı arabirimi nesneleri" komutları oluşturma yeteneği. Her tür kullanıcı arabirimi nesnesi, bir kimliği vardır. Bir kullanıcı arabirimi nesnesi nesne ve komut aynı kimliği atayarak bir komut ile ilişkilendirin. İçinde anlatıldığı gibi [iletileri](../mfc/messages.md), komutları, özel ileti olarak uygulanır. "Komutları, Framework" Aşağıdaki şekil, framework komutları nasıl yönettiğini gösterir. Ne zaman bir kullanıcı arabirimi nesnesi oluşturur, komut gibi `ID_EDIT_CLEAR_ALL`, uygulamanızdaki nesneleri birini işler komutu — Aşağıda, belge nesnenin şekildeki `OnEditClearAll` belgenin ileti eşlemesi çağrılan işlev.

![Framework'te komutları](../mfc/media/vc385p1.gif "vc385p1") Framework komutları

"Komut güncelleştirme içinde Framework" aşağıdaki şekilde, MFC menü öğeleri ve araç çubuğu düğmeleri gibi kullanıcı arabirimi nesneleri güncelleştirmeleri nasıl gösterilmektedir. Önce aşağı doğru açılır menü veya araç çubuğu düğmeleri söz konusu olduğunda boşta döngü sırasında güncelleştirme komutu MFC yönlendirir. Aşağıdaki çizimde, belge nesnesi güncelleştirme komut işleyicisi, çağıran `OnUpdateEditClearAll`, etkinleştirme veya devre dışı kullanıcı arabirimi nesnesi.

![Komutu Framework güncelleştirme](../mfc/media/vc385p2.png "vc385p2") Framework komut güncelleştiriliyor

## <a name="see-also"></a>Ayrıca Bkz.

[Framework'teki İletiler ve Komutlar](../mfc/messages-and-commands-in-the-framework.md)

