---
title: Menü komutları (C++)
ms.date: 02/15/2019
helpviewer_keywords:
- menu items, properties
- keyboard shortcuts [C++], menu association
- commands [C++], associating menu commands with accelerator keys
- menu commands [C++], associating with keyboard shortcuts
- status bars [C++], associating menu items
- menus [C++], status bar text
- access keys [C++], checking
- menus [C++], shortcut keys
- keyboard shortcuts [C++], command assignments
- access keys [C++], assigning
- mnemonics [C++], adding to menus
- keyboard shortcuts [C++], uniqueness checking
- mnemonics [C++], uniqueness checking
- Check Mnemonics command
ms.assetid: 6d308205-3c9e-42f2-ab42-45e656940e45
ms.openlocfilehash: 972478923a7c4c60d8ff949c5532b00a1de1efc0
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80075497"
---
# <a name="menu-commands-c"></a>Menü komutları (C++)

Aşağıdaki bilgiler, bir menü komutu seçtiğinizde [Özellikler penceresinde](/visualstudio/ide/reference/properties-window) görünen **menü** özelliklerine göre düzenlenmiştir. Bunlar alfabetik olarak listelenir, ancak **Özellikler** penceresi ayrıca bu özellikleri kategoriye göre görüntülemenize olanak sağlar.

|Özellik|Açıklama|
|--------------|-----------------|
|**Sonundan**|Şu değerlerden biri olabilir:<br/>  **None**- : kesme yok. Bu varsayılandır.<br/>  - **sütunu**: statik menüler için, bu değer menü komutunu yeni bir satıra koyar.<br/>      Açılır menülerde, bu değer menü komutunu sütunlar arasında bölme olmadan yeni bir sütuna koyar.<br/>      Bu özellik ayarlandığında menü düzenleyicisinde değil, yalnızca çalışma zamanında menü görünümü etkilenir.<br />   - **çubuğu**: **sütun** ile aynı, ancak açılan menüler için, bu değer yeni sütunu eski sütundan dikey bir satırla ayırır.<br/>      Bu özellik ayarlandığında menü **düzenleyicisinde**değil, yalnızca çalışma zamanında menü görünümü etkilenir.|
|**Başlığını**|Menü komutunun etiketlediği metin (menü adı). Bir menü komutunun resim yazısından birini, anımsatıcı anahtarı olacak şekilde, bir ve işareti (&) ile önüne alın.|
|**Edildikten**|**True**ise, menü komutu başlangıçta denetlenir. Tür: **bool**. Varsayılan: **false**.|
|**Etkin**|**False**ise, menü öğesi devre dışıdır.|
|**Gri**|**Doğru**ise, menü komutu başlangıçta gridir ve etkin değildir. Tür: **bool**. Varsayılan: **false**.|
|**Yardım**|Menü öğesini sağa hizalar. Varsayılan: **false**.<br/><br/>Örneğin, **Yardım** menüsü komutu her zaman tüm Windows uygulamalarında sağ tarafta bulunur. Bu özelliği bir menü öğesinde ayarlarsanız, bu öğe en sağda ve menünün en sonunda görüntülenir. Üst düzey öğeler için geçerlidir.|
|**ID**|Üst bilgi dosyasında tanımlanan bir simge. Tür: **symbol**, **Integer**veya **tırnaklı dize**.<br/><br/>[Özellikler penceresi](/visualstudio/ide/reference/properties-window) seçim yapmanız için bir açılır liste sağlamasa bile, düzenleyicilerin herhangi birinde yaygın olarak kullanılabilen herhangi bir sembolü kullanabilirsiniz.|
|**Açılan Pencere**|**True**ise menü komutu bir açılır menü olur. Tür: **bool**. Varsayılan: bir menü çubuğundaki en üst düzey menüler için **true** , aksi durumda **false**.|
|**İsteme**|Bu menü komutu vurgulandığında durum çubuğunda görünecek metni içerir. Metin, menü komutuyla aynı tanımlayıcıya sahip dize tablosuna yerleştirilir.<br/><br/>Bu özellik her proje türü için kullanılabilir, ancak çalışma zamanı işlevselliği MFC 'ye özgüdür.|
|**Sağdan Sola Yasla**|Çalışma zamanında menü çubuğunda menü komutunu sağa yaslar. Tür: **bool**. Varsayılan: **false**.|
|**Sağdan sola düzen**|Arabirim, Ibranice veya Arapça gibi sağdan sola okuyan herhangi bir dile yerelleştirildiği zaman menü komutlarının sağdan sola görüntülemesine olanak tanır.|
|**Ayıraç**|**True**ise menü komutu bir ayırıcıdır. Tür: **bool**. Varsayılan: **false**.|

