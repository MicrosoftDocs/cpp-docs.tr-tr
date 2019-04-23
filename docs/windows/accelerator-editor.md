---
title: Hızlandırıcı Düzenleyicisi (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.accelerator.F1
- vc.editors.accelerator
helpviewer_keywords:
- accelerator tables [C++], editing
- tables [C++], accelerator key
- accelerator keys [C++]
- resource editors [C++], Accelerator editor
- keyboard shortcuts [C++], Accelerator editor
- accelerator properties
- properties [C++], accelerator properties
- Type property
- Key property
- Modifier property
- VIRTKEY
- Key property
- ID property
- accelerator tables [C++], editing
- keyboard shortcuts [C++], editing in an accelerator table
- searching, in accelarator tables
- accelerator tables [C++], finding entries
- accelerator tables [C++], adding entries
- New Accelerator command
- accelerator tables [C++], deleting entries
- keyboard shortcuts [C++], deleting entry from accelerator table
- accelerator tables [C++], copying entries
- rc files [C++], moving an accelerator table entry
- .rc files [C++], moving accelerator table entries
- accelerator tables [C++], moving entries
- keyboard shortcuts [C++], property changing
- accelerator tables [C++], changing properties
ms.assetid: 013c30b6-5d61-4f1c-acef-8bd15bed7060
ms.openlocfilehash: f5ae9880719a3a8b799ea8deb751b6f0a85542bd
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59041130"
---
# <a name="accelerator-editor-c"></a>Hızlandırıcı Düzenleyicisi (C++)

Hızlandırıcı tablosunu kısayol tuşları, kısayol tuşları ve bunlarla ilişkili komut tanımlayıcıları olarak bilinen bir listesini içeren bir C++ Windows kaynaktır. Bir program, birden fazla Hızlandırıcı tablosu olabilir.

Normalde, Hızlandırıcıları klavye kısayolları da menü veya araç çubuğunda kullanılabilir program komutları için kullanılır. Ancak, Hızlandırıcı tablosu tuş bileşimleri için ilişkili bir kullanıcı arabirimi nesnesi olmayan komutları tanımlamak için kullanabilirsiniz.

> [!TIP]
> Kullanırken **Hızlandırıcı Düzenleyicisi**, sık kullanılan komutları kısayol menüsünü görüntülemek için sağ tıklayın. Kullanılabilir komutlar ne işaretçinin işaret ettiği üzerinde bağlıdır.

Kullanabileceğiniz [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code) kod anahtar komutlarını Hızlandırıcı yeteneklerinizi. Önceden tanımlanmış Hızlandırıcı tuşları listesi için bkz. [kısayol tuşları](../windows/predefined-accelerator-keys.md).

> [!NOTE]
> Windows boş Hızlandırıcı tabloları oluşturmak izin vermez. Hızlandırıcı tablosunu giriş yok oluşturursanız, tabloyu kaydettiğinizde otomatik olarak silinir.

## <a name="accelerator-properties"></a>Hızlandırıcı özellikleri

Hızlandırıcı özelliklerini ayarlayabileceğiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window) dilediğiniz zaman. Ayrıca **Hızlandırıcı Düzenleyicisi** Hızlandırıcı tablosunda Hızlandırıcı özelliklerini değiştirmek için. Kullanılarak yapılan değişiklikleri **özellikleri** penceresi veya **Hızlandırıcı Düzenleyicisi** aynı sonucu, düzenlemeleri Hızlandırıcı tablosunda anında yansıtılır.

**Kimliği** her Hızlandırıcı tablosu girişini program kodunda özelliğine başvuruyor. Bu giriş kullanıcı kısayol tuşunu ya da bir tuş bileşimi bastığında program aldığı komut değerdir. Bir kısayol menü öğesi ile aynı yapmak için olun **kimliği** aynı şekilde sürece **kimliği** Hızlandırıcı tablo aynıdır **kimliği** menü kaynağı için.

