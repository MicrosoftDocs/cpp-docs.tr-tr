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
ms.openlocfilehash: 774575e978a8e7f94868eb1b5dad90c6ac345460
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59038667"
---
# <a name="resource-editors-c"></a>Kaynak Düzenleyicileri (C++)

Kaynak Düzenleyicisi oluştururken veya değiştirirken bir Visual Studio projesinde bulunan kaynaklar için özel bir ortamdır. Visual Studio kaynak düzenleyicileri teknikleri ve arabirimleri oluşturma ve uygulama kaynaklarını hızla ve kolayca değiştirme yardımcı olacak paylaşın. Kaynak düzenleyicileri görüntülemek ve kaynakları için uygun düzenleyici ve önizleme kaynakları düzenlemek etkinleştirin.

Bir kaynak oluşturduğunuzda veya açtığınızda uygun Düzenleyicisi'ni otomatik olarak açılır.

> [!NOTE]
> Yönetilen projelere kaynak betik dosyalarına kullanmadığından kaynaklarınızdan açmalısınız **Çözüm Gezgini**. Kullanabileceğiniz [Resim Düzenleyicisi](../windows/image-editor-for-icons.md) ve [ikili düzenleyici](binary-editor.md) yönetilen projelerde kaynak dosyalarıyla çalışmak için. Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır. Visual Studio kaynak düzenleyicileri eklenmiş kaynakları düzenlemeyi desteklemez.

|Kullan...|Düzenlemek için...|
|----------------|----------------|
|[Hızlandırıcı Düzenleyicisi](../windows/accelerator-editor.md)|Hızlandırıcı tablolarında Visual C++ projeleri.|
|[İkili Düzenleyicisi](binary-editor.md)|İkili veri bilgileri ve Visual C++, Visual Basic veya Visual C# projelerinde özel kaynaklar.|
|[İletişim Kutusu Düzenleyicisi](../windows/dialog-editor.md)|Visual C++ projelerinde iletişim kutuları.|
|[Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)|Bit eşlemler, simgeler, işaretçiler ve diğer Visual C++, Visual Basic veya Visual C# projelerinde görüntü dosyaları.|
|[Menü Düzenleyicisi](../windows/menu-editor.md)|Visual C++ projelerinde menüsü kaynaklarını.|
|[Ribbon Düzenleyicisi](../mfc/ribbon-designer-mfc.md)|MFC projeleri Şerit kaynakları.|
|[Dize Düzenleyicisi](../windows/string-editor.md)|Visual C++ projeleri tablolarında dize.|
|[Araç Çubuğu Düzenleyicisi](../windows/toolbar-editor.md)|Visual C++ projelerinde araç çubuğu kaynakları. **Araç çubuğu Düzenleyicisi** parçasıdır **Resim Düzenleyicisi**.|
|[Sürüm Bilgileri Düzenleyicisi](../windows/version-information-editor.md)|Visual C++ projelerinde sürüm bilgisi.|

> [!NOTE]
> Projenize bir .rc dosyası yoksa, lütfen bkz [nasıl yapılır: Kaynakları oluşturma](../windows/how-to-create-a-resource-script-file.md).

## <a name="view-and-edit-resources"></a>Görünümü ve düzenleme kaynakları

Her kaynak türü bu kaynak türü için belirli bir kaynak Düzenleyicisi sahiptir. Yeniden düzenleme, yeniden boyutlandırma, denetimleri ve Özellik Ekle veya aksi ilişkili Düzenleyicisi'ni kullanarak bir kaynak özelliklerini değiştirin. Bir kaynak olarak da düzenleyebilirsiniz [metin biçimi](../windows/how-to-open-a-resource-script-file-in-text-format.md) ve [ikili biçimi](../windows/opening-a-resource-for-binary-editing.md).

Bazı kaynak türleri içeri aktarıldı ve çeşitli şekillerde kullanılan tek dosyalardır; Bunlar, bit eşlemler, simgeler, işaretçiler, araç çubukları ve html dosyaları içerir. Böyle kaynaklar dosya adlarına sahip ve [kaynak tanımlayıcıları](../windows/symbols-resource-identifiers.md). Diğer iletişim kutuları, menüler ve Win32 projeleri, dize tablolarında gibi yalnızca bir kaynak betiği (.rc) veya kaynak şablonu (.rct) dosyasının parçası olarak mevcut.

Kaynakları da olabilir proje açmak zorunda kalmadan projenin dışında düzenlendi, bkz: [nasıl yapılır: Kaynakları oluşturma](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).

> [!NOTE]
> Kaynağın özelliklerini kullanarak değiştirilebilir **özellikleri** penceresi.

- Bir kaynağın özelliklerini düzenlemek için [kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources), seçin ve düzenlemek istediğiniz kaynağa sağ **özellikleri**.  Ardından [Özellikler penceresi](/visualstudio/ide/reference/properties-window), kaynak özelliklerini değiştirin.

