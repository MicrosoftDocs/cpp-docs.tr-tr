---
title: Kaynak Düzenleyicileri (C++)
ms.date: 02/14/2019
f1_keywords:
- vs.editors.resource
- vc.resvw.resource.editors
- vs.resvw.resource.editors
- vs.resourceview
- vc.resvw.resource.previewing
- vs.resvw.resource.previewing
helpviewer_keywords:
- editors [C++], resource
- editors [C++]
- resource editors
- Windows [C++], application resource editing
- resources [C++], viewing
- layouts, previewing resource
- resource editors [C++], viewing resources
- .rc files [C++], viewing resources
- resources [C++], editing
- properties [C++], resources
- resources [C++], properties
ms.assetid: e20a29ec-d6fb-4ead-98f3-431a0e23aaaf
ms.openlocfilehash: aeeca87ceb5b2c5e54da7087b5020ccbc1c39039
ms.sourcegitcommit: 470de1337035dd33682d935b4b6c6d8b1bdb0bbb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56320815"
---
# <a name="resource-editors-c"></a>Kaynak Düzenleyicileri (C++)

A **kaynak** oluştururken veya değiştirirken bir Visual Studio projesinde bulunan kaynaklar için özel bir ortam düzenleyicisidir. Visual Studio kaynak düzenleyicileri teknikleri ve arabirimleri oluşturma ve uygulama kaynaklarını hızla ve kolayca değiştirme yardımcı olacak paylaşın. Kaynak düzenleyicileri görüntülemek ve kaynakları için uygun düzenleyici ve önizleme kaynakları düzenlemek etkinleştirin.

Bir kaynak oluşturduğunuzda veya açtığınızda uygun Düzenleyicisi'ni otomatik olarak açılır.

> [!NOTE]
> Yönetilen projelere kaynak betik dosyalarına kullanmadığından kaynaklarınızdan açmalısınız **Çözüm Gezgini**. Kullanabileceğiniz [Resim Düzenleyicisi](../windows/image-editor-for-icons.md) ve [ikili düzenleyiciyi](binary-editor.md) yönetilen projelerde kaynak dosyalarıyla çalışmak için. Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır. Visual Studio kaynak düzenleyicileri eklenmiş kaynakları düzenlemeyi desteklemez.

|Kullan...|Düzenlemek için...|
|----------------|----------------|
|[Hızlandırıcı Düzenleyicisi](../windows/accelerator-editor.md)|Hızlandırıcı tablolarında Visual C++ projeleri.|
|[İkili Düzenleyicisi](binary-editor.md)|İkili veri bilgileri ve Visual C++, Visual Basic veya Visual C# projelerinde özel kaynaklar.|
|[İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)|Visual C++ projelerinde iletişim kutuları.|
|[Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)|Bit eşlemler, simgeler, işaretçiler ve diğer Visual C++, Visual Basic veya Visual C# projelerinde görüntü dosyaları.|
|[Menü Düzenleyicisi](../windows/menu-editor.md)|Visual C++ projelerinde menüsü kaynaklarını.|
|[Ribbon Düzenleyicisi](../mfc/ribbon-designer-mfc.md)|MFC projeleri Şerit kaynakları.|
|[Dize Düzenleyicisi](../windows/string-editor.md)|Visual C++ projeleri tablolarında dize.|
|[Araç Çubuğu Düzenleyicisi](../windows/toolbar-editor.md)|Visual C++ projelerinde araç çubuğu kaynakları. Araç çubuğu Düzenleyicisi, Resim Düzenleyicisi'ni bir parçasıdır.|
|[Sürüm Bilgileri Düzenleyicisi](../windows/version-information-editor.md)|Visual C++ projelerinde sürüm bilgisi.|

> [!NOTE]
> Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

## <a name="view-and-edit-resources"></a>Görünümü ve düzenleme kaynakları

Her kaynak türüne sahip bir **kaynak** bu kaynak türü için belirli bir düzenleyici. Yeniden düzenleme, yeniden boyutlandırma, denetimleri ve Özellik Ekle veya aksi ilişkili Düzenleyicisi'ni kullanarak bir kaynak özelliklerini değiştirin. Bir kaynak olarak da düzenleyebilirsiniz [metin biçimi](../windows/how-to-open-a-resource-script-file-in-text-format.md) ve [ikili biçimi](../windows/opening-a-resource-for-binary-editing.md).

Bazı kaynak türleri içeri aktarıldı ve çeşitli şekillerde kullanılan tek dosyalardır; Bunlar, bit eşlemler, simgeler, işaretçiler, araç çubukları ve html dosyaları içerir. Böyle kaynaklar dosya adlarına sahip ve [kaynak tanımlayıcıları](../windows/symbols-resource-identifiers.md). Diğer iletişim kutuları, menüler ve Win32 projeleri, dize tablolarında gibi yalnızca bir kaynak betiği (.rc) veya kaynak şablonu (.rct) dosyasının parçası olarak mevcut.

Kaynak projenin dışında da düzenlenebilir, bkz: [nasıl yapılır: (Tek başına) proje dışındaki kaynak betik dosyasını açma](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).

> [!NOTE]
> Kaynağın özelliklerini [Özellikler penceresini kullanarak değiştirilebilir](../windows/changing-the-properties-of-a-resource.md).

