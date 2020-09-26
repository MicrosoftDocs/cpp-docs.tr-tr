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
ms.openlocfilehash: 2552f9eea79aa0a3545d9746d85cacfbd9a3f25d
ms.sourcegitcommit: d9c94dcabd94537e304be0261b3263c2071b437b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2020
ms.locfileid: "91353174"
---
# <a name="resource-editors-c"></a>Kaynak Düzenleyicileri (C++)

Kaynak Düzenleyicisi, Visual Studio projesinde yer alan kaynakları oluşturmaya veya değiştirmeye yönelik özel bir ortamdır. Visual Studio kaynak düzenleyicileri, uygulama kaynaklarını hızlı ve kolay bir şekilde oluşturup değiştirmenize yardımcı olacak teknikleri ve arabirimleri paylaşır. Kaynak düzenleyicileri, uygun düzenleyicide ve önizleme kaynaklarında kaynakları görüntülemenizi ve düzenlemenizi sağlar.

Kaynak oluşturduğunuzda veya açtığınızda uygun düzenleyici otomatik olarak açılır.

> [!NOTE]
> Yönetilen projeler kaynak betik dosyalarını kullanmadığından, kaynaklarınızı **Çözüm Gezgini**açmalısınız. Yönetilen projelerde kaynak dosyalarıyla çalışmak için [resim düzenleyicisini](../windows/image-editor-for-icons.md) ve [ikili düzenleyiciyi](binary-editor.md) kullanabilirsiniz. Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır. Visual Studio kaynak düzenleyicileri eklenmiş kaynakları düzenlemeyi desteklemez.

|Kullanın...|Düzenlemek için...|
|----------------|----------------|
|[Hızlandırıcı düzenleyici](../windows/accelerator-editor.md)|Visual Studio C++ projelerinde Hızlandırıcı tabloları.|
|[İkili Düzenleyici](binary-editor.md)|Visual C++, Visual Basic veya Visual C# projelerindeki ikili veri bilgileri ve özel kaynaklar.|
|[İletişim kutusu Düzenleyicisi](../windows/dialog-editor.md)|Visual Studio C++ projelerindeki iletişim kutuları.|
|[Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)|Visual C++, Visual Basic veya Visual C# projelerindeki bit eşlemler, simgeler, imleçler ve diğer görüntü dosyaları.|
|[Menü Düzenleyicisi](../windows/menu-editor.md)|Visual Studio C++ projelerindeki menü kaynakları.|
|[Şerit Düzenleyicisi](../mfc/ribbon-designer-mfc.md)|MFC Projelerindeki Şerit kaynakları.|
|[Dize Düzenleyicisi](../windows/string-editor.md)|Visual Studio C++ projelerindeki dize tabloları.|
|[Araç Çubuğu Düzenleyicisi](../windows/toolbar-editor.md)|Visual Studio C++ projelerindeki araç çubuğu kaynakları. **Araç Çubuğu Düzenleyicisi** , **görüntü düzenleyicisinin**bir parçasıdır.|
|[Sürüm bilgileri Düzenleyicisi](../windows/version-information-editor.md)|Visual Studio C++ projelerindeki sürüm bilgileri.|

> [!NOTE]
> Projeniz zaten bir. rc dosyası içermiyorsa bkz. [nasıl yapılır: kaynak oluşturma](../windows/how-to-create-a-resource-script-file.md).

## <a name="view-and-edit-resources"></a>Kaynakları görüntüleme ve düzenleme

Her kaynak türünün bu kaynak türüne özgü bir kaynak Düzenleyicisi vardır. İlişkili düzenleyiciyi kullanarak bir kaynağın özelliklerini yeniden düzenleyebilir, yeniden boyutlandırabilir, denetim ve özellik ekleyebilir ya da başka bir şekilde değiştirebilirsiniz. Ayrıca, bir kaynağı metin biçiminde ve ikili biçimde düzenleyebilirsiniz. Daha fazla bilgi için bkz. [nasıl yapılır: kaynak oluşturma](../windows/how-to-create-a-resource-script-file.md).

Bazı kaynak türleri, içeri aktarılabilen ve çeşitli yollarla kullanılabilen tek dosyalardır. Bunlara bit eşlemler, simgeler, imleçler, araç çubukları ve HTML dosyaları dahildir. Bu tür kaynaklarda dosya adları ve [kaynak tanımlayıcıları](../windows/symbols-resource-identifiers.md)vardır. Win32 projelerindeki iletişim kutuları, menüler ve dize tabloları gibi diğerleri, yalnızca bir kaynak betiği (. RC) dosyasının veya kaynak şablonu (. rct) dosyasının bir parçası olarak mevcuttur.

Kaynaklar proje açık olmadan proje dışında da düzenlenebilir. Daha fazla bilgi için bkz. [nasıl yapılır: kaynak oluşturma](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).

> [!NOTE]
> Bir kaynağın özellikleri, **Özellikler** penceresi kullanılarak değiştirilebilir.

