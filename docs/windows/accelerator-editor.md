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
ms.openlocfilehash: 21f588f6103195d9fe977d0b019b911b33f43105
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57210841"
---
# <a name="accelerator-editor-c"></a>Hızlandırıcı Düzenleyicisi (C++)

Hızlandırıcı tablosunu hızlandırma tuşları (kısayol tuşları olarak da bilinir) bir listesini içeren bir C++ Windows kaynak ve bunlarla ilişkili komut tanımlayıcıları ' dir. Bir program, birden fazla Hızlandırıcı tablosu olabilir.

Normalde, Hızlandırıcıları klavye kısayolları da menü veya araç çubuğunda kullanılabilir program komutları için kullanılır. Ancak, Hızlandırıcı tablosu tuş bileşimleri için ilişkili bir kullanıcı arabirimi nesnesi olmayan komutları tanımlamak için kullanabilirsiniz.

Kullanabileceğiniz [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code) kod anahtar komutlarını Hızlandırıcı yeteneklerinizi.

Önceden tanımlanmış Hızlandırıcı tuşları listesi için bkz. [kısayol tuşları](../windows/predefined-accelerator-keys.md).

> [!TIP]
> Kullanırken **Hızlandırıcı Düzenleyicisi**, sık kullanılan komutları kısayol menüsünü görüntülemek için sağ tıklayın. Kullanılabilir komutlar ne işaretçinin işaret ettiği üzerinde bağlıdır.

> [!NOTE]
> Windows boş Hızlandırıcı tabloları oluşturmak izin vermez. Hızlandırıcı tablosunu giriş yok oluşturursanız, tabloyu kaydettiğinizde otomatik olarak silinir.

## <a name="accelerator-properties"></a>Hızlandırıcı özellikleri

Hızlandırıcı özelliklerini ayarlayabileceğiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window) dilediğiniz zaman. Ayrıca **Hızlandırıcı Düzenleyicisi** Hızlandırıcı tablosunda Hızlandırıcı özelliklerini değiştirmek için. Kullanılarak yapılan değişiklikleri **özellikleri** penceresi veya **Hızlandırıcı Düzenleyicisi** aynı sonucu, düzenlemeleri Hızlandırıcı tablosunda anında yansıtılır.

### <a name="id-property"></a>ID Özelliği

**Kimliği** her Hızlandırıcı tablosu girişini program kodunda özelliğine başvuruyor. Bu giriş kullanıcı kısayol tuşunu ya da bir tuş bileşimi bastığında program aldığı komut değerdir. Bir kısayol menü öğesi ile aynı yapmak için olun, **kimliği** aynı şekilde sürece **kimliği** Hızlandırıcı tablo aynıdır **kimliği** menü kaynağı için.

Her hızlandırıcının için üç özellik **kimliği**: **Değiştiricisi**, **anahtarı**, ve **türü**

#### <a name="modifier-property"></a>Değiştirici özelliği

**Değiştiricisi** özelliği denetimi için kısayol tuş birleşimleri ayarlar.

> [!NOTE]
> İçinde **özellikleri** penceresinde **değiştiricisi** özelliği üç ayrı görünür **Boole** özellikler, bunların tümü denetlenebilir bağımsız olarak: **Alt**, **Ctrl**, ve **Shift**.

İçin yasal girdileri verilmiştir **değiştiricisi** Hızlandırıcı tablosu özelliği:

   |Değer|Açıklama|
   |-----------|-----------------|
   |**Yok.**|Kullanıcı yalnızca **anahtar** değeri. Bu değer en etkili bir şekilde 026 aracılığıyla 001 ASCII/ANSI değerleri olarak yorumlanıp kullanılır ^ A-^ Z (**Ctrl + A** aracılığıyla **Ctrl + Z**).|
   |**Alt**|Kullanıcı gerekir basın **Alt** önce **anahtar** değeri.|
   |**CTRL**|Kullanıcı gerekir basın **Ctrl** önce **anahtar** değeri. ASCII türü geçerli değil.|
   |**Kaydırma**|Kullanıcı gerekir basın **Shift** önce **anahtar** değeri.|
   |**Ctrl + Alt**|Kullanıcı gerekir basın **Ctrl** ve **Alt** önce **anahtar** değeri. ASCII türü geçerli değil.|
   |**CTRL + üst karakter**|Kullanıcı gerekir basın **Ctrl** ve **Shift** önce **anahtar** değeri. ASCII türü geçerli değil.|
   |**Alt + üst karakter**|Kullanıcı gerekir basın **Alt** ve **Shift** önce **anahtar** değeri. ASCII türü geçerli değil.|
   |**Ctrl + Alt + üst karakter**|Kullanıcı gerekir basın **Ctrl**, **Alt**, ve **Shift** önce **anahtar** değeri. ASCII türü geçerli değil.|

