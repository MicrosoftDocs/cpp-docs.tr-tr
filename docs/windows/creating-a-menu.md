---
title: Menüler (C++) oluşturma
ms.date: 11/04/2016
f1_keywords:
- vc.editors.menu
helpviewer_keywords:
- mnemonics [C++], associating menu items
- menus [C++], associating commands with mnemonic keys
- menus [C++], creating
- menus [C++], adding items
- commands [C++], adding to menus
- menu items, adding to menus
- submenus
- submenus [C++], creating
- menus [C++], creating
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
ms.assetid: 66f94448-9b97-4b73-bf97-10d4bf87cc65
ms.openlocfilehash: e3b3cc58b82f68c55ac98601fd11775422c901e5
ms.sourcegitcommit: 5a7dbd640376e13379f5d5b2cf66c4842e5e737b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55905777"
---
# <a name="creating-menus-c"></a>Menüler (C++) oluşturma

> [!NOTE]
> **Kaynak penceresi** Express sürümlerinde kullanılamaz.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="to-create-a-standard-menu"></a>Standart menü oluşturmak için

1. Gelen **görünümü** menüsünde **kaynak görünümü** ve ardından sağ tıklayarak **menü** başlık ve seçin **kaynak Ekle**. Seçin **menü**.

1. Seçin **yeni öğe** menü çubuğundaki kutusuna ("Buraya türü" içeren dikdörtgen).

   ![Menü Düzenleyicisi'nde yeni bir öğe kutusu](../windows/media/vcmenueditornewitembox.gif "vcMenuEditorNewItemBox")<br/>
   Yeni öğe kutusu

1. Yeni menünüzde, örneğin, "File" için bir ad yazın.

   Her ikisinde de, yazdığınız metni görünür **menü** Düzenleyicisi ve **açıklamalı alt yazı** kutusunda [Özellikler penceresi](/visualstudio/ide/reference/properties-window). Her iki konumda yeni menünüzde özelliklerini düzenleyebilirsiniz.

   Menü çubuğunda yeni menünüzde bir adı verilen sonra yeni öğe kutusunu (başka bir menü eklemenize izin vermek için) sağa kaydırır ve menü komutları ekleyebilmek için ilk menünüzün başka bir yeni öğe kutusu açılır.

   ![Genişletilmiş yeni öğe kutusunda](../windows/media/vcmenueditornewitemboxexpanded.gif "vcMenuEditorNewItemBoxExpanded")<br/>
   Menü adını yazdıktan sonra yeni öğe kutusu odaklanılan kaydırılacağı uzaklık.

   > [!NOTE]
   > Menü çubuğunda bir tek öğesi menüsü oluşturmak için **açılan** özelliğini **False**.

## <a name="to-create-a-submenu"></a>Alt menü oluşturma

1. Alt menü oluşturmak istediğiniz komutu seçin.

1. İçinde **yeni öğe** sağda açılan kutusunda yeni menü komutunu adını yazın. Bu yeni komut ilk alt menüsünde görüntülenir.

1. Ek menü komutları, alt menüyü ekleyin.

## <a name="to-insert-a-new-menu-between-existing-menus"></a>Mevcut menülerin arasına yeni menü eklemek için

Var olan bir menü adı ve ENTER tuşuna seçin **Ekle** anahtarı. **Yeni öğe** kutusu önce seçilen öğe eklenir.

   \- veya -

Menü çubuğunda sağ tıklatın ve seçin **yeni Ekle** kısayol menüsünden.

## <a name="to-add-commands-to-a-menu"></a>Bir menü komutları eklemek için

1. Bir menü oluşturun.

1. Örneğin, bir menü adı seçin **dosya**.

   Her menüsünü genişletin ve komutlar için yeni bir öğe kutusu kullanıma sunar. Örneğin, komutlar ekleyebilirsiniz **yeni**, **açık**, ve **Kapat** için bir **dosya** menüsü.

1. Yeni öğe kutuya yeni bir menü komutu için bir ad yazın.

   > [!NOTE]
   > Her ikisinde de, yazdığınız metni görünür **menü** Düzenleyicisi ve **açıklamalı alt yazı** kutusunda [Özellikler penceresi](/visualstudio/ide/reference/properties-window). Her iki konumda yeni menünüzde özelliklerini düzenleyebilirsiniz.

   > [!TIP]
   > Menü komutunu seçmesini sağlayan bir kısayol tuşu (kısayol tuşu) tanımlayabilirsiniz. Ve işareti yazın (`&`) anımsatıcı belirtmek için bir harf önünde. Kullanıcı, harf yazarak menü komutunu seçebilir.

1. İçinde **özellikleri** menü uygulanan özellikleri komut penceresinde, seçin. Ayrıntılar için bkz [menü komut özellikleri](../windows/menu-command-properties.md).

1. İçinde **istemi** kutusunda **özellikleri** penceresinde, uygulamanızın durum çubuğunda görüntülenmesini istediğiniz istem dizesi yazın.

   Bu adım, aynı kaynak tanımlayıcısı olarak oluşturduğunuz menü komutu ile dize tablosunda bir giriş oluşturur.

   > [!NOTE]
   > Komut istemlerini ile menü öğesi için yalnızca uygulayabileceğiniz bir **açılan** özelliği **True**. Örneğin, bunlar alt menü öğeleri varsa en üst düzey menü öğeleri istemleri olabilir. Amacı, bir **istemi** ne olacağını belirtmek için bir kullanıcı menü öğesi seçtiğinde.

1. Tuşuna **Enter** menü komutu tamamlamak için.

   Ek menü komutlarını oluşturmak için yeni bir öğe kutusunda seçilir.

## <a name="to-create-pop-up-menus"></a>Açılır menüler oluşturma

[Açılır menüler](../mfc/menus-mfc.md) görüntü sık kullanılan komutları. Bağlama duyarlı işaretçisi konumunu olabilirler. Uygulamanıza açılır menüleri kullanarak menü oluşturmak ve ardından uygulama koduna bağlanmayı gerektirir.

Menü kaynağı oluşturduktan sonra uygulama kodunuz menü kaynağı yüklemek ve kullanmak gereken [TrackPopupMenu](/windows/desktop/api/winuser/nf-winuser-trackpopupmenu) menüsünün görünmesi neden olacak. Kullanıcı açılır menüyü dışında seçerek kapatıldı veya bir komut seçilmiş sonra bu işlev döndürür. Kullanıcı komut seçerse, tanıtıcı geçirildi penceresine komut ileti gönderilir.

### <a name="to-create-a-pop-up-menu"></a>Açılır menü oluşturmak için

1. [Menü oluşturmak](../windows/creating-a-menu.md) boş bir başlığa sahip (sağlamayan bir **açıklamalı alt yazı**).

1. [Yeni menüsüne bir menü komutu eklemek](../windows/adding-commands-to-a-menu.md). Boş Menü başlığının altında ilk menü Komut çubuğuna Taşı (geçici açıklamalı alt yazı yazan `Type Here`). Tür a **açıklamalı alt yazı** ve diğer bilgiler.

   Diğer bir menü komutları açılır menüde için bu işlemi yineleyin.

1. Menü kaynağı kaydedin.

### <a name="to-connect-a-pop-up-menu-to-your-application"></a>Açılır menü, uygulamanızı bağlamak için

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

### <a name="to-view-a-menu-resource-as-a-pop-up-menu"></a>Açılır menü olarak menü kaynağı görüntülemek için

Normalde, ne zaman çalışmakta olduğunuz **menü** Düzenleyicisi, bir menü kaynağı bir menü çubuğu görüntülenir. Ancak, program çalışırken uygulamanın menü çubuğuna eklediğiniz menü kaynaklarınız olabilir.

Menüyü sağ tıklatın ve seçin **pencerede görüntüle** kısayol menüsünden.

   Bu seçenek yalnızca görüntüleme tercihi olan ve menünüzde değiştirmez.

   > [!NOTE]
   > Menü çubuğunun görünümünü değiştirmek için tıklayın **pencerede görüntüle** yeniden (onay işaretini kaldırır ve menü çubuğu görünümünüzü döndürür).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Menü Düzenleyicisi](../windows/menu-editor.md)