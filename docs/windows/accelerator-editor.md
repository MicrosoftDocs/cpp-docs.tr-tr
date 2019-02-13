---
title: Hızlandırıcı Düzenleyicisi (C++)
ms.date: 11/04/2016
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
ms.openlocfilehash: 5ece5c7e85a3ef59b728474746e9553a751d43c6
ms.sourcegitcommit: bec1480a03e7b4070b469a6c131a69f516bbac70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/13/2019
ms.locfileid: "56226351"
---
# <a name="accelerator-editor-c"></a>Hızlandırıcı Düzenleyicisi (C++)

Hızlandırıcı tablosunu hızlandırma tuşları (kısayol tuşları olarak da bilinir) bir listesini içeren bir C++ Windows kaynak ve bunlarla ilişkili komut tanımlayıcıları ' dir. Bir program, birden fazla Hızlandırıcı tablosu olabilir.

Normalde, Hızlandırıcıları klavye kısayolları da menü veya araç çubuğunda kullanılabilir program komutları için kullanılır. Ancak, Hızlandırıcı tablosu tuş bileşimleri için ilişkili bir kullanıcı arabirimi nesnesi olmayan komutları tanımlamak için kullanabilirsiniz.

Kullanabileceğiniz [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code) kod anahtar komutlarını Hızlandırıcı yeteneklerinizi.

Önceden tanımlanmış Hızlandırıcı tuşları listesi için bkz. [önceden tanımlanmış Hızlandırıcı tuşları](../windows/predefined-accelerator-keys.md).

   > [!TIP]
   > Kullanırken **hızlandırıcı** Düzenleyicisi sağ sık kullanılan komutlar bir kısayol menüsünü görüntülemek için. Kullanılabilir komutlar ne işaretçinin işaret ettiği üzerinde bağlıdır.

   > [!NOTE]
   > Windows, boş bir Hızlandırıcı tabloları oluşturmak izin vermez. Hızlandırıcı tablosunu giriş yok oluşturursanız, tabloyu kaydettiğinizde otomatik olarak silinir.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="accelerator-properties"></a>Hızlandırıcı özellikleri

Hızlandırıcı özelliklerini ayarlayabileceğiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window) dilediğiniz zaman. Ayrıca **hızlandırıcı** Hızlandırıcı tablosunda Hızlandırıcı özelliklerini değiştirmek için düzenleyici. Kullanılarak yapılan değişiklikleri **özellikleri** penceresi veya **hızlandırıcı** Düzenleyicisi sahip aynı sonucu: düzenlemeleri Hızlandırıcı tablosunda anında yansıtılır.

### <a name="id-property"></a>ID özelliği

**Kimliği** her Hızlandırıcı tablosu girişini program kodunda özelliğine başvuruyor. Bu giriş kullanıcı kısayol tuşunu ya da bir tuş bileşimi bastığında program alırsınız komut değerdir. (Hızlandırıcı tablosu kimliği menüsü kaynak kimliği ile aynı olduğu sürece) bir kısayol menü öğesi ile aynı yapmak için kimlikleri aynı yapın.

Her Hızlandırıcı kimliği için üç özellik vardır: **değiştiricisi** özelliği **anahtarı** özelliği ve **türü** özelliği.

#### <a name="modifier-property"></a>Değiştirici özelliği

**Değiştiricisi** özelliği denetimi için kısayol tuş birleşimleri ayarlar.

> [!NOTE]
> İçinde **özellikleri** penceresi, bu özellik, üç ayrı görünür **Boole** özellikler, bunların tümü denetlenebilir bağımsız olarak: **Alt**, **Ctrl**, ve **Shift**.

İçin yasal girdileri verilmiştir **değiştiricisi** Hızlandırıcı tablosu özelliği:

   |Değer|Açıklama|
   |-----------|-----------------|
   |**Yok.**|Kullanıcı yalnızca **anahtar** değeri. Bu değer en etkili bir şekilde 026 aracılığıyla 001 ASCII/ANSI değerleri olarak yorumlanıp kullanılır ^ A-^ Z (**Ctrl + A** aracılığıyla **Ctrl + Z**).|
   |**Alt**|Kullanıcı gerekir basın **Alt** önce anahtar **anahtar** değeri.|
   |**CTRL**|Kullanıcı gerekir basın **Ctrl** önce anahtar **anahtar** değeri. ASCII türü geçerli değil.|
   |**Kaydırma**|Kullanıcı gerekir basın **Shift** önce anahtar **anahtar** değeri.|
   |**Ctrl + Alt**|Kullanıcı gerekir basın **Ctrl** anahtarı ve **Alt** önce anahtar **anahtar** değeri. ASCII türü geçerli değil.|
   |**CTRL + üst karakter**|Kullanıcı gerekir basın **Ctrl** anahtarı ve **Shift** önce anahtar **anahtar** değeri. ASCII türü geçerli değil.|
   |**Alt + üst karakter**|Kullanıcı gerekir basın **Alt** anahtarı ve **Shift** önce anahtar **anahtar** değeri. ASCII türü geçerli değil.|
   |**Ctrl + Alt + üst karakter**|Kullanıcı gerekir basın **Ctrl**, **Alt**, ve **Shift** önce **anahtar** değeri. ASCII türü geçerli değil.|

