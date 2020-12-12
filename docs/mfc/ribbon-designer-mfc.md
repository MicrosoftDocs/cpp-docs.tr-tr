---
description: 'Daha fazla bilgi edinin: Şerit Tasarımcısı (MFC)'
title: Şerit Tasarımcısı (MFC)
ms.date: 11/19/2018
f1_keywords:
- vc.editors.ribbon.F1
helpviewer_keywords:
- Ribbon Designer (MFC)
- MFC Ribbon Designer
ms.assetid: 0806dfd6-7d11-471a-99e1-4072852231f9
ms.openlocfilehash: 9491efb0c88f540f1376f42e831eb78b042cf6df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218023"
---
# <a name="ribbon-designer-mfc"></a>Şerit Tasarımcısı (MFC)

Şerit Tasarımcısı, MFC uygulamalarında şeritler oluşturmanıza ve özelleştirmenize olanak sağlar. Şerit, komutları mantıksal gruplar halinde düzenleyen bir kullanıcı arabirimi (UI) öğesidir. Bu gruplar pencerenin üst kısmındaki bir şeridinde ayrı sekmelerde görüntülenir. Şerit, menü çubuğu ve araç çubuklarının yerini alır. Bir şerit, uygulama kullanılabilirliğini önemli ölçüde iyileştirebilir. Daha fazla bilgi için bkz. [şeritler](/windows/win32/uxguide/cmd-ribbons). Aşağıdaki çizimde bir şerit gösterilmektedir.

![MFC Şeridi Kaynak denetimi](../mfc/media/ribbon_no_callouts.png "MFC Şeridi Kaynak denetimi")

Visual Studio 'nun önceki sürümlerinde,, [CMFCRibbonBar sınıfı](../mfc/reference/cmfcribbonbar-class.md)gibi mfc şerit sınıflarını kullanan kod yazarak şeritlerin oluşturulması gerekiyordu. Visual Studio 2010 ve üzeri sürümlerde, Şerit Tasarımcısı şeritler oluşturmak için alternatif bir yöntem sağlar. İlk olarak, bir şeridi kaynak olarak oluşturun ve özelleştirin. Ardından, şerit kaynağını MFC uygulamasındaki koddan yükleyin. Şerit kaynaklarını ve MFC şerit sınıflarını da birlikte kullanabilirsiniz. Örneğin, bir şerit kaynağı oluşturabilir ve daha sonra kodu kullanarak çalışma zamanında buna program aracılığıyla daha fazla öğe ekleyebilirsiniz.

## <a name="understanding-the-ribbon-designer"></a>Şerit Tasarımcısını anlama

Şerit Tasarımcısı, şeridi oluşturur ve bir kaynak olarak depolar. Bir şerit kaynağı oluşturduğunuzda, Şerit Tasarımcısı bu üç şeyi yapar:

- Proje kaynak tanımı betiğine (*. RC) bir giriş ekler. Aşağıdaki örnekte, IDR_RIBBON şerit kaynağını tanımlayan benzersiz addır, RT_RIBBON_XML kaynak türüdür ve Ribbon. mfcribbon-ms kaynak dosyasının adıdır.

```cpp
    IDR_RIBBON RT_RIBBON_XML      "res\\ribbon.mfcribbon-ms"
```

- Komut kimliklerinin tanımlarını Resource. h öğesine ekler.

```
#define IDR_RIBBON            307
```

- Şeridin düğmelerini, denetimlerini ve özniteliklerini tanımlayan XML kodunu içeren bir Şerit kaynak dosyası (*. mfcribbon-ms) oluşturur. Şerit tasarımcısındaki şeritte yapılan değişiklikler kaynak dosyasında XML olarak depolanır. Aşağıdaki kod örneği bir \* . mfcribbon-ms dosyasının içeriğinin bir parçasını gösterir:

```
<RIBBON_BAR>
<ELEMENT_NAME>RibbonBar</ELEMENT_NAME>
<IMAGE>
<ID>
<NAME>IDB_BUTTONS</NAME>
<VALUE>113</VALUE>
</ID>
```

