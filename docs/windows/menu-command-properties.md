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
ms.openlocfilehash: c9abf46907c473d4cf6d9e945038f70aa75bfc48
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59026285"
---
# <a name="menu-commands-c"></a>Menü komutları (C++)

Aşağıdaki bilgilere göre düzenlenmiş **menü** görünen Özellikler [Özellikler penceresi](/visualstudio/ide/reference/properties-window) seçtiğinizde bir menü komutu. Bu rağmen alfabetik olarak listelenen **özellikleri** pencere Ayrıca bu özellikleri kategoriye göre görüntüle olanak sağlar.

|Özellik|Açıklama|
|--------------|-----------------|
|**sonu**|Şu değerlerden biri olabilir:<br/>  - **Hiçbiri**: Kesme yok. Bu varsayılandır.<br/>  - **Sütun**: Statik menüleri için bu değer, yeni bir satıra menü komutunu yerleştirir.<br/>      Açılır menüler için bu değeri hiçbir sütunları arasındaki çizgi ile yeni bir sütun menü komutunu yerleştirir.<br/>      Bu özelliğin ayarlanması menü görünümünü yalnızca çalışma zamanında, menü Düzenleyicisi'nde etkiler.<br />   - **Çubuk**: Aynı **sütun** dışında açılır menüler için bu değeri yeni bir sütun içeren bir dikey çizgi eski sütunu ayırır.<br/>      Bu özelliğin ayarlanması etkiler menü görünümünü yalnızca çalışma zamanında değil **Menü Düzenleyici**.|
|**Başlık**|Menü komutunu (menü adı) etiket metni. Bir harf menüsünün açıklamasındaki kısayol tuşu komutu, bir ampersan ile önünde olmak için (&).|
|**İşaretli**|Varsa **True**, menü komutunu başlangıçta denetlenir. Tür: **bool**. Varsayılan: **False**.|
|**Etkin**|Varsa **False**, menü öğesi devre dışı bırakıldı.|
|**Gri**|Varsa **True**, başlangıçta gri ve etkin olmayan menü komutu. Tür: **bool**. Varsayılan: **False**.|
|**Yardım**|Menü öğesi sağa hizalar. Varsayılan: **False**.<br/><br/>Örneğin, **yardımcı** menü komutu olduğundan her zaman, tüm Windows uygulamalarını sağdaki. Bir menü öğesi bu özelliği ayarlarsanız, bu öğe en çok sağdaki ve menüsünün en sonunda görünür. Üst düzey öğeleri için geçerlidir.|
|**Kimlik**|Üst bilgi dosyasında tanımlanan bir simge. Tür: **Sembol**, **tamsayı**, veya **sınırlandırılmış**.<br/><br/>Yaygın olarak kullanılabilen düzenleyicileri hiçbirinde olsa bile herhangi bir simge kullanabilir [Özellikler penceresi](/visualstudio/ide/reference/properties-window) arasından seçim yapabileceğiniz bir açılan liste sağlamaz.|
|**Açılan Pencere**|Varsa **True**, açılır menü menü komutudur. Tür: **bool**. Varsayılan: **Doğru** değilse, menü çubuğunda en üst düzey menüler için **False**.|
|**İstem**|Bu menü komutu vurgulandığında durum çubuğunda görüntülenecek metni içerir. Menü komutu ile aynı tanımlayıcıyla dize tablosunda metin yerleştirilir.<br/><br/>Bu özellik, her türden proje için kullanılabilir, ancak MFC belirli çalışma zamanı işlevdir.|
|**Sağdan Sola Yasla**|Sağa hizalar çalışma zamanında menü çubuğundaki menü komutu. Tür: **bool**. Varsayılan: **False**.|
|**Sağa sola düzeni için**|Sağ İbranice ve Arapça gibi sola, okuyan herhangi bir dil için yerelleştirilmiş arabirim sağdan sola görüntülemek, menü komutlarını sağlar.|
|**Ayırıcı**|Varsa **True**, menü komutunu olduğu bir ayırıcı. Tür: **bool**. Varsayılan: **False**.|