#### <a name="key-property"></a>Anahtar özelliği

**Anahtar** özelliği Hızlandırıcı olarak kullanılacak gerçek anahtarı ayarlar.

İçin yasal girdileri verilmiştir **anahtar** Hızlandırıcı tablosu özelliği:

   |Değer|Açıklama|
   |-----------|-----------------|
   |0 ve 255 ondalık biçiminde arasında bir tamsayı.|Değer, değer ASCII veya ANSI şu şekilde işlenir olup olmadığını belirler:<br/><br/>-Tek basamaklı sayı her zaman ASCII veya ANSI değerleri olarak değil, karşılık gelen anahtar olarak yorumlanır.<br/>-1 ila 26, önünde sıfır ile zaman değerlerini olarak yorumlanır ^ A-^ alfabedeki ile basıldığında ASCII değeri temsil eden Z **Ctrl** tuşu basılı tutularak.<br/>-27-32 değerlerinden her zaman üç basamaklı ondalık değerler 032 aracılığıyla 027 olarak yorumlanır.<br/>-033 ile 255'den 0'ın öncesinde ya da ANSI değerleri olarak yorumlanmadı değerleri.|
   |Tek klavye karakter.|A - Z büyük harf veya sayı 0 - 9 ASCII veya sanal anahtar değerleri olabilir; başka bir karakter yalnızca ASCII'dir.|
   |Bir tek klavye karakter aralığı A - Z (yalnızca büyük), öncesinde bir şapka (^) (örneğin, ^ C).|İle basıldığında anahtarın ASCII değeri bu seçeneği girer **Ctrl** tuşu basılı tutularak.|
   |Herhangi bir geçerli sanal anahtar tanımlayıcı.|Hızlandırıcı tablosu açılan anahtar kutusunda standart sanal anahtarı tanımlayıcıları listesini içerir.|

> [!NOTE]
> ASCII değeri girerken değiştiricisi özellik seçenekleri sınırlıdır. Yalnızca denetim kullanılabilir için anahtar kullanımı **Alt** anahtarı.

> [!TIP]
> Hızlandırıcı tuşunu tanımlamak için başka bir yolu ise Hızlandırıcı tablosunda birden çok girişlere sağ tıklayın, seçin **sonraki anahtarı yazılan** kısayol menüsünden anahtarlar veya tuş birleşimleri birini klavyede tuşuna basın. **Sonraki anahtarı yazılan** komutu kullanılabilir ayrıca **Düzenle** menüsü.

#### <a name="type-property"></a>Tür özelliği