Her hızlandırıcının **kimliği** üç özelliğe sahiptir: **Değiştiricisi**, **anahtarı**, ve **türü**

**Değiştiricisi** özelliği denetimi için kısayol tuş birleşimleri ayarlar.

> [!NOTE]
> İçinde **özellikleri** penceresinde **değiştiricisi** özelliği üç ayrı görünür **Boole** özellikler, bunların tümü denetlenebilir bağımsız olarak: **Alt**, **Ctrl**, ve **Shift**.

İçin yasal girdileri verilmiştir **değiştiricisi** Hızlandırıcı tablosu özelliği:

   |Değer|Açıklama|
   |-----------|-----------------|
   |**Yok.**|Kullanıcı yalnızca **anahtar** değeri.<br/><br/>Bu değer en etkili bir şekilde 026 aracılığıyla 001 ASCII/ANSI değerleri olarak yorumlanıp kullanılır ^ A-^ Z (**Ctrl + A** aracılığıyla **Ctrl + Z**).|
   |**Alt**|Kullanıcı gerekir basın **Alt** önce **anahtar** değeri.|
   |**CTRL**|Kullanıcı gerekir basın **Ctrl** önce **anahtar** değer, ASCII türü geçerli değil.|
   |**Kaydırma**|Kullanıcı gerekir basın **Shift** önce **anahtar** değeri.|
   |**Ctrl + Alt**|Kullanıcı gerekir basın **Ctrl** ve **Alt** önce **anahtar** değer, ASCII türü geçerli değil.|
   |**CTRL + üst karakter**|Kullanıcı gerekir basın **Ctrl** ve **Shift** önce **anahtar** değer, ASCII türü geçerli değil.|
   |**Alt + üst karakter**|Kullanıcı gerekir basın **Alt** ve **Shift** önce **anahtar** değer, ASCII türü geçerli değil.|
   |**Ctrl + Alt + üst karakter**|Kullanıcı gerekir basın **Ctrl**, **Alt**, ve **Shift** önce **anahtar** değer, ASCII türü geçerli değil.|

**Anahtar** özelliği Hızlandırıcı olarak kullanılacak gerçek anahtarı ayarlar.

İçin yasal girdileri verilmiştir **anahtar** Hızlandırıcı tablosu özelliği:

   |Değer|Açıklama|
   |-----------|-----------------|
   |0 ve 255 ondalık biçiminde arasında bir tamsayı.|Değer, değer ASCII veya ANSI şu şekilde işlenir olup olmadığını belirler:<br/><br/>   -Tek basamaklı sayı her zaman ASCII veya ANSI değerleri olarak değil, karşılık gelen anahtar olarak yorumlanır.<br/>   -1 ila 26, önünde sıfır ile zaman değerlerini olarak yorumlanır ^ A-^ alfabedeki ile basıldığında ASCII değeri temsil eden Z **Ctrl** tuşu basılı tutularak.<br/>   -27-32 değerlerinden her zaman üç basamaklı ondalık değerler 032 aracılığıyla 027 olarak yorumlanır.<br/>   -033 ile 255'den 0'ın öncesinde ya da ANSI değerleri olarak yorumlanmadı değerleri.|
   |Tek klavye karakter.|A - Z büyük veya 0 - 9 sayılar ASCII veya sanal anahtar değerleri olabilir. Başka bir karakter yalnızca ASCII'dir.|
   |Bir tek klavye karakter aralığı A - Z (büyük yalnızca), örneğin, bir şapka (^) tarafından öncesinde ^ C.|İle basıldığında anahtarın ASCII değeri bu seçeneği girer **Ctrl** tuşu basılı tutularak.|
   |Herhangi bir geçerli sanal anahtar tanımlayıcı.|Aşağı açılan **anahtar** Hızlandırıcı tablo kutusuna standart sanal anahtarı tanımlayıcıları listesini içerir.|

