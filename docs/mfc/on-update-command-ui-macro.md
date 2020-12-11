---
description: 'Hakkında daha fazla bilgi edinin: ON_UPDATE_COMMAND_UI makrosu'
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
ms.openlocfilehash: 394ee2679e84c09223f61d485fac3e628dec7145
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112173"
---
# <a name="on_update_command_ui-macro"></a>ON_UPDATE_COMMAND_UI Makrosu

Bir kullanıcı arabirimi nesnesini bir komut-hedef nesnesindeki bir komut güncelleştirme işleyicisine bağlamak için, **sınıf görünümü** açın, ardından işleyicinin ekleneceği sınıfa sağ tıklayın ve **sınıf Sihirbazı**' nı seçin. Sol taraftaki listede Kullanıcı arabirimi nesnesinin KIMLIĞINI bulun, ardından sağ bölmedeki **UPDATE_COMMAND_UI** seçin ve **İşleyici Ekle**' ye tıklayın. Bu, sınıfında bir işleyici işlevi oluşturur ve ileti eşlemesine uygun girişi ekler. Daha fazla bilgi için bkz. [Iletileri IŞLEVLERE eşleme](reference/mapping-messages-to-functions.md) . **İletiler** bölmesinde işlenecek ek iletiler belirtebilirsiniz.

Örneğin, programınızın düzenleme menüsünde Tümünü Temizle komutunu güncelleştirmek için, seçili sınıfta bir ileti eşleme girişi,  sınıf bildiriminde çağrılan bir komut güncelleştirme işleyicisi için bir işlev bildirimi `OnUpdateEditClearAll` ve sınıfın uygulama dosyasında boş bir işlev şablonu eklemek için sınıf Sihirbazı ' nı kullanın. İşlev prototipi şöyle görünür:

[!code-cpp[NVC_MFCDocView#2](codesnippet/cpp/on-update-command-ui-macro_1.h)]

Tüm işleyiciler gibi, işlev bildiriminde **afx_msg** anahtar sözcüğü gösterilmektedir. Tüm güncelleştirme işleyicileri gibi, bir nesneye yönelik bir işaretçi olan bir bağımsız değişken alır `CCmdUI` .

## <a name="see-also"></a>Ayrıca bkz.

[Nasıl yapılır: User-Interface nesneleri güncelleştirme](how-to-update-user-interface-objects.md)
