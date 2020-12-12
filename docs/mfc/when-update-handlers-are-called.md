---
description: 'Hakkında daha fazla bilgi edinin: güncelleştirme Işleyicileri çağrıldığında'
title: Güncelleştirme İşleyicilerini Çağırma Zamanı
ms.date: 11/04/2016
helpviewer_keywords:
- updating user interface objects [MFC]
- command routing [MFC], update commands
- toolbar buttons [MFC], enabling
- disabling toolbar buttons
- menus [MFC], initializing
- update handlers [MFC]
- disabling menu items
- toolbars [MFC], updating
- menus [MFC], updating as context changes
- toolbar controls [MFC], updated during OnIdle method [MFC]
- menu items, enabling
- command routing [MFC], update handlers
- update handlers, calling
ms.assetid: 7359f6b1-4669-477d-bd99-690affed08d9
ms.openlocfilehash: ee5d402eea4121c9ceb4bcbd48e752549c55b1c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297180"
---
# <a name="when-update-handlers-are-called"></a>Güncelleştirme İşleyicilerini Çağırma Zamanı

Kullanıcının, WM_INITMENUPOPUP bir ileti üreten Dosya menüsünde fareyle tıkladığını varsayın. Framework 'ün güncelleştirme mekanizması, Kullanıcı tarafından görebilmek için menü kapatılmadan önce Dosya menüsündeki tüm öğeleri topluca günceller.

Bunu yapmak için Framework, açılan menüdeki tüm menü öğelerinin güncelleştirme komutlarını standart komut yönlendirme boyunca yönlendirir. Yönlendirmenin komut hedefleri, uygun bir ileti eşleme girdisiyle (forma `ON_UPDATE_COMMAND_UI` ) ve "güncelleştirme işleyicisi" işlevine çağırarak, herhangi bir menü öğesini güncelleştirme komutunu eşleştirerek güncelleştirme fırsatına sahiptir. Bu nedenle, altı menü öğesi olan bir menü için altı güncelleştirme komutu gönderilir. Menü öğesinin komut KIMLIĞI için bir güncelleştirme işleyici varsa, bu güncelleştirme yapmak için çağrılır. Aksi takdirde, çerçeve bu komut KIMLIĞI için bir işleyicinin varlığını denetler ve menü öğesini uygun şekilde etkinleştirip devre dışı bırakır.

Çerçeve `ON_UPDATE_COMMAND_UI` komut yönlendirme sırasında bir giriş bulamazsa, aynı komut kimliğiyle bir giriş varsa, Kullanıcı arabirimi nesnesine otomatik olarak izin verilir `ON_COMMAND` . Aksi takdirde, Kullanıcı arabirimi nesnesini devre dışı bırakır. Bu nedenle, bir kullanıcı arabirimi nesnesinin etkinleştirildiğinden emin olmak için, nesnenin bir güncelleştirme işleyicisi oluşturduğu veya sağlaması için bir işleyici sağlayın. [Kullanıcı arabirimi nesneleri ve komut kimlikleri](../mfc/user-interface-objects-and-command-ids.md)konusundaki şekle bakın.

Kullanıcı arabirimi nesnelerinin varsayılan devre dışı bırakılmasını devre dışı bırakmak mümkündür. Daha fazla bilgi için bkz [](../mfc/reference/cframewnd-class.md#m_bautomenuenable) `CFrameWnd` . *MFC başvurusu* içindeki sınıfın m_bAutoMenuEnable üyesi.

Menü başlatma, uygulama WM_INITMENUPOPUP bir ileti aldığında ortaya çıkan otomatiktir. Boşta döngüsü sırasında çerçeve, düğme güncelleştirme işleyicileri için komut yönlendirmesini menülerde olduğu şekilde arar.

## <a name="see-also"></a>Ayrıca bkz.

[Nasıl yapılır: User-Interface nesneleri güncelleştirme](../mfc/how-to-update-user-interface-objects.md)
