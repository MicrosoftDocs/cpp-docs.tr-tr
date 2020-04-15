---
title: Şerit Tasarımcısı (MFC)
ms.date: 11/19/2018
f1_keywords:
- vc.editors.ribbon.F1
helpviewer_keywords:
- Ribbon Designer (MFC)
- MFC Ribbon Designer
ms.assetid: 0806dfd6-7d11-471a-99e1-4072852231f9
ms.openlocfilehash: 8b66ff0f19392eb1685f8632a3fc4d9e90094304
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372797"
---
# <a name="ribbon-designer-mfc"></a>Şerit Tasarımcısı (MFC)

Şerit Tasarımcısı, MFC uygulamalarında şeritler oluşturmanıza ve özelleştirmenize olanak tanır. Şerit, komutları mantıksal gruplar halinde düzenleyen bir kullanıcı arabirimi (UI) öğesidir. Bu gruplar pencerenin üst kısmındaki şeritte ayrı sekmelerde görünür. Şerit menü çubuğu ve araç çubukları nın yerini alır. Şerit, uygulama kullanılabilirliğini önemli ölçüde artırabilir. Daha fazla bilgi için [Bkz. Şeritler.](/windows/win32/uxguide/cmd-ribbons) Aşağıdaki resimde bir şerit gösterilmektedir.

![MFC Şerit Kaynak Denetimi](../mfc/media/ribbon_no_callouts.png "MFC Şerit Kaynak Denetimi")

Visual Studio'nun önceki sürümlerinde, [CMFCRibbonBar Class](../mfc/reference/cmfcribbonbar-class.md)gibi MFC şerit sınıflarını kullanan kod yazılarak şeritler oluşturulmak zorunda kaldı. Visual Studio 2010 ve sonrası, şerit tasarımcısı şerit oluşturmak için alternatif bir yöntem sağlar. İlk olarak, kaynak olarak bir şerit oluşturun ve özelleştirin. Ardından MFC uygulamasında koddaki şerit kaynağını yükleyin. Şerit kaynaklarını ve MFC şerit sınıflarını birlikte bile kullanabilirsiniz. Örneğin, bir şerit kaynağı oluşturabilir ve ardından kod kullanarak çalışma zamanında daha fazla öğe ekleyebilirsiniz.

## <a name="understanding-the-ribbon-designer"></a>Şerit Tasarımcısını Anlama

Şerit tasarımcısı şerit oluşturur ve şerit bir kaynak olarak depolar. Bir şerit kaynağı oluşturduğunuzda, şerit tasarımcısı şu üç şeyi yapar:

- Proje kaynak tanımı komut dosyasına (*.rc) bir giriş ekler. Aşağıdaki örnekte, IDR_RIBBON şerit kaynağını tanımlayan benzersiz addır, kaynak türü RT_RIBBON_XML ve şerit.mfcribbon-ms kaynak dosyasının adıdır.

```cpp
    IDR_RIBBON RT_RIBBON_XML      "res\\ribbon.mfcribbon-ms"
```

- Komut Tanımları tanımlarını resource.h'ye ekler.

```
#define IDR_RIBBON            307
```

- Şeridin düğmelerini, denetimlerini ve özniteliklerini tanımlayan XML kodunu içeren bir şerit kaynak dosyası (*.mfcribbon-ms) oluşturur. Şerit tasarımcısındaki şerit değişiklikleri kaynak dosyasında XML olarak depolanır. Aşağıdaki kod örneği,.mfcribbon-ms dosyasının içeriğinin bir \*kısmını gösterir:

```
<RIBBON_BAR>
<ELEMENT_NAME>RibbonBar</ELEMENT_NAME>
<IMAGE>
<ID>
<NAME>IDB_BUTTONS</NAME>
<VALUE>113</VALUE>
</ID>
```