> [!NOTE]
> Bir ASCII değeri girerken **değiştiricisi** özellik seçenekleri sınırlıdır. Yalnızca denetim kullanılabilir için anahtar kullanımı **Alt** anahtarı.

> [!TIP]
> Hızlandırıcı tuşunu tanımlamak için bir kısayol girişi sağ tıklatın ya da Hızlandırıcı Tablo birden çok giriş için ardından **sonraki anahtarı yazılan** ve anahtarları veya tuş birleşimleri klavyede tuşuna basın.
>
> Bu **sonraki anahtarı yazılan** komutu kullanılabilir ayrıca **Düzenle** menüsü.

**Türü** özelliği, kısayol tuş bileşimi Hızlandırıcı ile ilişkili olup olmadığını belirler **kimliği** ASCII/ANSI anahtar değeri veya bir sanal anahtar (VIRTKEY'e) birleşimi olarak yorumlanır.

- Varsa **türü** özelliği **ASCII**, **değiştiricisi** özelliği být pouze parametry `None` veya `Alt`, veya kullananbirHızlandırıcıolabilir**Ctrl** anahtar, anahtar ile önceki tarafından belirtilen bir `^`.

- Varsa **türü** özelliği **VIRTKEY'e**, herhangi bir birleşimini **değiştiricisi** ve **anahtar** değerleri geçerlidir.

> [!NOTE]
> Hızlandırıcı tablosu içine bir değer girin ve kabul ASCII/ANSI, select değerine sahip istiyorsanız **türü** tablosu seçip giriş için **ASCII** aşağı açılan listeden. Ancak, kullanırsanız **sonraki anahtarı yazılan** komutunu **Düzenle** belirtmek için menü **anahtarı**, değiştirmeniz gerekir **türü** özelliği **VIRTKEY'e** için **ASCII** *önce* girme **anahtar** kod.

## <a name="accelerator-tables"></a>Hızlandırıcı tabloları

Bir C++ projesinde, doğrudan yerinde düzenlemeyle Hızlandırıcı tablosunu düzenleyebilirsiniz **Hızlandırıcı Düzenleyicisi**.

Standart özellik sayfalarının kullanımı için aşağıdaki yordamlara bakın, ancak aynı sonucu yerinde düzenleme ve özellik sayfası yöntemi vardır. Özellik sayfaları veya yerinde düzenlemeyi kullanarak yapılan değişiklikler hemen Hızlandırıcı tablosunda yansıtılır.

### <a name="to-edit-in-an-accelerator-table"></a>Hızlandırıcı tablosunu düzenleme

1. Hızlandırıcı tablosu simgeye çift tıklayarak açın [kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources).

1. Bir giriş tablosunda seçin ve yerinde düzenlemeyi etkinleştirmek için seçin.

1. Açılan birleşik giriş kutusundan seçin ya da değişiklik yerinde yazın:

   - İçin **kimliği**listesinden veya düzenlemek için türü seçin.

   - İçin **değiştiricisi**listeden seçin.

   - İçin **anahtar**listesinden veya düzenlemek için türü seçin.

   - İçin **türü**seçin **ASCII** veya **VIRTKEY'e** listeden.

### <a name="to-find-an-entry-in-an-open-accelerator-table"></a>Açık Hızlandırıcı tablosunda giriş aramak için

1. Hızlandırıcı tablosu simgeye çift tıklayarak açın [kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources).

1. Bir sütunun içeriğine alfabetik olarak sıralamak için sütun head seçin. Örneğin, **kimliği** Hızlandırıcı tablonuzdaki tüm kimlikleri alfabetik olarak görüntülenecek.

   Listenin tarama ve girişini bulun.

### <a name="to-add-an-entry-to-an-accelerator-table"></a>Hızlandırıcı tablosunu giriş ekleme

1. Hızlandırıcı tablosu simgeye çift tıklayarak açın [kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources).

1. Hızlandırıcı tablosu içinde sağ tıklatın ve seçin **yeni hızlandırıcı**, veya tablonun alt kısmındaki boş satır girişi seçin.

1. Seçin bir **kimliği** aşağı açılan listeden **kimliği** kutusuna veya yeni bir tür *kimliği* içinde **kimliği** kutusu.

1. Tür *anahtarı* bir Hızlandırıcı olarak kullanmak ya da sağ tıklayın ve istediğiniz **sonraki anahtarı yazılan** bir tuş bileşimini veya menüsüne gidin, **Düzenle**  >  **Asılan sonraki tuş**.

1. Değişiklik **değiştiricisi** ve **türü**, gerekirse basın **Enter**.

> [!NOTE]
> Tanımladığınız tüm Hızlandırıcıları benzersiz olduğundan emin olun. Birkaç tuş bileşimleri aynı Kimliğine sahip hiçbir olumsuz etkisi, örneğin, atanan olabilir **Ctrl**+**P** ve **F8** ID_PRINT için her ikisi de atanabilir. Ancak, birden fazla kimliği çalışmaz, örneğin, atanan bir tuş bileşimi sahip **Ctrl**+**Z** ID_SPELL_CHECK ve ID_THESAURUS atanmış.

### <a name="to-delete-an-entry-from-an-accelerator-table"></a>Hızlandırıcı tablosundan giriş silme

1. Hızlandırıcı tablosu simgeye çift tıklayarak açın [kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources).

1. Silme veya basılı girişi seçin **Ctrl** veya **Shift** birden çok girişi seçmek için seçme tuşunu.

1. Sağ tıklatın ve seçin **Sil**, veya menüsüne gidin **Düzenle** > **Sil**.

> [!TIP]
> Ayrıca basabilirsiniz **Sil** anahtarı silinemedi.

### <a name="to-move-or-copy-an-accelerator-table-entry-to-another-resource-script-file"></a>Hızlandırıcı tablosu girişini başka bir kaynak betik dosyasına taşınacak veya kopyalanacak

1. Hızlandırıcı tablolarını hem kaynak kod dosyalarını açın ve taşımak istediğiniz girişini seçin.

1. Gelen **Düzenle** menüsünde seçin **kopyalama** veya **Kes**.

1. Hedef kaynak betik dosyasında ve bir giriş seçin **Düzenle** menüsünde seçin **Yapıştır**.

> [!NOTE]
> Ayrıca, kopyalama ve yapıştırma için kısayol tuşlarını kullanabilirsiniz.

### <a name="to-change-the-properties-of-multiple-accelerator-keys"></a>Birden çok hızlandırma tuşunun özelliklerini değiştirme

1. Hızlandırıcı tablosu simgeye çift tıklayarak açın [kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources).

1. Hızlandırıcı tuşları basılı tutarak değiştirmek istediğiniz seçin **Ctrl** anahtar her birini seçin.

1. Git [Özellikler penceresi](/visualstudio/ide/reference/properties-window) tüm paylaşmak için seçilen Hızlandırıcılar istediğiniz değerleri yazın.

> [!NOTE]
> Her değiştiricisi değer bir Boolean özelliği olarak görünür **özellikleri** penceresi. Değiştirirseniz bir [değiştiricisi](../windows/accelerator-modifier-property.md) değerini **özellikleri** penceresinde Hızlandırıcı tablosunu işler yeni değiştiricisini ek olarak, önceden var olan tüm değiştiriciler. Herhangi bir değiştirici değeri ayarlarsanız, bu nedenle, her hızlandırıcının aynı paylaşımları sağlamak için bunların tümünü ayarlamak ihtiyacınız olacak **değiştiricisi** ayarları.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
[Hızlandırıcı Tuşları](../windows/predefined-accelerator-keys.md)<br/>