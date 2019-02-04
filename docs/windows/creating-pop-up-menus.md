---
title: Açılır menüler oluşturma (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- context menus [C++], Menu Editor
- pop-up menus [C++], creating
- menus [C++], pop-up
- menus [C++], creating
- shortcut menus [C++], creating
- pop-up menus [C++], displaying
- pop-up menus [C++], connecting to applications
- context menus [C++], connecting to applications
- shortcut menus [C++], connecting to applications
- pop-up menus
ms.assetid: dff4dddf-2e8d-4c34-b755-90baae426b58
ms.openlocfilehash: cf2e3578f49cb6b4af8797052273211f699a6b4f
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55702836"
---
# <a name="creating-pop-up-menus-c"></a>Açılır menüler oluşturma (C++)

[Açılır menüler](../mfc/menus-mfc.md) görüntü sık kullanılan komutları. Bağlama duyarlı işaretçisi konumunu olabilirler. Uygulamanıza açılır menüleri kullanarak menü oluşturmak ve ardından uygulama koduna bağlanmayı gerektirir.

Menü kaynağı oluşturduktan sonra uygulama kodunuz menü kaynağı yüklemek ve kullanmak gereken [TrackPopupMenu](/windows/desktop/api/winuser/nf-winuser-trackpopupmenu) menüsünün görünmesi neden olacak. Kullanıcı açılır menüyü dışında seçerek kapatıldı veya bir komut seçilmiş sonra bu işlev döndürür. Kullanıcı komut seçerse, tanıtıcı geçirildi penceresine komut ileti gönderilir.

## <a name="to-create-a-pop-up-menu"></a>Açılır menü oluşturmak için

1. [Menü oluşturmak](../windows/creating-a-menu.md) boş bir başlığa sahip (sağlamayan bir **açıklamalı alt yazı**).

1. [Yeni menüsüne bir menü komutu eklemek](../windows/adding-commands-to-a-menu.md). Boş Menü başlığının altında ilk menü Komut çubuğuna Taşı (geçici açıklamalı alt yazı yazan `Type Here`). Tür a **açıklamalı alt yazı** ve diğer bilgiler.

   Diğer bir menü komutları açılır menüde için bu işlemi yineleyin.

1. Menü kaynağı kaydedin.

## <a name="to-connect-a-pop-up-menu-to-your-application"></a>Açılır menü, uygulamanızı bağlamak için

1. Bir ileti işleyicisi WM_CONTEXTMENU için (örneğin) ekleyin. Daha fazla bilgi için [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md).

1. Aşağıdaki kodu için ileti işleyicisi ekleyin:

    ```cpp
    CMenu menu;
    VERIFY(menu.LoadMenu(IDR_MENU1));
    CMenu* pPopup = menu.GetSubMenu(0);
    ASSERT(pPopup != NULL);
    pPopup->TrackPopupMenu(TPM_LEFTALIGN | TPM_RIGHTBUTTON, point.x, point.y, AfxGetMainWnd());
    ```

   > [!NOTE]
   > [CPoint](../atl-mfc-shared/reference/cpoint-class.md) geçirilen ekran koordinatlarında ileti işleyicisidir.

   > [!NOTE]
   > Uygulamanıza açılır menü bağlantısı MFC gerektirir.

## <a name="to-view-a-menu-resource-as-a-pop-up-menu"></a>Açılır menü olarak menü kaynağı görüntülemek için

Normalde, ne zaman çalışmakta olduğunuz **menü** Düzenleyicisi, bir menü kaynağı bir menü çubuğu görüntülenir. Ancak, program çalışırken uygulamanın menü çubuğuna eklediğiniz menü kaynaklarınız olabilir.

Menüyü sağ tıklatın ve seçin **pencerede görüntüle** kısayol menüsünden.

   Bu seçenek yalnızca görüntüleme tercihi olan ve menünüzde değiştirmez.

   > [!NOTE]
   > Menü çubuğunun görünümünü değiştirmek için tıklayın **pencerede görüntüle** yeniden (onay işaretini kaldırır ve menü çubuğu görünümünüzü döndürür).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Menü Düzenleyicisi](../windows/menu-editor.md)