MFC uygulamanızda şerit kaynağını kullanmak için [CMFCRibbonBar:: LoadFromResource](../mfc/reference/cmfcribbonbar-class.md#loadfromresource)öğesini çağırarak kaynağı yükleyin.

## <a name="creating-a-ribbon-by-using-the-ribbon-designer"></a>Şerit Tasarımcısını kullanarak şerit oluşturma

Bunlar, MFC projenize Şerit kaynağı eklemenin iki yolu vardır:

- Bir MFC uygulaması oluşturun ve şerit oluşturmak için MFC Proje Sihirbazı 'Nı yapılandırın. Daha fazla bilgi için bkz. [Izlenecek yol: MFC kullanarak şerit uygulaması oluşturma](../mfc/walkthrough-creating-a-ribbon-application-by-using-mfc.md).

- Varolan bir MFC projesinde, bir şerit kaynağı oluşturup yükleyin. Daha fazla bilgi için bkz. [Izlenecek yol: MFC karalama uygulamasını güncelleştirme (1. bölüm)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md).

Projenizin zaten el ile kodlanmış bir şeridi varsa, MFC, varolan Şeriti bir şerit kaynağına dönüştürmek için kullanabileceğiniz işlevlere sahiptir. Daha fazla bilgi için bkz. [nasıl yapılır: varolan BIR MFC şeridini şerit kaynağına dönüştürme](../mfc/how-to-convert-an-existing-mfc-ribbon-to-a-ribbon-resource.md).

> [!NOTE]
> İletişim kutusu tabanlı uygulamalarda şeritler oluşturulamaz. Daha fazla bilgi için bkz. [uygulama türü, MFC Uygulama Sihirbazı](../mfc/reference/application-type-mfc-application-wizard.md).

## <a name="customizing-ribbons"></a>Şeritleri özelleştirme

Şerit tasarımcısında bir şerit açmak için Kaynak Görünümü şerit kaynağına çift tıklayın. Tasarımcıda şerit, uygulama düğmesi veya hızlı erişim araç çubuğu üzerinde öğeleri ekleyebilir, kaldırabilir ve özelleştirebilirsiniz. Olayları, örneğin düğme tıklama olayları ve menü olayları gibi uygulamanızdaki bir yönteme da bağlayabilirsiniz.

Aşağıdaki çizim, Şerit Tasarımcısı 'ndaki çeşitli bileşenleri göstermektedir.

![MFC Şerit Tasarımcısı](../mfc/media/ribbon_designer.png "MFC Şerit Tasarımcısı")

- **Araç kutusu:** Tasarımcı yüzeyine sürüklenebilen denetimleri içerir.

- **Tasarımcı yüzeyi:** Şerit kaynağının görsel gösterimini içerir.

- **[Sınıf Sihirbazı](reference/mfc-class-wizard.md):** Tasarımcı yüzeyinde seçilen öğenin özniteliklerini listeler.

- **Kaynak görünümü penceresi:** Projenizdeki şerit kaynaklarını içeren kaynakları görüntüler.

- **Şerit Düzenleyicisi araç çubuğu:** Şeridin önizlemesini yapmanızı ve görsel temasını değiştirmenize olanak sağlayan komutları içerir.

Aşağıdaki konularda, Şerit tasarımcısında özelliklerin nasıl kullanılacağı açıklanır:

- [Nasıl yapılır: uygulama düğmesini özelleştirme](../mfc/how-to-customize-the-application-button.md)

- [Nasıl yapılır: hızlı erişim araç çubuğunu özelleştirme](../mfc/how-to-customize-the-quick-access-toolbar.md)

- [Nasıl yapılır: Şerit denetimleri ve olay Işleyicileri ekleme](../mfc/how-to-add-ribbon-controls-and-event-handlers.md)

- [Nasıl yapılır: bir MFC uygulamasından şerit kaynağı yükleme](../mfc/how-to-load-a-ribbon-resource-from-an-mfc-application.md)

## <a name="definitions-of-ribbon-elements"></a>Şerit öğelerinin tanımları

![MFC Şeridi](../mfc/media/ribbon.png "MFC Şeridi")

- **Uygulama düğmesi:** Şeridin sol üst köşesinde görünen düğme. Uygulama düğmesi Dosya menüsünün yerini alır ve şerit küçültüldüğünde bile görünür. Düğmeye tıklandığında, komut listesi içeren bir menü görüntülenir.

- **Hızlı erişim araç çubuğu:** Sık kullanılan komutları görüntüleyen küçük, özelleştirilebilir bir araç çubuğu.

- **Kategori**: bir Şerit sekmesinin içeriğini temsil eden mantıksal gruplama.

- **Kategori varsayılan düğmesi:** Şerit küçültüldüğünde görüntülenen düğme. Düğmeye tıklandığında kategori bir menü olarak yeniden görüntülenir.

- **Panel:** Bir ilişkili denetimler grubunu görüntüleyen şerit çubuğunun alanı. Her Şerit kategorisi bir veya daha fazla şerit paneli içerir.

- **Şerit öğeleri:** Panellerdeki, düğme ve Birleşik giriş kutularındaki denetimler. Bir şeritte barındırılabilecek çeşitli denetimleri görmek için bkz. [Ribbonaraçları örneği: şerit araçları uygulaması](../overview/visual-cpp-samples.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)<br/>
[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)