## <a name="associate-menu-commands"></a>Menü komutlarını ilişkilendir

Bir menü komutunun ve klavye bileşiminin aynı program komutunu vermesini sağlamak için genellikle birkaç zaman vardır. Aynı komutlar menü komutuna ve uygulamanızın Hızlandırıcı tablosundaki bir girdiye aynı kaynak tanımlayıcısını atamak için **Menü Düzenleyicisi** kullanılarak verilir. Ardından, kısayol tuşunun adını göstermek için menü komutunun [başlığını](../windows/menu-command-properties.md) düzenlersiniz.

### <a name="to-associate-a-menu-command-with-an-accelerator-key"></a>Bir menü komutunu Hızlandırıcı anahtarıyla ilişkilendirmek için

1. **Menü düzenleyicisinde**istediğiniz menü komutunu seçin.

1. [Özellikler penceresinde](/visualstudio/ide/reference/properties-window), kısayol tuşunun adını **Caption** özelliğine ekleyin:

   - Menü başlığını takip eden bir sekme (\t) için kaçış sırası yazın, böylece tüm menü kısayol tuşlarının sola hizalı olmasını sağlayabilirsiniz.

   - Değiştirici anahtarın adını (**CTRL**, **alt**veya **SHIFT**), ardından artı işareti ( **+** ) ve ek anahtarın adı, harfi veya sembolünü yazın.

   Örneğin, **Dosya** menüsündeki **aç** komutuna **CTRL**+**O** atamak için, menü komutunun **başlığını** aşağıdaki metin gibi görünecek şekilde değiştirirsiniz:

   ```
   &Open...\tCtrl+O
   ```

   **Menü düzenleyicisinde** menü komutu, yazarken yeni açıklamalı alt yazıyı yansıtacak şekilde güncelleştirilir.

1. **Hızlandırıcı Düzenleyicisi 'nde** [Hızlandırıcı-tablosu girişini oluşturun](../windows/adding-an-entry-to-an-accelerator-table.md) ve menü komutuyla aynı tanımlayıcıya atayın. Anımsanması kolay olacağını düşündüğünüz bir tuş birleşimini kullanın.

MFC uygulamanız, bir kullanıcının seçebileceğiniz her bir menü komutu için açıklayıcı metin gösterebilir. **Özellikler** penceresindeki **Prompt** özelliğini kullanarak her menü komutuna bir metin dizesi atayarak açıklayıcı metni görüntüleyin. [Dize tablosunda](../windows/string-editor.md) , kimliği komutla aynı olan bir dizeniz varsa, bir Kullanıcı bir menü öğesinin üzerine geldiğinde, bir MFC uygulaması, çalışan uygulamanın durum çubuğunda Bu dize kaynağını otomatik olarak görüntüler.

- Bir menü komutunu MFC uygulamalarında bir durum çubuğu metin dizesiyle ilişkilendirmek için, menü **düzenleyicisinde**menü komutunu seçin. [Özellikler penceresinde](/visualstudio/ide/reference/properties-window), **istem** kutusuna ilişkili durum çubuğu metnini yazın.

Bir C++ projede, menüler ve menü komutlarınızda bir erişim anahtarı (kullanıcının klavye ile menüyü seçmesini sağlayan bir anımsatıcı) atayabilirsiniz.

- Bir menü komutuna bir erişim (kısayol) anahtarı atamak için, ilgili erişim anahtarı olarak bu harfi belirtmek üzere menü adı veya komut adındaki bir harfin önüne bir ampersan (`&`) yazın.

   Örneğin, "& File" **Alt**+**F** 'yi Microsoft Windows için yazılmış uygulamalardaki **Dosya** menüsünün kısayol tuşu olarak ayarlar.

   Menü öğesi, mektuplardan birine atanmış kısayol tuşuna sahip olan görünür bir ipucu sağlar. Ve işaretini izleyen harf altı çizili olarak görünür (işletim sisteminde çalışır).

> [!NOTE]
> Menüdeki tüm erişim anahtarlarının benzersiz olduğundan emin olun ve menü için sağ tıklayıp **anımsatıcıları denetle**' yi seçin.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Menü Düzenleyicisi](../windows/menu-editor.md)

<!--
[Strings (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>-->