---
title: Şerit Tasarımcısı (MFC)
ms.date: 11/19/2018
f1_keywords:
- vc.editors.ribbon.F1
helpviewer_keywords:
- Ribbon Designer (MFC)
- MFC Ribbon Designer
ms.assetid: 0806dfd6-7d11-471a-99e1-4072852231f9
ms.openlocfilehash: 5740b2f93f451a74407483c98ce5bf547b79bf35
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58769491"
---
# <a name="ribbon-designer-mfc"></a>Şerit Tasarımcısı (MFC)

Şerit Tasarımcısı oluşturmanızı ve MFC uygulamalarında şeritler özelleştirme sağlar. Şerit, mantıksal gruplarda komutları düzenleyen bir kullanıcı arabirimi (UI) öğesidir. Bu grupların bir Şeritte ayrı sekmeler pencerenin üst kısmında görünür. Şerit menü çubuğu ve araç çubukları değiştirir. Şerit, uygulamanın kullanılabilirliğini önemli ölçüde artırabilir. Daha fazla bilgi için [şeritler](/windows/desktop/uxguide/cmd-ribbons). Aşağıdaki çizim Şerit gösterir.

![MFC Şerit kaynak denetimi](../mfc/media/ribbon_no_callouts.png "MFC Şerit kaynak denetimi")

Visual Studio'nun önceki sürümlerinde şeritler gerekiyordu gibi MFC Şerit sınıflarını kullanan kod yazılarak oluşturulmak [CMFCRibbonBar sınıfı](../mfc/reference/cmfcribbonbar-class.md). Visual Studio 2010 ve sonraki sürümlerinde, Şerit Tasarımcısı Şerit oluşturmak için alternatif bir yöntem sağlar. İlk olarak, oluşturma ve bir Şerit kaynağı olarak özelleştirebilirsiniz. Ardından MFC uygulamasındaki koddan Şerit kaynağını yükleyin. Hatta Şerit kaynaklarını ve MFC Şerit sınıflarını birlikte kullanabilirsiniz. Örneğin, bir Şerit kaynağı oluşturabilir ve ardından program aracılığıyla daha fazla öğe çalışma zamanında kodu kullanarak ekleyin.

## <a name="understanding-the-ribbon-designer"></a>Şerit Tasarımcısı'nı anlama

Şerit Tasarımcısı oluşturur ve şeridi bir kaynak olarak depolar. Bir Şerit kaynağı oluşturduğunuzda, Şerit Tasarımcısı şu üç şeyi yapar:

- Bir giriş ekler proje kaynağı tanımlama betiğine (* .rc). Aşağıdaki örnekte, ıdr_rıbbon Şerit kaynağını tanımlayan benzersiz addır, RT_RIBBON_XML kaynak türüdür ve ribbon.mfcribbon ms kaynak dosyasının adıdır.

```
    IDR_RIBBON RT_RIBBON_XML      "res\\ribbon.mfcribbon-ms"
```

- Tanımları komut kimliklerinin tanımını resource.h öğesine ekler.

```
#define IDR_RIBBON            307
```

- Şeridin düğmeleri, denetimleri ve özniteliklerini tanımlayan XML kodunu içeren bir Şerit kaynak dosyası (*.mfcribbon-ms) oluşturur. Şerit tasarımcısındaki Şeritte yapılan değişiklikler kaynak dosyasında XML olarak depolanır. Aşağıdaki kod örneği içeriğini parçası gösterir bir \*.mfcribbon-ms dosyası:

```
<RIBBON_BAR>
<ELEMENT_NAME>RibbonBar</ELEMENT_NAME>
<IMAGE>
<ID>
<NAME>IDB_BUTTONS</NAME>
<VALUE>113</VALUE>
</ID>
```