#### <a name="key-property"></a>Anahtar özelliği

**Anahtar** özelliği Hızlandırıcı olarak kullanılacak gerçek anahtarı ayarlar.

İçin yasal girdileri verilmiştir **anahtar** Hızlandırıcı tablosu özelliği:

   |Değer|Açıklama|
   |-----------|-----------------|
   |0 ve 255 ondalık biçiminde arasında bir tamsayı.|Değer, değer ASCII veya ANSI şu şekilde işlenir olup olmadığını belirler:<br/><br/>   -Tek basamaklı sayı her zaman ASCII veya ANSI değerleri olarak değil, karşılık gelen anahtar olarak yorumlanır.<br/>   -1 ila 26, önünde sıfır ile zaman değerlerini olarak yorumlanır ^ A-^ alfabedeki ile basıldığında ASCII değeri temsil eden Z **Ctrl** tuşu basılı tutularak.<br/>   -27-32 değerlerinden her zaman üç basamaklı ondalık değerler 032 aracılığıyla 027 olarak yorumlanır.<br/>   -033 ile 255'den 0'ın öncesinde ya da ANSI değerleri olarak yorumlanmadı değerleri.|
   |Tek klavye karakter.|A - Z büyük veya 0 - 9 sayılar ASCII veya sanal anahtar değerleri olabilir. Başka bir karakter yalnızca ASCII'dir.|
   |Bir tek klavye karakter aralığı A - Z (büyük yalnızca), öncesinde bir şapka (^).<br/><br/>Örneğin, ^ C.|İle basıldığında anahtarın ASCII değeri bu seçeneği girer **Ctrl** tuşu basılı tutularak.|
   |Herhangi bir geçerli sanal anahtar tanımlayıcı.|Aşağı açılan **anahtar** Hızlandırıcı tablo kutusuna standart sanal anahtarı tanımlayıcıları listesini içerir.|

> [!NOTE]
> Bir ASCII değeri girerken **değiştiricisi** özellik seçenekleri sınırlıdır. Yalnızca denetim kullanılabilir için anahtar kullanımı **Alt** anahtarı.

> [!TIP]
> Hızlandırıcı tuşunu tanımlamak için bir kısayol Hızlandırıcı tablosunda birden çok girişlere sağ sağlamaktır. Seçin **sonraki anahtarı yazılan** ve anahtarları veya tuş birleşimleri klavyede tuşuna basın.
>
> **Sonraki anahtarı yazılan** komutu kullanılabilir ayrıca **Düzenle** menüsü.

#### <a name="type-property"></a>Özellik türü