- Bir kaynağın özelliklerini düzenlemek için, [kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources), düzenlemek istediğiniz kaynağa sağ tıklayın ve **Özellikler**' i seçin.  Sonra, [Özellikler penceresi](/visualstudio/ide/reference/properties-window)kaynağınızın özelliklerini değiştirin.

- Bir kaynağın özelliklerine yapılan bir değişikliği geri almak için, kaynağınızın **kaynak görünümü** odaklanmış olduğundan emin olun ve **Düzenle** menüsünden **geri al** ' ı seçin.

### <a name="win32-resources"></a>Win32 kaynakları

[Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources) bölmesinde Win32 kaynaklarına erişebilirsiniz.

#### <a name="to-view-a-win32-resource-in-a-resource-editor"></a>Bir kaynak düzenleyicisinde Win32 kaynağını görüntülemek için

1. Menü **View**  >  **diğer Windows**  >  **kaynak görünümü**görüntüleme sayfasına gidin.

1. **Kaynak görünümü** pencere en üstteki pencere değilse, en üste getirmek için **kaynak görünümü** sekmesini seçin.

1. **Kaynak görünümü**, görüntülemek istediğiniz kaynakları içeren proje için klasörü genişletin. Örneğin, bir iletişim kaynağı görüntülemek istiyorsanız **Iletişim kutusu** klasörünü genişletin.

1. Kaynağa çift tıklayın, örneğin **IDD_ABOUTBOX**.

   Kaynak uygun düzenleyicide açılır. Örneğin, iletişim kutusu kaynakları için, kaynak **Iletişim kutusu Düzenleyicisi**içinde açılır.

#### <a name="to-delete-an-existing-win32-resource"></a>Mevcut bir Win32 kaynağını silmek için

1. **Kaynak görünümü**, bir kaynak türü için düğümünü genişletin.

1. Silmek istediğiniz kaynağa sağ tıklayın ve **Sil**' i seçin.

> [!TIP]
> Bu yöntemi,. RC dosyanızı proje dışındaki bir belge penceresinde açtığınızda de kullanabilirsiniz.

### <a name="managed-project-resources"></a>Yönetilen proje kaynakları

Yönetilen projeler kaynak betik dosyalarını kullanmadığından, kaynaklarınızı **Çözüm Gezgini**açmalısınız. Yönetilen projelerdeki kaynak dosyalarıyla çalışmak için [resim düzenleyicisini](../windows/image-editor-for-icons.md) ve [ikili düzenleyiciyi](binary-editor.md) kullanın. Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır ve Visual Studio kaynak düzenleyicileri gömülü kaynakları düzenlemeyi desteklemez.

- Bir kaynak düzenleyicisinde yönetilen bir kaynağı görüntülemek için, **Çözüm Gezgini**, kaynağa çift tıklayın, örneğin, *Bitmap1.bmp*ve kaynak uygun düzenleyicide açılır.

- Mevcut bir yönetilen kaynağı silmek için, **Çözüm Gezgini**, silmek istediğiniz kaynağa sağ tıklayın ve **Sil**' i seçin.

## <a name="preview-resources"></a>Kaynakları Önizle

Kaynakları açmadan grafik kaynağını görüntülemenize olanak tanımak için kaynaklarınızı önizleyin. Kaynak tanımlayıcıları sayılara değiştiğinden, bunları derledikten sonra da, önizleme, yürütülebilir dosyalar için de yararlıdır. Bu sayısal tanımlayıcılar genellikle yeterli bilgi sağlamadıklarından, kaynakların önizlemesi bunları hızlıca tanımanıza yardımcı olur.

Aşağıdaki kaynak türleri bir görsel düzen önizlemesi sağlar: bit eşlem, Iletişim kutusu, simge, menü, Imleç, araç çubuğu

Aşağıdaki kaynaklar görsel önizleme sağlamaz: Hızlandırıcı, bildirim, dize tablosu, sürüm bilgileri

> [!NOTE]
> Kaynakları önizlemek için Win32 gerekir.

### <a name="to-preview-resources"></a>Kaynakları önizlemek için

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources) veya belge penceresinde, kaynağı seçin, örneğin **IDD_ABOUTBOX**.

1. [Özellikler penceresi](/visualstudio/ide/reference/properties-window), **Özellik sayfaları** düğmesini seçin.

   > [!TIP]
   > Kısayol kullanın menüsünde menü **görünümü**  >  **Özellik sayfaları**' na gidin.

   Kaynak için **özellik** sayfası, bu kaynağın önizlemesini görüntüleyen açılır. **Kaynak görünümü** veya belge penceresinde ağaç denetiminde gezinmek için **yukarı** ve **aşağı** ok tuşlarını kullanabilirsiniz. **Özellik** sayfası açık kalır ve odaklanmış olan ve önizlenebilir tüm kaynakları gösterir.

## <a name="requirements"></a>Gereksinimler

Yok

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)<br/>
[Kaynak dosyaları](../windows/resource-files-visual-studio.md)<br/>
[Kaynak tanımlayıcıları (semboller)](../windows/symbols-resource-identifiers.md)<br/>