Şerit kaynağını MFC uygulamanızda kullanmak için çağırarak kaynağı yükleyin [CMFCRibbonBar::LoadFromResource](../mfc/reference/cmfcribbonbar-class.md#loadfromresource).

## <a name="creating-a-ribbon-by-using-the-ribbon-designer"></a>Şerit Tasarımcısı kullanarak Şerit oluşturma

MFC projenize Şerit kaynağı eklemek için iki şekilde şunlardır:

- Bir MFC uygulaması oluşturun ve şeridi oluşturmak üzere MFC proje sihirbazını yapılandırın. Daha fazla bilgi için [izlenecek yol: MFC kullanarak Şerit uygulaması oluşturma](../mfc/walkthrough-creating-a-ribbon-application-by-using-mfc.md).

- Mevcut bir MFC projesinde bir Şerit kaynağı oluşturabilir ve yükleyin. Daha fazla bilgi için [izlenecek yol: (Kısım 1) MFC karalama uygulamasını güncelleştirme](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md).

Projeniz el ile kodlanmış bir Şerit zaten varsa, MFC, mevcut şeridi bir Şerit kaynağına dönüştürmek için kullanabileceğiniz işlevleri vardır. Daha fazla bilgi için [nasıl yapılır: Varolan bir MFC şeridini Şerit kaynağına dönüştürme](../mfc/how-to-convert-an-existing-mfc-ribbon-to-a-ribbon-resource.md).

> [!NOTE]
>  İletişim tabanlı uygulamalarda Şerit oluşturulamaz. Daha fazla bilgi için [Application Type, MFC Uygulama Sihirbazı](../mfc/reference/application-type-mfc-application-wizard.md).

## <a name="customizing-ribbons"></a>Şeritleri özelleştirme

Şerit Tasarımcısı'nda bir Şerit açmak için kaynak görünümünde Şerit kaynağını çift tıklayın. Tasarımcıda ekleyin, kaldırın ve Şerit, uygulama düğmesini veya hızlı erişim araç çubuğu öğelerini özelleştirdiğiniz. Düğme tıklama olayları ve menü olayları gibi olayları da uygulamanızda bir yönteme de bağlayabilirsiniz.

Aşağıdaki çizim Şerit tasarımcısındaki çeşitli bileşenleri gösterir.

![MFC Şerit Tasarımcısı](../mfc/media/ribbon_designer.png "MFC Şerit Tasarımcısı")

- **Araç kutusu:** Tasarımcı yüzeyine sürüklenebilen denetimler içerir.

- **Tasarımcı yüzeyi:** Şerit kaynağını görsel temsilini içerir.

- **Özellikler penceresi:** Tasarımcı yüzeyinde seçilen öğenin özniteliklerini listeler.

- **Kaynak Görünümü penceresi:** Projenize Şerit kaynakları dahil kaynakları görüntüler.

- **Şerit Düzenleyicisi araç çubuğu:** Şeridi önizlemenizi ve görsel temasını değiştirmenizi sağlayan komutları içerir.

Aşağıdaki konular, Şerit Tasarımcısı'nda özelliklerini kullanmak nasıl açıklar:

- [Nasıl yapılır: Uygulama düğmesini özelleştirme](../mfc/how-to-customize-the-application-button.md)

- [Nasıl yapılır: Hızlı Erişim Araç çubuğunu özelleştirme](../mfc/how-to-customize-the-quick-access-toolbar.md)

- [Nasıl yapılır: Şerit denetimleri ve olay işleyicileri ekleme](../mfc/how-to-add-ribbon-controls-and-event-handlers.md)

- [Nasıl yapılır: Bir MFC uygulamasından Şerit kaynağı yükleme](../mfc/how-to-load-a-ribbon-resource-from-an-mfc-application.md)

## <a name="definitions-of-ribbon-elements"></a>Şerit öğelerinin tanımları

![MFC Şerit](../mfc/media/ribbon.png "MFC Şeridi")

- **Uygulama düğmesi:** Şerit üzerinde üst sol löşede görüntülenen düğme. Uygulama düğmesi Dosya menüsünün yerini alır ve hatta Şerit küçültüldüğünde bile görülebilir. Düğme tıklandığında komutların bir listesini içeren bir menü görüntülenir.

- **Hızlı Erişim Araç çubuğu:** Sık görüntüleyen küçük ve özelleştirilebilir bir araç komutları kullanılır.

- **Kategori**: Bir Şerit sekmesinin içeriğini temsil eden mantıksal gruplama.

- **Kategori varsayılan düğmesi:** Şerit küçültüldüğünde Şerit üzerinde görüntülenen düğme. Düğme tıklandığında kategori menü olarak yeniden görüntülenir.

- **Pano:** Bir alan bir ilgili denetimlerin grubunu görüntüleyen Şerit çubuğu. Her Şerit kategorisi bir veya daha fazla Şerit paneli içerir.

- **Şerit öğeleri:** Panel üzerindeki, örneğin, düğmeler ve birleşik giriş kutuları denetler. Bir Şeritte barındırılabilecek farklı denetimleri görmek için bkz: [RibbonGadgets örneği: Şerit araçları uygulaması](../overview/visual-cpp-samples.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)<br/>
[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)
