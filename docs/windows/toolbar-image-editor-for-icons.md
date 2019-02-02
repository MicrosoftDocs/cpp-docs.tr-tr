---
title: Araç çubuğu (simgeler için görüntü Düzenleyicisi C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.bitmap
- vc.editors.icon
- vc.editors.texttool
helpviewer_keywords:
- Graphics toolbar
- Image editor [C++], toolbar
- Image editor [C++], Option selector
- Properties window
- Option selector, Image editor
- toolbars [C++], showing
- toolbars [C++], hiding
- text, adding to an image
- Text Tool dialog box [C++]
- Text Tool Font dialog box [C++]
- fonts, changing on an image
- text, on images
ms.assetid: a0af4209-6273-4106-a7c1-0edecc9b5755
ms.openlocfilehash: dfbd721afd997f3151b1c20a7e0e1fb60e0c83e4
ms.sourcegitcommit: efcc8c97570ddf7631570226c700e8f6ebb6c7be
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2019
ms.locfileid: "55560328"
---
# <a name="toolbar-c-image-editor-for-icons"></a>Araç çubuğu (simgeler için görüntü Düzenleyicisi C++)

**Resim Düzenleyicisi** araç çubuğu çizim, boyama, metin girme, silme ve görünüm işlemek için araçları içerir. Ayrıca, her aracını kullanma seçenekleri seçebilirsiniz bir seçenek belirleyici içerir. Örneğin, çeşitli fırça genişlikleri, büyütme faktörleri ve satır stilleri seçebilirsiniz.

> [!NOTE]
> Kullanılabilir olan tüm araçları **Resim Düzenleyicisi** araç web'da ayrıca **görüntü** menü (altında **Araçları** komutu).

![Resim Düzenleyicisi araç çubuğu](../mfc/media/vcimageeditortoolbar.gif "vcImageEditorToolbar") Resim Düzenleyicisi araç çubuğu

Kullanılacak **Resim Düzenleyicisi** araç ve **seçeneği** Seçici, Aracı'nı seçin veya istediğiniz seçeneği.

> [!TIP]
> İmlecinizi bir araç çubuğu düğmenin üzerine geldiğinizde araç ipuçlarında görünür. Bu ipuçları her düğmesinin işlevini belirlemenize yardımcı olabilir.

İle **seçeneği** Seçici genişliğini bir satır, bir fırça vuruşu ve daha fazlasını belirtebilirsiniz. Simgeye **seçeneği** seçtiğiniz bağlı olarak hangi aracın Seçici değişir.

![Çizim&#45;şekli Seçici görüntü düzenleyici araç çubuğunda](../mfc/media/vcimageeditortoolbaroptionselector.gif "vcImageEditorToolbarOptionSelector") görüntü düzenleyici araç çubuğunda seçenek belirleyici

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="use-the-text-tool-dialog-box"></a>Metin aracı iletişim kutusunu kullanın

Kullanım **metin aracı** imleç, bit eşlem ve simge kaynak metin eklemek için iletişim kutusu.

Bu iletişim kutusuna erişmek için açık [Resim Düzenleyicisi](../windows/window-panes-image-editor-for-icons.md). Seçin **Araçları** gelen **görüntü** menüsüne ve ardından **metin aracı** komutu.

### <a name="font-button"></a>Yazı tipi düğmesi

Açılır **metin aracı yazı tipi** iletişim kutusu, hangi değiştirebilirsiniz yazı tipini, stili veya imleç yazı tipi boyutu. Değişiklikleri görüntülenen metni uygulanır **metin** alan.

Bu iletişim kutusuna erişmek için seçin **yazı tipi** düğmesine **metin aracı** iletişim kutusu. Kullanılabilir özellikler şunlardır:

|Özellik|Açıklama|
|---|---|
|**Yazı tipi**|Yazı tiplerini listeler.|
|**Yazı tipi stili**|Belirtilen yazı tipi için kullanılabilir stilleri listeler.|
|**Boyutu**|Belirtilen yazı tipi noktası kullanılabilir boyutları listeler.|
|**Örnek**|Metnin belirtilen yazı tipi ayarlarını ile nasıl görüneceğini gösterir.|
|**Komut Dosyası**|Belirtilen yazı tipi kullanılabilir dil kodları listeler. Farklı dil komut dosyasını seçin, karakter için dil, çok dilli belgeleri oluşturmak için kullanılabilir duruma ayarlanır.|

#### <a name="to-change-the-font-of-text-on-an-image"></a>Görüntüdeki metnin yazı tipini değiştirmek için

Aşağıdaki yordamda, bir Windows uygulamasındaki bir simge metin ekleyin ve yazı tipi, metin işlemek nasıl örneğidir.

1. Bir C++ Windows Forms uygulaması oluşturun. Ayrıntılar için bkz [bir Windows uygulaması projesi oluşturma](/previous-versions/visualstudio/visual-studio-2010/42wc9kk5). Bir *n app.ico* dosya varsayılan olarak projenize eklenir.

1. İçinde **Çözüm Gezgini**, dosyayı çift *n app.ico*. [Resim Düzenleyicisi](../windows/image-editor-for-icons.md) açılır.

1. Gelen **görüntü** menüsünde **Araçları** seçip **metin aracı**. **Metin aracı** iletişim kutusu görüntülenir.

1. İçinde **metin aracı** iletişim kutusuna *C++* boş metin alanında. Bu metin kutusunda sol üst köşedeki bir yeniden boyutlandırılabilir görünür *n app.ico*, **Resim Düzenleyicisi**.

1. İçinde **Resim Düzenleyicisi**, yeniden boyutlandırılabilir kutusunda metnin okunabilirliğini geliştirmek için n app.ico ortasına sürükleyin.

1. İçinde **metin aracı** iletişim kutusunda **yazı tipi** düğmesi. **Metin aracı yazı tipi** iletişim kutusu görüntülenir.

1. İçinde **metin aracı yazı tipi** iletişim kutusunda **Times yeni Roman** listelenen tiplerinin listesinden **yazı tipi** liste kutusu.

1. Seçin **kalın** listelenen kullanılabilir yazı tipi stillerini listesinden **yazı tipi stili** liste kutusu.

1. Seçin **10** listesinden kullanılabilir boyutları listelenen noktası **boyutu** liste kutusu.

1. **Tamam** düğmesini seçin. **Metin aracı yazı tipi** iletişim kutusunu kapatmak ve yeni yazı tipi ayarlarını metninize uygulanır.

1. Seçin **Kapat** düğmesini **metin aracı** iletişim kutusu. Yeniden boyutlandırılabilir kutu çevresinde, metin alanından kaybolur **Resim Düzenleyicisi**.

### <a name="text-area"></a>Metin alanı

Kaynak bir parçası olarak görünen metni görüntüler. Başlangıçta bu alan boştur.

> [!NOTE]
> Varsa **saydam arka plan** , yalnızca metin görüntüsüne yerleştirilir ayarlanmış. Varsa **donuk arka plan** ayarlandığında, sınırlayıcı bir dikdörtgen ile doldurulan [arka plan rengi](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md), metnin arkasında yer alır. Daha fazla bilgi için [seçme opak ve saydam arka planlar](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).

Sağ tıklayabilirsiniz **metin aracı** standart Windows komutların bir listesini içeren bir varsayılan kısayol menüsüne erişmek için iletişim kutusu.

## <a name="to-display-or-hide-the-image-editor-toolbar"></a>Görüntülenecek veya Resim Düzenleyicisi araç çubuğunu gizle

Çizim araçlarından birçoğunu kullanılabilir olduğundan [klavye](../windows/accelerator-keys-image-editor-for-icons.md), gizlemek bazen kullanışlıdır **Resim Düzenleyicisi** araç çubuğu.

Üzerinde **görünümü** menüsünde **araç çubukları** ardından **Resim Düzenleyicisi**.

   > [!NOTE]
   > Bu araç çubuğu öğeleri görünür bir resim dosyası olduğunda kullanılamaz geçerli projeden veya çözüm açık değil **Resim Düzenleyicisi**. Bkz: [bir simge veya diğer görüntü oluşturma](../windows/creating-an-icon-or-other-image-image-editor-for-icons.md), projelerinize görüntü dosyaları ekleme hakkında bilgi için.

## <a name="requirements"></a>Gereksinimler

Hiçbiri

## <a name="see-also"></a>Ayrıca Bkz.

[Renkler penceresi](../windows/colors-window-image-editor-for-icons.md)<br/>
[Grafik kaynakları düzenleme](../windows/editing-graphical-resources-image-editor-for-icons.md)<br/>
[Hızlandırıcı Tuşları](../windows/accelerator-keys-image-editor-for-icons.md)<br/>