**Türü** özelliği, kısayol tuş bileşimi Hızlandırıcı ile ilişkili olup olmadığını belirler **kimliği** ASCII/ANSI anahtar değeri veya bir sanal anahtar (VIRTKEY'e) birleşimi olarak yorumlanır.

- Varsa **türü** özelliği **ASCII**, **değiştiricisi** özelliği být pouze parametry `None` veya `Alt`, veya kullananbirHızlandırıcıolabilir**Ctrl** anahtar (anahtar ile önceki tarafından belirtilen bir `^`).

- Varsa **türü** özelliği **VIRTKEY'e**, herhangi bir birleşimini **değiştiricisi** ve **anahtar** değerleri geçerlidir.

> [!NOTE]
> Hızlandırıcı tablosu içine bir değer girin ve kabul ASCII/ANSI, select değerine sahip istiyorsanız **türü** tablosu seçip giriş için **ASCII** açılır listeden. Ancak, kullanırsanız **sonraki anahtarı yazılan** komutunu **Düzenle** belirtmek için menü **anahtarı**, değiştirmeniz gerekir **türü** özelliği **VIRTKEY'e** için **ASCII** *önce* girme **anahtar** kod.

## <a name="accelerator-tables"></a>Hızlandırıcı tabloları

Bir C++ projesinde, doğrudan yerinde düzenlemeyle Hızlandırıcı tablosunu düzenleyebilirsiniz **Hızlandırıcı Düzenleyicisi**.

Standart özellik sayfalarının kullanımı için aşağıdaki yordamlara bakın, ancak aynı sonucu yerinde düzenleme ve özellik sayfası yöntemi vardır. Özellik sayfaları veya yerinde düzenlemeyi kullanarak yapılan değişiklikler hemen Hızlandırıcı tablosunda yansıtılır.

Hızlandırıcı tablosunu düzenlemek için:

1. Hızlandırıcı tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

1. Bir giriş tablosunda seçin ve yerinde düzenlemeyi etkinleştirmek için seçin.

1. Açılan birleşik giriş kutusundan seçin ya da değişiklik yerinde yazın:

   - İçin **kimliği**listesinden veya düzenlemek için türü seçin.

   - İçin **değiştiricisi**listeden seçin.

   - İçin **anahtar**listesinden veya düzenlemek için türü seçin.

   - İçin **türü**seçin **ASCII** veya **VIRTKEY'e** listeden.

Açık Hızlandırıcı tablosunda bir giriş bulunacak:

1. Hızlandırıcı tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

1. Bir sütunun içeriğine alfabetik olarak sıralamak için sütun head seçin. Örneğin, **kimliği** Hızlandırıcı tablonuzdaki tüm kimlikleri alfabetik olarak görüntülenecek.

   Listenin tarama ve girişini bulun.

Hızlandırıcı tablosunu giriş eklemek için:

1. Hızlandırıcı tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

1. Hızlandırıcı tablosu içinde sağ tıklatın ve seçin **yeni hızlandırıcı** kısayol menüsünden veya tablonun alt kısmındaki boş satır girişi seçin.

1. Seçin bir **kimliği** aşağı açılan listeden **kimliği** kutusuna veya yeni bir tür *kimliği* içinde **kimliği** kutusu.

1. Tür *anahtarı* bir Hızlandırıcı olarak kullanmak ya da sağ tıklayın ve istediğiniz **sonraki anahtarı yazılan** bir tuş bileşimini veya menüsüne gidin, kısayol menüsünden **Düzenle**  >  **Asılan sonraki tuş**.

1. Değişiklik **değiştiricisi** ve **türü**, gerekirse basın **Enter**.

   > [!NOTE]
   > Tanımladığınız tüm Hızlandırıcıları benzersiz olduğundan emin olun. Birkaç tuş bileşimleri aynı Kimliğine sahip hiçbir olumsuz etkisi, örneğin, atanan olabilir **Ctrl**+**P** ve **F8** ID_PRINT için her ikisi de atanabilir. Ancak, birden fazla kimliği çalışmaz, örneğin, atanan bir tuş bileşimi sahip **Ctrl**+**Z** ID_SPELL_CHECK ve ID_THESAURUS atanmış.

Hızlandırıcı tablosundan girdi silmek için:

1. Hızlandırıcı tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

1. Silme veya basılı girişi seçin **Ctrl** veya **Shift** birden çok girişi seçmek için seçme tuşunu.

1. Sağ tıklatın ve seçin **Sil**, veya menüsüne gidin **Düzenle** > **Sil**.

> [!TIP]
> Silmek için bir kısayol tuşuna basmaktır **Sil** anahtarı.

Hızlandırıcı tablosu girişini başka bir kaynak betik dosyasına kopyalayın veya taşımak için:

1. Hızlandırıcı tablolarını hem kaynak kod dosyalarını açın ve taşımak istediğiniz girişini seçin.

1. Gelen **Düzenle** menüsünde seçin **kopyalama** veya **Kes**.

1. Hedef kaynak betik dosyasında ve bir giriş seçin **Düzenle** menüsünde seçin **Yapıştır**.

> [!NOTE]
> Ayrıca, kopyalama ve yapıştırma için kısayol tuşlarını kullanabilirsiniz.

Birden çok hızlandırma tuşunun özelliklerini değiştirmek için:

1. Hızlandırıcı tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

1. Hızlandırıcı tuşları basılı tutarak değiştirmek istediğiniz seçin **Ctrl** anahtar her birini seçin.

1. Git [Özellikler penceresi](/visualstudio/ide/reference/properties-window) tüm paylaşmak için seçilen Hızlandırıcılar istediğiniz değerleri yazın.

> [!NOTE]
> Her değiştiricisi değer bir Boolean özelliği olarak görünür **özellikleri** penceresi. Değiştirirseniz bir [değiştiricisi](../windows/accelerator-modifier-property.md) değerini **özellikleri** penceresinde Hızlandırıcı tablosunu işler yeni değiştiricisini ek olarak, önceden var olan tüm değiştiriciler. Herhangi bir değiştirici değeri ayarlarsanız, bu nedenle, her hızlandırıcının aynı paylaşımları sağlamak için bunların tümünü ayarlamak ihtiyacınız olacak **değiştiricisi** ayarları.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
[Hızlandırıcı Tuşları](../windows/predefined-accelerator-keys.md)<br/>