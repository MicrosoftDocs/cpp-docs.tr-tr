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
ms.openlocfilehash: a21ff3ba736bd345e4b8399a761b5a8d9db531ac
ms.sourcegitcommit: 9aab425662a66825772f091112986952f341f7c8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72444979"
---
# <a name="menu-editor-c"></a>Menü Düzenleyicisi (C++)

Menüler, komutları mantıksal ve kolay bir biçimde düzenlemenizi sağlar. **Menü Düzenleyicisi**ile, tamamlanmış uygulamanızdaki bir menü çubuğuyla doğrudan birlikte çalışarak menü oluşturabilir ve düzenleyebilirsiniz.

> [!TIP]
> Birçok örnekte **menü düzenleyicisini**kullanırken, sık kullanılan komutların açılır menüsünü göstermek için sağ tıklayabilirsiniz. Kullanılabilir komutlar, işaretçinin işaret ettiği işe bağlıdır.

## <a name="how-to"></a>Nasıl Yapılır

**Menü Düzenleyicisi** şunları yapmanızı mümkün:

### <a name="to-create-a-standard-menu"></a>Standart bir menü oluşturmak için

1. Menü '  > **diğer Windows** > **kaynak görünümü** **görüntüleyin**ve **menü** başlığına sağ tıklayın. **Kaynak Ekle**' yi ve ardından **menüyü**seçin.

1. Menü çubuğunda **Yeni öğe** kutusunu ( *burada türü*içeren dikdörtgen) seçin.

   ![Menü düzenleyicisinde yeni öğe kutusu](../windows/media/vcmenueditornewitembox.gif "vcMenuEditorNewItemBox")<br/>
   **Yeni öğe** kutusu

1. Yeni menünüzün adını (örneğin, *dosyası*) yazın.

   Yazdığınız metin, hem **menü düzenleyicisinde** hem de [Özellikler penceresindeki](/visualstudio/ide/reference/properties-window) **başlık** kutusunda görünür. Yeni menünüzün özelliklerini her iki konumdan de düzenleyebilirsiniz.

   Yeni menünüzün menü çubuğunda bir adı verildikten sonra, yeni öğe kutusu sağa kayar (başka bir menü eklemenize izin vermek için) ve buna menü komutları ekleyebilmek için ilk menünün altında başka bir yeni öğe kutusu açılır.

   ![Genişletilmiş yeni öğe kutusu](../windows/media/vcmenueditornewitemboxexpanded.gif "Vcmenueditornewwitemboxgenişletilen")<br/>
   Menü adı yazdıktan sonra odak kaydırılan **Yeni öğe** kutusu

   > [!NOTE]
   > Menü çubuğunda tek bir öğe menüsü oluşturmak için, **açılan** özelliğini **false**olarak ayarlayın.

### <a name="to-create-a-submenu"></a>Bir alt menü oluşturmak için

1. Alt menü oluşturmak istediğiniz menü komutunu seçin.

1. Sağ tarafta görünen **Yeni öğe** kutusunda yeni menü komutunun adını yazın. Bu yeni komut alt menü menüsünde ilk olarak görünür.

1. Alt menü menüsüne ek menü komutları ekleyin.

### <a name="to-insert-a-new-menu-between-existing-menus"></a>Varolan menüler arasında yeni bir menü eklemek için

Mevcut bir menü adı seçin ve **Ekle** tuşuna basın veya menü çubuğuna sağ tıklayıp **Yeni Ekle**' yi seçin.

   **Yeni öğe** kutusu seçili öğeden önce eklenir.

### <a name="to-add-commands-to-a-menu"></a>Menüye komut eklemek için

1. Bir menü oluşturun. Sonra bir menü adı (örneğin, **Dosya**) seçin.

   Her menü, komutlar için yeni bir öğe kutusu genişletir ve kullanıma sunar. Örneğin, **Yeni**, **Açık**ve **kapalı** komutlarını bir **Dosya** menüsüne ekleyebilirsiniz.