**Türü** özelliği belirler Hızlandırıcı Kimliğiyle ilişkilendirilmiş kısayol tuş bileşimi bir ASCII/ANSI anahtar değeri veya bir sanal anahtar (VIRTKEY'e) birleşimi olarak yorumlanır.

- Varsa **türü** özelliktir ASCII, **değiştiricisi** özelliği být pouze parametry `None` veya `Alt`, veya kullanan bir Hızlandırıcı olabilir **Ctrl** (anahtar Belirtilen anahtarla koyarak bir `^`).

- Varsa **türü** özelliktir VIRTKEY'e, herhangi bir birleşimini `Modifier` ve `Key` değerleri geçerlidir.

> [!NOTE]
> Hızlandırıcı tablosu içine bir değer girin ve ASCII/ANSI, yalnızca tıklatın değerlendirilmesi bir değere sahip istiyorsanız **türü** açılır listeden seçin ASCII ve tablo girişi. Ancak, kullanırsanız **sonraki anahtarı yazılan** komut (**Düzenle** menüsü) belirtmek için `Key`, değiştirmeniz gerekir **türü** VIRTKEY'e özelliğine ASCII *önce* girme `Key` kod.

## <a name="accelerator-tables"></a>Hızlandırıcı tabloları

Bir C++ projesinde, doğrudan yerinde düzenlemeyle Hızlandırıcı tablosunu düzenleyebilirsiniz **hızlandırıcı** Düzenleyici.

Standart özellik sayfalarının kullanımı için aşağıdaki yordamlara bakın, ancak aynı sonucu yerinde düzenleme ve özellik sayfası yöntemi vardır. Özellik sayfaları veya yerinde düzenlemeyi kullanarak yapılan değişiklikler hemen Hızlandırıcı tablosunda yansıtılır.

> [!NOTE]
> Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

### <a name="to-edit-in-an-accelerator-table"></a>Hızlandırıcı tablosunu düzenleme

1. Hızlandırıcı tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

1. Bir giriş tablosunda seçin ve yerinde düzenlemeyi etkinleştirmek için seçin.

1. Açılan birleşik giriş kutusundan seçin veya değişiklik yerinde yazın.

   - İçin **kimliği**listesinden veya düzenlemek için türü seçin.

   - İçin **değiştiricisi**listeden seçin.

   - İçin **anahtar**listesinden veya düzenlemek için türü seçin.

   - İçin **türü**seçin **ASCII** veya **VIRTKEY'e** listeden.

### <a name="to-find-an-entry-in-an-open-accelerator-table"></a>Açık Hızlandırıcı tablosunda giriş aramak için

1. Hızlandırıcı tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

1. Bir sütunun içeriğine alfabetik olarak sıralamak için sütun head seçin. Örneğin, **kimliği** Hızlandırıcı tablonuzdaki tüm kimlikleri alfabetik olarak görüntülenecek.

Listenin tarama ve girişini bulun.

### <a name="to-add-an-entry-to-an-accelerator-table"></a>Hızlandırıcı tablosunu giriş ekleme

1. Hızlandırıcı tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

1. Hızlandırıcı tablosu içinde sağ tıklatın ve seçin **yeni hızlandırıcı** kısayol menüsünden veya tablonun alt kısmındaki boş satır girişi seçin.

1. Seçin bir **kimliği** kimliği aşağı açılan listeden kutusuna veya yeni bir kimliği yazın **kimliği** kutusu.

1. Türü **anahtarı** bir Hızlandırıcı veya sağ tıklayarak kullanın ve isteyip **sonraki anahtarı yazılan** bir tuş bileşimi ayarlamak için kısayol menüsünden ( **sonraki anahtarı yazılan** komutu Ayrıca kullanılabilir **Düzenle** menü).

1. Değişiklik **değiştiricisi** ve **türü**, gerekirse.

1. Tuşuna **girin**.

   > [!NOTE]
   > Tanımladığınız tüm Hızlandırıcıları benzersiz olduğundan emin olun. Birkaç tuş bileşimleri aynı Kimliğine sahip hiçbir olumsuz etkisi, örneğin, atanan olabilir **Ctrl** + **P** ve **F8** ID_PRINT için her ikisi de atanabilir. Ancak, birden fazla kimliği çalışmaz, örneğin, atanan bir tuş bileşimi sahip **Ctrl** + **Z** ID_SPELL_CHECK ve ID_THESAURUS atanmış.

### <a name="to-delete-an-entry-from-an-accelerator-table"></a>Hızlandırıcı tablosundan giriş silme

1. Hızlandırıcı tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

1. Silmek istediğiniz girişini seçin. (Basılı **Ctrl** veya **Shift** birden çok girişi seçmek için seçme tuşunu.)

1. Sağ tıklatın ve seçin **Sil** kısayol menüsünden (veya **Sil** gelen **Düzenle** menü).

> [!TIP]
> Silme için bir kısayol tuşuna basmaktır **Sil** anahtarı.

### <a name="to-move-or-copy-an-accelerator-table-entry-to-another-resource-script-file"></a>Hızlandırıcı tablosu girişini başka bir kaynak betik dosyasına taşınacak veya kopyalanacak

1. Hızlandırıcı tablolarını, hem kaynak kod dosyalarını açın.

1. Taşımak istediğiniz girişini seçin.

1. Gelen **Düzenle** menüsünde seçin **kopyalama** veya **Kes**.

1. Hedef kaynak kod dosyasında bir giriş seçin.

1. Gelen **Düzenle** menüsünde seçin **Yapıştır**.

   > [!NOTE]
   > Ayrıca, kopyalama ve yapıştırma için kısayol tuşlarını kullanabilirsiniz.

### <a name="to-change-the-properties-of-multiple-accelerator-keys"></a>Birden çok hızlandırma tuşunun özelliklerini değiştirme

1. Hızlandırıcı tablosu simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

1. Hızlandırıcı tuşları basılı tutarak değiştirmek istediğiniz seçin **Ctrl** anahtar her birini seçin.

1. Git [Özellikler penceresi](/visualstudio/ide/reference/properties-window) tüm paylaşmak için seçilen Hızlandırıcılar istediğiniz değerleri yazın.

   > [!NOTE]
   > Her değiştiricisi değer bir Boolean özelliği olarak görünür **özellikleri** penceresi. Değiştirirseniz bir [değiştiricisi](../windows/accelerator-modifier-property.md) değerini **özellikleri** penceresinde Hızlandırıcı tablosunu işler yeni değiştiricisini ek olarak, önceden var olan tüm değiştiriciler. Herhangi bir değiştirici değeri ayarlarsanız, bu nedenle, her hızlandırıcının aynı paylaşımları sağlamak için bunların tümünü ayarlamak ihtiyacınız olacak **değiştiricisi** ayarları.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)

[Hızlandırıcı Tablosunu Düzenleme](../windows/editing-in-an-accelerator-table.md)<br/>
[Önceden Tanımlanmış Hızlandırıcı Tuşları](../windows/predefined-accelerator-keys.md)<br/>