### <a name="to-edit-the-properties-of-a-resource"></a>Kaynağın özelliklerini düzenlemek için

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), seçin ve düzenlemek istediğiniz kaynağa sağ **özellikleri** kısayol menüsünden.

1. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), kaynak özelliklerini değiştirin.

### <a name="to-undo-a-change-made-to-the-properties-of-a-resource"></a>Bir kaynak özelliklerine yapılan bir değişikliği geri almak için

1. Kaynak odak olduğundan emin olun **kaynak görünümü**.

1. Seçin **geri** gelen **Düzenle** menüsü.

### <a name="win32-resources"></a>Win32 kaynakları

Win32 kaynaklarında erişebileceğiniz [kaynak görünümü](../windows/resource-view-window.md) bölmesi.

#### <a name="to-view-a-win32-resource-in-a-resource-editor"></a>Bir Win32 kaynağı kaynak düzenleyicide görüntülemek için

1. Seçin **kaynak görünümü** gelen **görünümü** menüsü.

1. Varsa **kaynak görünümü** penceresi seçin en üst penceresine değil **kaynak görünümü** dön getirmek için sekmesinde.

1. Gelen **kaynak görünümü**, görüntülemek istediğiniz kaynakları içeren proje klasörünü genişletin. Örneğin, bir iletişim kutusu kaynağı görüntülemek istiyorsanız, genişletme **iletişim** klasör.

1. Örneğin, kaynağa çift tıklatın **IDD_ABOUTBOX**.

   Kaynak uygun Düzenleyicisi'nde açılır. Örneğin, iç kaynak iletişim kutusu kaynakları için açılır **iletişim** Düzenleyici.

   Ayrıca [görüntülemek kaynakları bir (kaynak betiği) .rc dosyasındaki açık bir projeniz zorunda kalmadan](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).

#### <a name="to-delete-an-existing-win-32-resource"></a>Mevcut bir Win 32 kaynağı silmek için

1. İçinde **kaynak görünümü**, bir kaynak türü için düğümü genişletin.

1. Sağ tıklayın ve silmek istediğiniz kaynak **Sil** kısayol menüsünden.

   > [!NOTE]
   > Bir belge penceresi dışında bir proje açın .rc dosyası varsa, aynı kısayol menü komutunu kullanarak kaynak silebilirsiniz.

### <a name="managed-project-resources"></a>Yönetilen proje kaynakları

Yönetilen projelere kaynak betik dosyalarına kullanmayın çünkü kaynaklarınızdan açmalısınız **Çözüm Gezgini**. Kullanabileceğiniz [Resim Düzenleyicisi](../windows/image-editor-for-icons.md) ve [ikili düzenleyiciyi](binary-editor.md) yönetilen projelerde kaynak dosyalarıyla çalışmak için. Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır. Visual Studio kaynak düzenleyicileri eklenmiş kaynakları düzenlemeyi desteklemez.

- Yönetilen kaynağı kaynak düzenleyicide görüntülemek için **Çözüm Gezgini**, kaynak, örneğin, çift *Bitmap1.bmp*.

   Kaynak uygun Düzenleyicisi'nde açılır.

- Mevcut bir yönetilen kaynak silmek için **Çözüm Gezgini**, seçin ve silmek istediğiniz kaynağa sağ **Sil** kısayol menüsünden.

## <a name="preview-resources"></a>Önizleme kaynakları

Kaynaklarınızı açmaya gerek kalmadan grafik kaynağı görüntülemek olanak Önizleme. Kaynak Tanımlayıcıları sayılara değiştiğinden bunlara derlenmiş sonra Önizleme de yürütülebilir dosyalar için yararlıdır. Bu sayısal tanımlayıcıları genellikle yeterli bilgi sağlamayan olduğundan, kaynakları Önizleme hızlıca belirlemenize yardımcı olur.

Görsel düzeni aşağıdaki kaynak türlerinin önizlemesini görebilirsiniz: Bit eşlem, iletişim, simge, menü, imleç ve araç çubuğu

Görsel Önizleme işlevi kaynakları için geçerli değildir: Hızlandırıcı, bildirimi, dize tablosu ve sürüm bilgileri

> [!NOTE]
> Kaynakları Önizleme için Win32 gerektirir.

### <a name="to-preview-resources"></a>Kaynakları Önizleme

1. İçinde [kaynak görünümü](../windows/resource-view-window.md) veya seçin, kaynak, örneğin, bir belge penceresi `IDD_ABOUTBOX`.

1. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window)seçin **özellik sayfaları** düğmesi.

   > [!TIP]
   > Bir kısayol üzerinde **görünümü** menüsünde **özellik sayfaları**.

   **Özellik sayfası** kaynak açar, kaynak önizlemesi görüntüleniyor. Ardından **yukarı** ve **aşağı** ağaç gezinmek için ok tuşlarını denetlemek de **kaynak görünümü** ya da belge penceresini. **Özellik sayfası** açık kalır ve odaklı ve önizlenebilir herhangi bir kaynağa göster.

## <a name="requirements"></a>Gereksinimler

Hiçbiri

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)<br/>
[Kaynak dosyaları](../windows/resource-files-visual-studio.md)<br/>
[Kaynak Tanımlayıcıları (simge)](../windows/symbols-resource-identifiers.md)<br/>