1. Yeni öğe kutusuna yeni menü komutu için bir ad yazın.

   > [!NOTE]
   > Yazdığınız metin, hem **menü düzenleyicisinde** hem de [Özellikler penceresindeki](/visualstudio/ide/reference/properties-window) **başlık** kutusunda görünür. Yeni menünüzün özelliklerini her iki konumdan de düzenleyebilirsiniz.

   > [!TIP]
   > Kullanıcının menü komutunu seçmesini sağlayan bir anımsatıcı anahtar (kısayol tuşu) tanımlayabilirsiniz. Anımsatıcı olarak belirtmek için bir harfin önüne bir ampersan (`&`) yazın. Kullanıcı bu harfi yazarak menü komutunu seçebilir.

1. **Özellikler** penceresinde, uygulanan menü komutu özelliklerini seçin. Ayrıntılar için bkz. [menü komut özellikleri](../windows/menu-command-properties.md).

1. **Özellikler** penceresindeki **istem** kutusuna uygulamanızın durum çubuğunda görünmesini istediğiniz istem dizesini yazın.

   Bu adım, oluşturduğunuz menü komutuyla aynı kaynak tanımlayıcısına sahip dize tablosunda bir giriş oluşturur.

   > [!NOTE]
   > İstemler yalnızca bir **Popup** özelliği **true**olan menü öğelerine uygulanabilir. Örneğin, üst düzey menü öğeleri, alt menü öğelerine sahip olmaları durumunda istemlere sahip olabilir. Bir **istem** amacı, bir Kullanıcı menü öğesini seçerse ne olacağını belirtsağlamaktır.

1. Menü komutunu doldurmak için **ENTER** tuşuna basın.

   Ek menü komutları oluşturabilmeniz için yeni öğe kutusu seçilidir.

### <a name="to-select-multiple-menu-commands-to-run-bulk-operations-such-as-deleting-or-changing-properties"></a>Özellikleri silme veya değiştirme gibi toplu işlemleri çalıştırmak için birden çok menü komutu seçmek için

**CTRL** tuşunu basılı tutarken istediğiniz menüleri veya alt menü komutlarını seçin.

### <a name="to-move-and-copy-menus-and-menu-commands"></a>Menüleri ve menü komutlarını taşımak ve kopyalamak için

- Sürükle ve bırak yöntemini kullanın:

   1. Taşımak istediğiniz öğeyi sürükleyin veya kopyalayın:

      - Geçerli menüdeki yeni bir konum.

      - Farklı bir menü. Fare işaretçisini üzerlerine sürükleyerek diğer menülere gidebilirsiniz.

   1. Ekleme kılavuzu istediğiniz konumu gösterdiğinde menü komutunu bırakın.

- Kısayol menü komutlarını kullan:

   1. Bir veya daha fazla menü ya da menü komutlarına sağ tıklayın, sonra **Kes** (taşımak için) veya **Kopyala**' yı seçin.

   1. Öğeleri başka bir menü kaynağına veya kaynak betik dosyasına taşıyorsanız, [başka bir pencerede açın](/visualstudio/ide/customizing-window-layouts-in-visual-studio).

   1. Taşımak veya kopyalamak istediğiniz menünün veya menü komutunun konumunu seçin.

   1. Kısayol menüsünden **Yapıştır**' ı seçin. Taşınan veya kopyalanmış öğe, seçtiğiniz öğeden önce yerleştirilir.

> [!NOTE]
> Ayrıca diğer menü pencerelerinin içindeki diğer menülere da sürükleyip yapıştırabilirsiniz.

### <a name="to-delete-a-menu-or-menu-command"></a>Menüyü veya menü komutunu silmek için

Menü adına veya komutuna sağ tıklayın ve **Sil**' i seçin.