MFC uygulamanızdaki şerit kaynağını kullanmak için [CMFCRibbonBar::LoadFromResource'ı](../mfc/reference/cmfcribbonbar-class.md#loadfromresource)arayarak kaynağı yükleyin.

## <a name="creating-a-ribbon-by-using-the-ribbon-designer"></a>Şerit Tasarımcısını Kullanarak Şerit Oluşturma

MFC projenize şerit kaynağı eklemenin iki yolu şunlardır:

- Bir MFC uygulaması oluşturun ve şeridi oluşturmak için MFC Project Wizard'ı yapılandırın. Daha fazla bilgi için [Bkz. Walkthrough: MFC kullanarak şerit uygulaması oluşturma.](../mfc/walkthrough-creating-a-ribbon-application-by-using-mfc.md)

- Varolan bir MFC projesinde, bir şerit kaynağı oluşturun ve yükleyin. Daha fazla bilgi için [Walkthrough: MFC Karalama Uygulamasını Güncelleştirme (Bölüm 1) bölümüne](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)bakın.

Projenizde zaten el ile kodlanmış bir şerit varsa, MFC'nin varolan şeridi bir şerit kaynağına dönüştürmek için kullanabileceğiniz işlevleri vardır. Daha fazla bilgi için [bkz: Varolan Bir MFC Şeridini Şerit Kaynağına Dönüştürün.](../mfc/how-to-convert-an-existing-mfc-ribbon-to-a-ribbon-resource.md)

> [!NOTE]
> İletişim tabanlı uygulamalarda şeritler oluşturulamaz. Daha fazla bilgi için [Bkz. Uygulama Türü, MFC Uygulama Sihirbazı.](../mfc/reference/application-type-mfc-application-wizard.md)

## <a name="customizing-ribbons"></a>Şerit Özelleştirme

Şerit tasarımcısında şerit açmak için Kaynak Görünümü'ndeki şerit kaynağını çift tıklatın. Tasarımcıda, şeritteki, Uygulama düğmesine veya hızlı erişim araç çubuğuna öğeleri ekleyebilir, kaldırabilir ve özelleştirebilirsiniz. Ayrıca, örneğin düğme tıklatma olayları ve menü olaylarını uygulamanızdaki bir yönteme bağlayabilirsiniz.

Aşağıdaki resimde şerit tasarımcısı çeşitli bileşenleri gösterir.

![MFC Şerit Tasarımcısı](../mfc/media/ribbon_designer.png "MFC Şerit Tasarımcısı")

- **Araç Kutusu:** Tasarımcı yüzeyine sürüklenebilecek denetimler içerir.

- **Tasarımcı Yüzeyi:** Şerit kaynağının görsel temsilini içerir.

- ** [Sınıf Sihirbazı](reference/mfc-class-wizard.md):** Tasarımcı yüzeyinde seçilen öğenin özniteliklerini listeler.

- **Kaynak Görünümü penceresi:** Projenizde şerit kaynaklarını içeren kaynakları görüntüler.

- **Şerit Düzenleyici Araç Çubuğu:** Şeridi önizlemenize ve görsel temasına değiştirmenize izin veren komutlar içerir.

Aşağıdaki konular şerit tasarımcısındaki özelliklerin nasıl kullanılacağını açıklar:

- [Nasıl yapılır: Uygulama Düğmesini Özelleştirme](../mfc/how-to-customize-the-application-button.md)

- [Nasıl yapılır: Hızlı Erişim Araç Çubuğunu Özelleştirme](../mfc/how-to-customize-the-quick-access-toolbar.md)

- [Nasıl yapılır: Şerit Denetimleri ve Olay İşleyicileri Ekleme](../mfc/how-to-add-ribbon-controls-and-event-handlers.md)

- [Nasıl yapılır: Bir MFC Uygulamasından Şerit Kaynağı Yükleme](../mfc/how-to-load-a-ribbon-resource-from-an-mfc-application.md)

## <a name="definitions-of-ribbon-elements"></a>Şerit Elemanlarının Tanımları

![MFC Şerit](../mfc/media/ribbon.png "MFC Şerit")

- **Uygulama düğmesi:** Şeridin sol üst köşesinde görünen düğme. Uygulama düğmesi Dosya menüsünün yerini alır ve şerit en aza indirildiğinde bile görünür. Düğme tıklatıldığında, komut listesi olan bir menü görüntülenir.

- **Hızlı Erişim araç çubuğu:** Sık kullanılan komutları görüntüleyen küçük, özelleştirilebilir araç çubuğu.

- **Kategori**: Şerit sekmesinin içeriğini temsil eden mantıksal gruplandırma.

- **Kategori Varsayılan düğmesi:** Şerit en aza indirildiğinde şeritte görünen düğme. Düğme tıklatıldığında, kategori menü olarak yeniden görünür.

- **Panel:** Şerit çubuğunun bir grup ilgili denetimi görüntüleyen bir alanı. Her şerit kategorisi bir veya daha fazla şerit paneli içerir.

- **Şerit elemanları:** Panellerde denetimler, örneğin, düğmeler ve açılan kutular. Şerit üzerinde barındırılabilen çeşitli denetimleri görmek için [Bkz. Şerit Gadgets Örnek: Şerit Gadget'lar Uygulaması](../overview/visual-cpp-samples.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı Arabirimi Elemanları](../mfc/user-interface-elements-mfc.md)<br/>
[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)
