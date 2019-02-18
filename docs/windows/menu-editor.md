---
title: Menü Düzenleyicisi (C++)
ms.date: 02/15/2019
f1_keywords:
- vc.editors.menu.F1
- vc.editors.menu
helpviewer_keywords:
- resource editors [C++], Menu editor
- editors, menus
- Menu editor
- menus [C++], Menu editor
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
- menu commands [C++], selecting
- menus [C++], selecting
- commands [C++], menu commands
- commands [C++], copying on menus
- menu items, moving
- commands [C++], moving on menus
- menu items, copying
- menu items, deleting
- commands [C++], deleting from menus
- menus [C++], deleting
ms.assetid: 421fb215-6e12-4ec9-a3af-82d77f87bfa6
ms.openlocfilehash: 8e97fb88a8860ab0831f62bf2413b1f8f7174c7b
ms.sourcegitcommit: 24592ba0a38c7c996ffd3d55fe1024231a59ccc2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/18/2019
ms.locfileid: "56336689"
---
# <a name="menu-editor-c"></a>Menü Düzenleyicisi (C++)

Menü komutları mantıksal ve bulma kolay bir şekilde Yerleştir olanak sağlar. İle **menü** Düzenleyicisi, oluşturabilir ve menüler doğrudan tamamlanmış uygulamanızdaki bir çok benzeyen bir menü çubuğu birlikte çalışarak düzenleyebilirsiniz.

> [!TIP]
> Kullanırken **menü** düzenleyicisinde birçok örneği, sık kullanılan komutlar açılan menüsünü görüntülemek için sağ fare düğmesine tıklayabilirsiniz. Kullanılabilir komutlar ne işaretçinin işaret ettiği üzerinde bağlıdır.

> [!NOTE]
> Microsoft Foundation Class Kitaplığı'nı (MFC) programları ve ATL programları için kullanabileceğiniz **kod sihirbazları** kod menü komutlarına yeteneklerinizi. Daha fazla bilgi için [olay ekleme](../ide/adding-an-event-visual-cpp.md).

## <a name="how-to"></a>Nasıl Yapılır

> [!NOTE]
> **Kaynak penceresi** Express sürümlerinde kullanılamaz.

**Menü** Düzenleyicisi sağlar:

### <a name="to-create-a-standard-menu"></a>Standart menü oluşturmak için

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

### <a name="to-create-a-submenu"></a>Alt menü oluşturma

1. Alt menü oluşturmak istediğiniz komutu seçin.

1. İçinde **yeni öğe** sağda açılan kutusunda yeni menü komutunu adını yazın. Bu yeni komut ilk alt menüsünde görüntülenir.

1. Ek menü komutları, alt menüyü ekleyin.

## <a name="to-insert-a-new-menu-between-existing-menus"></a>Mevcut menülerin arasına yeni menü eklemek için

Var olan bir menü adı ve ENTER tuşuna seçin **Ekle** tuşunu veya menü çubuğunda sağ tıklayın ve seçin **yeni Ekle** kısayol menüsünden.

**Yeni öğe** kutusu önce seçilen öğe eklenir.

### <a name="to-add-commands-to-a-menu"></a>Bir menü komutları eklemek için

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

### <a name="to-select-multiple-menu-commands"></a>Birden çok menü komutları seçmek için

Birden çok menü adları veya özelliklerini değiştirme veya silme gibi toplu işlemleri çalıştırmak için menü komutları seçebilirsiniz.

Tutarken **Ctrl** anahtar, menüler ya da alt menü komutları, istediğiniz seçin.

### <a name="to-move-and-copy-menus-and-menu-commands"></a>Taşıma ve kopyalama menüleri ve menü komutları

> [!NOTE]
> Sürükleyin, kopyalamak ve diğer menü windows diğer menülere yapıştırın.

#### <a name="to-move-or-copy-menus-or-menu-commands-using-the-drag-and-drop-method"></a>Menüleri ve menü komutlarını sürükle ve bırak yöntemiyle taşınacak veya kopyalanacak

1. Sürükleyin veya taşımak istediğiniz öğeyi kopyalayın:

   - Geçerli menüsünden Yeni bir konum.

   - Farklı bir menü. (Fare işaretçisi sürükleyerek diğer menülere gidebilirsiniz.)

1. İstediğiniz yere klavuzunu gösterdiği durumlarda menü komutunu bırakın.

#### <a name="to-move-or-copy-menus-or-menu-commands-using-shortcut-menu-commands"></a>Taşıma veya kopyalama menü veya menü komutu kısayol menü komutlarını kullanmak için

1. Bir veya birden çok menü veya menü komutu sağ tıklayın.

1. Kısayol menüsünden **Kes** (taşımak için) veya **kopyalama**.

1. Başka bir menü öğeleri taşıyorsanız kaynak veya kaynak betik dosyasını [başka bir pencerede açmak](/visualstudio/ide/customizing-window-layouts-in-visual-studio).

1. Menü veya menü komutu taşımak veya kopyalamak istediğiniz konumu seçin.

1. Kısayol menüsünden **Yapıştır**. Seçtiğiniz öğe önce taşınmış ya da kopyalanmış öğesi yerleştirilir.

### <a name="to-delete-a-menu-or-menu-command"></a>Bir menü veya menü komutu silmek için

Menü adına veya komuta sağ tıklatın ve seçin **Sil** kısayol menüsünden.

> [!NOTE]
> Benzer şekilde, kopyalama, kesme, yapıştırma, yeni, Ekle ayırıcı, kimlikleri, düzenleme görünümü açılır, anımsatıcıları kontrol edin, vb. olarak Ekle gibi diğer eylemleri gerçekleştirmek için kısayol menüsünü kullanabilirsiniz.

## <a name="pop-up-menus"></a>Açılır menüler

[Açılır menüler](../mfc/menus-mfc.md) görüntü sık kullanılan komutları. Bağlama duyarlı işaretçisi konumunu olabilirler. Uygulamanıza açılır menüleri kullanarak menü oluşturmak ve ardından uygulama koduna bağlanmayı gerektirir.

Menü kaynağı oluşturduktan sonra uygulama kodunuz menü kaynağı yüklemek ve kullanmak gereken [TrackPopupMenu](/windows/desktop/api/winuser/nf-winuser-trackpopupmenu) menüsünün görünmesi neden olacak. Kullanıcı açılır menüyü dışında seçerek kapatıldı veya bir komut seçilmiş sonra bu işlev döndürür. Kullanıcı komut seçerse, tanıtıcı geçirildi penceresine komut ileti gönderilir.

### <a name="to-create-a-pop-up-menu"></a>Açılır menü oluşturmak için

1. Boş bir başlığa sahip menü oluşturmak (sağlamayan bir **açıklamalı alt yazı**).

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
> Menü çubuğunun görünümünü değiştirmek için seçin **pencerede görüntüle** yeniden (onay işaretini kaldırır ve menü çubuğu görünümünüzü döndürür).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
[Menü Komutları](../windows/menu-command-properties.md)<br/>

<!--
[User-Interface Objects and Command IDs](../mfc/user-interface-objects-and-command-ids.md)<br/>
[Menus](../mfc/menus-mfc.md)<br/>
[Menus](https://msdn.microsoft.com/library/windows/desktop/ms646977.aspx)-->