> [!NOTE]
> Benzer şekilde, kopyalama, kesme, yapıştırma, yeni ekleme, ayırıcı ekleme, kimlikleri düzenleme, açılır pencere, denetim anımsatıcıları vb. gibi diğer eylemleri gerçekleştirmek için kısayol menüsünü kullanabilirsiniz.

## <a name="pop-up-menus"></a>Açılır menüler

[Açılır menüler](../mfc/menus-mfc.md) sık kullanılan komutları görüntüler. Bu, işaretçinin konumuyla hassas içeriğe sahip olabilirler. Uygulamanızdaki açılır menülerin kullanılması, menünün kendisini oluşturmayı ve sonra uygulama koduna bağlamayı gerektirir.

Menü kaynağını oluşturduktan sonra, uygulama kodunuzun menü kaynağını yüklemesi ve menünün görünmesine neden olacak [TrackPopupMenu](/windows/win32/api/winuser/nf-winuser-trackpopupmenu) kullanması gerekir. Kullanıcı açılan menüyü dışarıda bırak seçeneğini belirlediğinizde veya bir komut seçtikten sonra, bu işlev döndürür. Kullanıcı bir komut seçerse, bu komut iletisi tutamacı geçilen pencereye gönderilir.

> [!NOTE]
> Microsoft Foundation Class (MFC) kitaplık programları ve ATL programları için kod **sihirbazları** 'nı kullanarak kod için menü komutlarını kullanın. Daha fazla bilgi için bkz. [bir olay ekleme](../ide/adding-an-event-visual-cpp.md) ve [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md).

- Bir açılır menü oluşturmak için, boş başlıklı *ve başlık sağlamayan*bir menü oluşturun. Ardından, yeni menüye bir menü komutu ekleyin, burada geçici açıklamalı alt yazı *tipinde* boş menü başlığının altındaki ilk menü komutuna gidin ve bir *başlık* ve diğer bilgileri yazın.

   Açılır menüdeki diğer menü komutları için bu işlemi tekrarlayın ve menü kaynağını kaydettiğinizden emin olun.

- Uygulamanıza bir açılır menü bağlamak için örneğin, WM_CONTEXTMENU için bir ileti işleyicisi ekleyin ve ileti işleyicisine aşağıdaki kodu ekleyin:

    ```cpp
    CMenu menu;
    VERIFY(menu.LoadMenu(IDR_MENU1));
    CMenu* pPopup = menu.GetSubMenu(0);
    ASSERT(pPopup != NULL);
    pPopup->TrackPopupMenu(TPM_LEFTALIGN | TPM_RIGHTBUTTON, point.x, point.y, AfxGetMainWnd());
    ```

   > [!NOTE]
   > İleti işleyicisi tarafından geçilen [CPoint](../atl-mfc-shared/reference/cpoint-class.md) , Ekran koordinatlarında.

Normalde, **menü düzenleyicisinde**çalışırken bir menü kaynağı bir menü çubuğu olarak görüntülenir. Ancak, program çalışırken uygulamanın menü çubuğuna eklenen menü kaynaklarına sahip olabilirsiniz.

- Bir menü kaynağını açılan menü olarak görüntülemek için, menüye sağ tıklayıp **açılan pencere olarak görüntüle**' yi seçin.

   Bu seçenek yalnızca bir görüntüleme tercihine sahiptir ve menü dosyanızı değiştirmez.

> [!TIP]
> Menü çubuğu görünümüne geri dönmek için, **açılan pencereyi yeniden göster** ' i seçin. Bu eylem onay işaretini kaldırır ve menü çubuğu görünümünüzü geri döndürür.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
[Menü Komutları](../windows/menu-command-properties.md)<br/>
[Kullanıcı Arabirimi Nesneleri ve Komut Kimlikleri](../mfc/user-interface-objects-and-command-ids.md)<br/>
[Menüler](../mfc/menus-mfc.md)<br/>
[Menüler](/windows/win32/menurc/menus)