- Bir kaynak özelliklerine yapılan bir değişikliği geri almak için kaynak odak sahip olduğundan emin olun **kaynak görünümü** ve **geri** gelen **Düzenle** menüsü.

### <a name="win32-resources"></a>Win32 kaynakları

Win32 kaynaklarında erişebileceğiniz [kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources) bölmesi.

#### <a name="to-view-a-win32-resource-in-a-resource-editor"></a>Bir Win32 kaynağı kaynak düzenleyicide görüntülemek için

1. Menü Git **görünümü** > **kaynak görünümü**.

1. Varsa **kaynak görünümü** penceresi seçin en üst penceresine değil **kaynak görünümü** dön getirmek için sekmesinde.

1. Gelen **kaynak görünümü**, görüntülemek istediğiniz kaynakları içeren proje klasörünü genişletin. Örneğin, bir iletişim kutusu kaynağı görüntülemek istiyorsanız, genişletme **iletişim** klasör.

1. Örneğin, kaynağa çift tıklatın **IDD_ABOUTBOX**.

   Kaynak uygun Düzenleyicisi'nde açılır. Örneğin, iç kaynak iletişim kutusu kaynakları için açılır **iletişim kutusu Düzenleyicisi**.

#### <a name="to-delete-an-existing-win32-resource"></a>Mevcut bir Win32 kaynağı silmek için

1. İçinde **kaynak görünümü**, bir kaynak türü için düğümü genişletin.

1. Sağ tıklayın ve silmek istediğiniz kaynak **Sil**.

> [!TIP]
> Bir belge penceresi dışında bir proje açın .rc dosyası varsa, bu yöntemi kullanabilirsiniz.

### <a name="managed-project-resources"></a>Yönetilen proje kaynakları

Yönetilen projelere kaynak betik dosyalarına kullanmayın çünkü kaynaklarınızdan açmalısınız **Çözüm Gezgini**. Kullanım [Resim Düzenleyicisi](../windows/image-editor-for-icons.md) ve [ikili düzenleyici](binary-editor.md) yönetilen projelerde kaynak dosyalarıyla çalışmak için. Düzenlemek istediğiniz yönetilen kaynaklar bağlı kaynaklar olmalıdır ve Visual Studio kaynak düzenleyicileri eklenmiş kaynakları düzenlemeyi desteklemez.

- Yönetilen kaynağı kaynak düzenleyicide görüntülemek için **Çözüm Gezgini**, kaynak, örneğin, çift *Bitmap1.bmp*, ve kaynak uygun Düzenleyicisi'nde açılır.

- Mevcut bir yönetilen kaynak silmek için **Çözüm Gezgini**, seçin ve silmek istediğiniz kaynağa sağ **Sil**.

## <a name="preview-resources"></a>Önizleme kaynakları

Kaynaklarınızı açmaya gerek kalmadan grafik kaynağı görüntülemek olanak Önizleme. Bunları, derlenmiş sonra kaynak tanımlayıcıları sayılara değiştiğinden Önizleme de yürütülebilir dosyalar için yararlıdır. Bu sayısal tanımlayıcıları genellikle yeterli bilgi sağlamayan olduğundan, kaynakları Önizleme hızlıca belirlemenize yardımcı olur.

Görsel düzeni önizlemesi aşağıdaki kaynak türlerini sağlar: Bit eşlem, iletişim, simge, menü, imleç ve araç çubuğu

Aşağıdaki kaynaklar, görüntü önizlemesini sağlaması gerekmez: Hızlandırıcı, dize tablosu bildirimi sürüm bilgisi

> [!NOTE]
> Kaynakları Önizleme için Win32 gerektirir.

### <a name="to-preview-resources"></a>Kaynakları Önizleme

1. İçinde [kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources) veya seçin, kaynak, örneğin, bir belge penceresi **IDD_ABOUTBOX**.

1. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window)seçin **özellik sayfaları** düğmesi.

   > [!TIP]
   > Bir kısayolu, menüsüne gidin **görünümü** > **özellik sayfaları**.

   **Özelliği** kaynak sayfasını açar, kaynak önizlemesi görüntüleniyor. Kullanabileceğiniz **yukarı** ve **aşağı** ağaç gezinmek için ok tuşlarını denetlemek de **kaynak görünümü** ya da belge penceresini. **Özelliği** sayfası açık kalır ve odaklı ve önizlenebilir herhangi bir kaynağa göster.

## <a name="requirements"></a>Gereksinimler

Yok.

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)<br/>
[Kaynak Dosyalar](../windows/resource-files-visual-studio.md)<br/>
[Kaynak Tanımlayıcıları (Semboller)](../windows/symbols-resource-identifiers.md)<br/>