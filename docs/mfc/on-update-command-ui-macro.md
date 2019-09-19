---
title: ON_UPDATE_COMMAND_UI Makrosu
ms.date: 09/06/2019
f1_keywords:
- ON_UPDATE_COMMAND_UI
helpviewer_keywords:
- ON_UPDATE_COMMAND_UI macro [MFC]
- update handlers [MFC]
- command-handler macros
- updating user-interface objects [MFC]
ms.assetid: 3e72b50f-4119-4c82-81cf-6e09b132de05
ms.openlocfilehash: 2a3f097a44e96fc470719ce636cc1b73e676fb38
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2019
ms.locfileid: "71095844"
---
# <a name="on_update_command_ui-macro"></a>ON_UPDATE_COMMAND_UI Makrosu

Bir kullanıcı arabirimi nesnesini bir komut-hedef nesnesindeki bir komut güncelleştirme işleyicisine bağlamak için, **sınıf görünümü**açın, ardından işleyicinin ekleneceği sınıfa sağ tıklayın ve **sınıf Sihirbazı**' nı seçin. Sol taraftaki listede Kullanıcı arabirimi nesnesinin KIMLIĞINI bulun, sonra sağ bölmedeki **UPDATE_COMMAND_UI** öğesini seçin ve **İşleyici Ekle**' ye tıklayın. Bu, sınıfında bir işleyici işlevi oluşturur ve ileti eşlemesine uygun girişi ekler. Daha fazla bilgi için bkz. [Iletileri IŞLEVLERE eşleme](../mfc/reference/mapping-messages-to-functions.md) . **İletiler** bölmesinde işlenecek ek iletiler belirtebilirsiniz.

Örneğin, programınızın düzenleme menüsünde Tümünü Temizle komutunu güncelleştirmek için, seçili sınıfta bir ileti eşleme girişi, **sınıf bildiriminde** çağrılan `OnUpdateEditClearAll` bir komut güncelleştirme işleyicisi için işlev bildirimi ve boş bir sınıfın uygulama dosyasındaki işlev şablonu. İşlev prototipi şöyle görünür:

[!code-cpp[NVC_MFCDocView#2](../mfc/codesnippet/cpp/on-update-command-ui-macro_1.h)]

Tüm işleyiciler gibi, işlev bildiriminde **afx_msg** anahtar sözcüğü gösterilmektedir. Tüm güncelleştirme işleyicileri gibi, bir `CCmdUI` nesneye yönelik bir işaretçi olan bir bağımsız değişken alır.

## <a name="see-also"></a>Ayrıca bkz.

[Nasıl yapılır: Kullanıcı Arabirimi Nesnelerini Güncelleştirme](../mfc/how-to-update-user-interface-objects.md)
