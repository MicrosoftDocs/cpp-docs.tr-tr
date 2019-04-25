---
title: Kullanıcı Arabirimi Nesneleri ve Komut Kimlikleri
ms.date: 11/19/2018
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
ms.openlocfilehash: 54372facc51062add122c1db2e01e3081127512e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180628"
---
# <a name="user-interface-objects-and-command-ids"></a>Kullanıcı Arabirimi Nesneleri ve Komut Kimlikleri

Menü öğeleri, araç çubuğu düğmeleri ve kısayol tuşları olan "kullanıcı arabirimi nesneleri" komutları oluşturma yeteneği. Her tür kullanıcı arabirimi nesnesi, bir kimliği vardır. Bir kullanıcı arabirimi nesnesi nesne ve komut aynı kimliği atayarak bir komut ile ilişkilendirin. İçinde anlatıldığı gibi [iletileri](../mfc/messages.md), komutları, özel ileti olarak uygulanır. "Komutları, Framework" Aşağıdaki şekil, framework komutları nasıl yönettiğini gösterir. Ne zaman bir kullanıcı arabirimi nesnesi oluşturur, komut gibi `ID_EDIT_CLEAR_ALL`, uygulamanızdaki nesneleri birini işler komutu — Aşağıda, belge nesnenin şekildeki `OnEditClearAll` belgenin ileti eşlemesi çağrılan işlev.

![Framework'te komutları](../mfc/media/vc385p1.gif "Framework komutları") <br/>
Framework'te komutları

"Komut güncelleştirme içinde Framework" aşağıdaki şekilde, MFC menü öğeleri ve araç çubuğu düğmeleri gibi kullanıcı arabirimi nesneleri güncelleştirmeleri nasıl gösterilmektedir. Önce aşağı doğru açılır menü veya araç çubuğu düğmeleri söz konusu olduğunda boşta döngü sırasında güncelleştirme komutu MFC yönlendirir. Aşağıdaki çizimde, belge nesnesi güncelleştirme komut işleyicisi, çağıran `OnUpdateEditClearAll`, etkinleştirme veya devre dışı kullanıcı arabirimi nesnesi.

![Komutu Framework güncelleştirme](../mfc/media/vc385p2.png "komutu Framework güncelleştiriliyor") <br/>
Komutu Framework güncelleştiriliyor

## <a name="see-also"></a>Ayrıca bkz.

[Framework'teki İletiler ve Komutlar](../mfc/messages-and-commands-in-the-framework.md)