## <a name="associate-menu-commands"></a>İlişkilendirme menü komutları

Genellikle bir menü komutu ve klavye birleşimi aynı program komutu vermek istediğiniz durumlar da vardır. Aynı komutları kullanarak yayımlanan **Menü Düzenleyici** menü komutunu ve uygulamanızın Hızlandırıcı tablosunda bir giriş için aynı kaynak tanımlayıcısı atamak için. Ardından Düzenle [açıklamalı alt yazı](../windows/menu-command-properties.md) kısayol tuşunu adını göstermek için menü komutu.

### <a name="to-associate-a-menu-command-with-an-accelerator-key"></a>Bir menü komutunu Hızlandırıcı tuşuyla ilişkilendirme

1. İçinde **Menü Düzenleyici**, istediğiniz komutu seçin.

1. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), hızlandırıcı anahtarı adını eklemek **açıklamalı alt yazı** özelliği:

   - Menü başlığı tüm menünün kısayol tuşları sola hizalanmış bir sekme (\t) kaçış sırası yazın.

   - Değiştirici tuş adını yazın (**Ctrl**, **Alt**, veya **Shift**) ve ardından bir artı işareti (**+**) ve ad, harf, veya İlave bir anahtar simgesi.

   Örneğin, atama için **Ctrl**+**O** için **açık** komutunu **dosya** menüsünde, menü komutunun değiştirme **Açıklamalı alt yazı** böylece şu metin gibi görünür:

   ```
   &Open...\tCtrl+O
   ```

   Menü komutunu **Menü Düzenleyici** siz yazarken yeni başlığı yansıtacak şekilde güncelleştirilir.

1. [Hızlandırıcı tablosu girişi oluşturmak](../windows/adding-an-entry-to-an-accelerator-table.md) içinde **hızlandırıcı** Düzenleyicisi ve menü komutunu aynı tanımlayıcıyı atayın. Kolay olacağını düşündüğünüz bir tuş bileşimini kullanın.

MFC uygulamanızı her bir kullanıcı seçebilir menü komutları için açıklayıcı metni görüntüleyebilirsiniz. Bir metin dizesi kullanarak her menü komut atayarak açıklayıcı metni görüntüler **istemi** özelliğinde **özellikleri** penceresi. Bir dize varsa [dize tablosu](../windows/string-editor.md) Kimliğine komutu ile aynıdır, bir kullanıcı bir menü öğesi geldiğinde bir MFC uygulaması otomatik olarak bu dize kaynağı çalışan uygulama durum çubuğunda görüntülenir.

- Bir menü komutu bir durum çubuğu MFC uygulamalarında, metin dizesi olarak ilişkilendirmek için **Menü Düzenleyici**, menü komutunu seçin. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), ilgili durum çubuğu metni yazın **istemi** kutusu.

Bir C++ projesinde, menüleri ve menü komutlarını, bir erişim anahtarı (kullanıcının klavye menüsüyle seçmesine izin veren bir anımsatıcı) atayabilirsiniz.

- Bir menü komutu için bir erişim (kısayol) anahtarı atamak, ve işareti yazın (`&`) menüsü adı veya harf karşılık gelen erişim anahtarı olarak belirtmek için komut adı bir harf önünde. 

   Örneğin, "& dosya" kümeleri **Alt**+**F** için kısayol tuşu **dosya** menüsünde Microsoft Windows için yazılmış uygulamalar için.

   Menü öğesi bir harf kendisine atanmış bir kısayol tuşuna sahip görünür bir ipucu sağlar. Ve işareti görünür harf aşağıdaki altı çizili (işletim sistemi topolojideki).

> [!NOTE]
> Menünüzde sağ tıklayıp seçerek menüsündeki tüm erişim anahtarlarını benzersiz olduğundan emin olun **anımsatıcıları kontrol**.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Menü Düzenleyicisi](../windows/menu-editor.md)<br/>

<!--
[Strings (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>-->