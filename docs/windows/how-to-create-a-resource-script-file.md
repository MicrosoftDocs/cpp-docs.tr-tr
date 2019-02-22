---
title: 'Nasıl yapılır: Kaynaklar (C++) oluştur'
ms.date: 02/14/2019
f1_keywords:
- vc.editors.resource
- vc.resvw.add.MFC
- vs.resourceview.F1
- vc.editors.insertresource
- vc.editors.newcustomresource
helpviewer_keywords:
- rc files [C++], creating
- .rc files [C++], creating
- resource script files [C++], creating
- resources [C++], viewing
- rc files [C++], viewing resources
- .rc files [C++], viewing resources
- resource script files [C++], viewing resources
- resource script files [C++], opening in text format
- .rc files [C++], opening in text format
- rc files [C++], opening in text format
- rc files [C++], adding MFC support
- .rc files [C++], adding MFC support
- MFC, adding support to resource scripts files
- resource script files [C++], adding MFC support
- toolbars [C++], resources
- resource toolbars
- resources [C++], creating
- Resource View window
- resources [C++], adding
- Add Resource dialog box [C++]
- Custom Resource Type dialog box [C++]
- language-specific template files [C++]
- resource templates
- rct files [C++]
- templates, resource templates
- resources [C++], templates
- .rct files [C++]
ms.assetid: 82be732a-cdcd-4a58-8de7-976d1418f86b
ms.openlocfilehash: 768675a878891ebb75c7f42c12eae8dfcfa3510b
ms.sourcegitcommit: e540706f4e2675e7f597cfc5b4f8dde648b007bb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56676493"
---
# <a name="how-to-create-resources-c"></a>Nasıl yapılır: Kaynaklar (C++) oluştur

Projeniz tarafından için kaynakları oluşturabilirsiniz:

- Kaynak betik dosyasını kullanarak. Kaynakları eklemeden önce bu adım gereklidir.

- Kaynakları projenize ekleme. Bu adımı nasıl kullanılacağını gösterir **kaynak görünümü**.

- Özelleştirilmiş kaynakları oluşturmak için bir kaynak şablonu kullanarak.

> [!NOTE]
> **Kaynak Düzenleyicisi** ve **kaynak görünümü** Express sürümlerinde kullanılamaz.

## <a name="use-resource-script-files"></a>Kaynak betik dosyalarına kullanın

Önce oluşturun ve yeni kaynakları projenize ekleyin, bir kaynak betiği (.rc) dosyası oluşturmanız gerekir.

> [!NOTE]
> Yalnızca, Visual Studio IDE'ye yüklü mevcut bir projeyi kaynak betiği ekleyebilirsiniz. Kaynak şablonları (.rct dosyaları) dilediğiniz zaman oluşturulabilir olsa, proje dışında bir tek başına kaynak komut dosyası oluşturulamıyor.

### <a name="to-create-a-resource-script-file"></a>Kaynak betik dosyasını oluşturmak için

1. Mevcut proje klasörünüzde odak yerleştirin **Çözüm Gezgini**, örneğin, *MyProject*.

   > [!NOTE]
   > Proje klasörü çözüm klasöründe ile karıştırmayın **Çözüm Gezgini**. Odak moduna geçirirseniz **çözüm** klasörü, aynı olmayacaktır **Yeni Öğe Ekle** seçenekleri.

1. Menüde, Git **proje** > **Yeni Öğe Ekle**.

1. Seçin **Visual C++** klasörü seçin **kaynak dosyası (.rc)** sağ bölmede.

1. Kaynak kod dosyanız için bir ad sağlayın **adı** metin kutusu ve select **açık**.

### <a name="to-open-a-resource-script-file"></a>Kaynak betik dosyasını açmak için

Açık bir projeniz zorunda kalmadan, kaynakları bir kaynak betik dosyasında görüntüleyebilirsiniz. Komut dosyası olarak bir belge penceresi açılır **kaynak görünümü**.

> [!NOTE]
> Bazı komutlar, yalnızca dosya proje dışındaki veya ilk proje yüklenirken olmadan anlamı açılan tek başına ise kullanılabilir. Örneğin, kullanılacak **Kaydet** komutu ile farklı bir biçimi veya dosya adı bir dosyaya kaydetmek için açılan tek başına dosya olmalıdır.

- Menüde, proje dışındaki kaynak betik dosyasını açmak için Git **dosya** > **açın**ve **dosya**. Ardından kaynak betik dosyasına gidin, dosyayı vurgulayın ve seçme **açık**.

  - Kaynak betik dosyasını metin biçiminde açma için sağ tarafında açılan liste okunu kullanın **açın** seçin ve Yukarıdaki adımda düğmesini **birlikte Aç**. Ardından **kaynak kodu (metin) Düzenleyicisi** ve **açık olarak** aşağı açılan listesinden **metin**, ve kaynak açılır **kaynak kodu**Düzenleyici.

    > [!NOTE]
    > Bir kaynak açmak için kaynak düzenleyicileri kullanmadan projenizin kaynak betik dosyası içeriğini görüntülemek istediğinizde zamanlar olabilir. Örneğin, her biri ayrı olarak açmak zorunda kalmadan kaynak dosyasındaki tüm iletişim kutuları arasında bir dize aramak isteyebilirsiniz. Kaynak dosya, içerdiği tüm kaynakları görüntülemek ve metin düzenleyicisi tarafından desteklenen genel işlemleri tamamlamak için metin biçiminde kolayca açabilirsiniz.

- Birden çok kaynak açmak için komut dosyaları, açmak istediğiniz, örneğin, her dosya için yukarıdaki adımları izleyin *Source1.rc* ve *Source2.rc*. Daha sonra her iki .rc dosyası ayrı belgeler windows açık olduğunda, ya da kullanın **penceresi** menüsü veya .rc dosyalarından birine sağ tıklayıp seçin **yeni yatay sekme grubu** veya **yeni bir dikey sekme Grup**. Aynı anda görüntülemek için windows artık döşenmiş.

> [!TIP]
> Kaynak betik dosyalarına .rc dosyasına sağ tıklayarak da açabilirsiniz **Çözüm Gezgini**seçip **birlikte Aç...**  seçerek **kaynak kodu (metin) Düzenleyicisi**.

### <a name="to-edit-a-resource-script-file"></a>Kaynak betik dosyasını düzenlemek için

- Menüde açık kaynak komut dosyası ile bir şablon için varolan bir kaynak dosyasını dönüştürmek için Git **dosya** > **Kaydet \< *filename*>olarak**. Ardından, bir konum belirtin ve seçin **Tamam**.

Kullanarak Windows için Microsoft Foundation Class (MFC) uygulama oluşturduğunuzda [MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md), sihirbaz dosyaları kaynak betiği (.rc) dosyası da dahil olmak üzere temel kümesini oluşturur), MFC'in temel özellikleri içerir. Ancak, MFC'ye dayalı olmayan Windows uygulamaları için bir .rc dosyasını düzenlerken bu MFC özgü özellikler kullanılamaz. Bu kod sihirbazları, menü komut istemi dizeleri, birleşik giriş kutusu denetimleri ve ActiveX denetimi barındırma için Liste içeriği içerir.

- MFC desteği, kaynak kod dosyasını açın, buna eklemek için **kaynak görünümü**, Kaynaklar klasörünü vurgulayın (örneğin, *MFC.rc*). Ardından [Özellikler penceresi](/visualstudio/ide/reference/properties-window)ayarlayın **MFC modu** için **True**.

  > [!NOTE]
  > Ek olarak **MFC modu**, .rc dosyasının bir MFC projesinin bir parçası olması gerekir. Yalnızca ayarlama **MFC modu** için **True** üzerinde bir .rc dosyası bir Win32 projesindeki MFC özellikleri vermeyecektir.

## <a name="create-resources"></a>Kaynakları oluşturma

Bir kaynak bir şablona bağlı olmayan bir kaynak anlamı, yeni bir varsayılan kaynak olarak ya da bir şablon sonra desenli bir kaynak olarak oluşturabilirsiniz.

Kullanım **kaynak görünümü** projelerinizde bulunan kaynak dosyaları görüntülemek için penceresi. Üst klasör için genişletme *Project1.rc*, bu dosyanın içindeki kaynak türlerini gösterir. Her bir kaynak türü, bu türdeki tek tek kaynakları göstermek için genişletin.

> [!TIP]
> Açmak için **kaynak görünümü** penceresinde menüsüne gidin **görünümü** > **kaynak görünümü** veya basın **Ctrl** +  **Shift**+**E**.

Sağ tıklama kullanabileceğiniz **kaynak görünümü** penceresi komutların kısayol menüsünü başlatma ya da pencere çıkar ve yerleştirme için başlık çubuğunu çift tıklatın. Pencere davranışını denetleyen ek komutlar için başlık çubuğunun sağ tıklayın. Daha fazla bilgi için [Windows Yönetim](/visualstudio/ide/customizing-window-layouts-in-visual-studio).

**Kaynak görünümü** windows içerir **kaynak Ekle** iletişim kutusu kaynakları bir C++ Windows masaüstü uygulaması projesine eklemek için aşağıdaki özelliklere sahip:

| Özellik | Açıklama |
|---|---|
| **Kaynak Türü** | Oluşturmak istediğiniz kaynak türünü belirtin.<br/><br/>Visual Studio ...\Microsoft içinde bulunan ek kaynaklar ortaya çıkarmak için imleç ve iletişim kutusunu kaynak kategorileri genişletebilirsiniz \<sürüm\>\VC\VCResourceTemplates\\< LCID\>\mfc.rct. .Rct dosyaları eklemeniz gerekiyorsa, buraya yerleştirin veya başka bir tane belirtin [yolunu](../windows/how-to-specify-include-directories-for-resources.md).<br/><br/>Ağaç denetimi üst düzeyde gösterilen kaynağı, Visual Studio tarafından sağlanan varsayılan kaynaklardır. .Rct dosyalarındaki kaynaklar ikinci düzey uygun kategorisinin altında görünür. Ekleyebileceğiniz .rct dosyaları sayısı önceden belirlenmiş bir sınır yoktur.<br/><br/> |
| **Yeni** | Seçili türüne göre kaynak Oluştur **kaynak türü** kutusuna ve kaynak uygun Düzenleyicisi'nde açın.<br/><br/>Örneğin, bir iletişim kutusu kaynağı oluşturursanız, kaynakta açar [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md). |
| **İçeri Aktar** | Açık **alma** iletişim kutusu, geçerli projenin içine aktarmak istediğiniz kaynağa gidin.<br/><br/>Aktarabilirsiniz bir bit eşlem simgesi, imleç, HTML, ses (. WAV) veya özel kaynak dosyası. |
| **Özel** | Açık **yeni özel kaynak** özel bir kaynak oluşturmak için iletişim kutusu.<br/><br/>Ayrıca içeren bir **kaynak türü** özel kaynak türü adını girmek metin kutusu sağlayan bir özellik. Çıkış, visual C++ otomatik olarak ad büyük harfe dönüştürür.<br/><br/>Özel kaynaklar ikili düzenleyicide yalnızca düzenlenebilir. |

Yeni bir kaynak oluşturduğunuzda, Visual C++ benzersiz bir ad, örneğin atar `IDD_Dialog1`. Bu kaynak kimliği, ilişkili kaynak Düzenleyicisi'ni veya kaynak özellikleri düzenleyerek özelleştirebilirsiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window).

> [!NOTE]
> Visual Studio tarafından ayrılmış bir kaynak adı ya belirtmeyin. Ayrılmış adlar `DESIGNINFO`, `HWB`, ve `TEXTINCLUDE`, ve ayırtılan ID `255`.

Bir kaynak kullanımı aşağıdakilerden birini oluşturmak için:

- İçinde **kaynak görünümü**.rc dosyanızı seçin ve ardından kullanmak **Düzenle** > **kaynak Ekle** ve projenize eklemek için kaynak türünü seçin.

   > [!TIP]
   > Ayrıca bir .rc dosyasında sağ **kaynak görünümü** ve **kaynak Ekle** kısayol menüsünden.

- İçinde **Çözüm Gezgini**, proje klasörüne sağ tıklayın, **Ekle** > **kaynak Ekle** ve projenize eklemek için kaynak türünü seçin.

   > [!NOTE]
   > Bu adım, projenizde zaten bir .rc dosyası yoksa oluşturur. Sonra belirli kaynak türlerine yeni .rc dosyasına eklemek için bu adımı yineleyebilirsiniz.

- İçinde [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code), sınıf sağ tıklayın, **Ekle** > **kaynak Ekle** ve projenize eklemek için kaynak türünü seçin.

- Menüyü kullanın **proje** > **kaynak Ekle**.

## <a name="use-resource-templates"></a>Kaynak şablonlarını kullanma

Kaynak şablon bir .rct dosyası olarak kaydettiğiniz bir özelleştirilmiş bir kaynaktır. Kaynak şablonu, ardından kaynakları oluşturmak için bir başlangıç noktası olarak görev yapar. Kaynak şablonları, ek kaynaklar veya standart denetimler gibi özellikleri paylaşmaz veya öğeleri yinelenen kaynak gruplarını geliştirmede zamandan tasarruf edin. Örneğin, birçok iletişim kutularında Yardım düğmeye sahip bir şirket logosu simgesi dahil etmek istiyorsanız, yeni bir iletişim kutusu şablonu oluşturun ve Yardım düğmesini ve logosu ile özelleştirebilir.

Yeni kaynak şablonu kaynak türüne altında görünmesi için kaynak şablonunu özelleştirdikten sonra değişikliklerinizi şablon klasöründe veya dahil etme yolunda belirtilen konuma kaydetmek **kaynak Ekle** iletişim kutusu. Artık yeni kaynak şablonu sıklıkta gerektiği şekilde kullanabilirsiniz.

> [!NOTE]
> Kaynak Düzenleyicisi bir kaynağın benzersiz kimliği otomatik olarak sağlar. Düzeltebilir [kaynak özellikleri](../windows/changing-the-properties-of-a-resource.md) gerektiğinde.

> [!NOTE]
> Dile özgü şablon dosyaları ana şablon dizininin alt dizinlerde yerleştirin. Örneğin, yalnızca İngilizce şablon dosyaları Git... \\< kaynak şablon dizini\>\1033. Visual Studio, Visual Studio \Program yeni .rct dosyaları arar \<sürüm\>\VC\VCResourceTemplates, Visual Studio \Program \<sürüm > \VC\VCResourceTemplates\\< LCID\> (örneğin, bir LCID için İngilizce 1033), veya herhangi bir yerinde [yolunu](../windows/how-to-specify-include-directories-for-resources.md). .Rct dosyaları başka bir konumda saklamak isterseniz, konum yoluna eklemeniz gerekir.

### <a name="to-create-and-use-a-resource-template"></a>Oluşturma ve kaynak şablonu kullanma

1. İçinde **Çözüm Gezgini**, projenize sağ tıklayın.

1. Kısayol menüsünden seçin **Ekle** > **Yeni Öğe Ekle**.

1. İçinde **şablonları:** bölmesinde **kaynak şablon dosyası (.rct)**.

1. Bir ad ve yeni .rct dosyanız için bir konum girin ve seçin **açık**.

   Yeni .rct dosyası projenize eklenir ve görünür **Çözüm Gezgini** altında **kaynakları** klasör.

1. Bu belge penceresinde .rct dosyasına çift tıklayarak açın. Kaynakları eklemek için belge penceresinde dosyasını sağ tıklatın ve seçin **kaynak Ekle**.

   Eklenen kaynaklarınızı özelleştirebilir ve .rct dosyayı kaydedin.

1. İçinde **kaynak görünümü** bölmesinde .rc dosyasını sağ tıklatın ve seçin **kaynak Ekle**.

1. Artı işaretini seçin (**+**) kaynak düğümünü genişletin ve o kaynak için kullanılabilir şablonları görüntülemek için bir kaynak yanında.

1. Kullanmak istediğiniz şablonu çift tıklatın.

   Eklenen kaynak, kaynak düzenleyicisinde gerektiği gibi değiştirebilirsiniz.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Dosyalar](../windows/resource-files-visual-studio.md)<br/>
[Nasıl yapılır: Kaynakları yönet](../windows/how-to-copy-resources.md)<br/>
[Nasıl yapılır: Derleme Sırasında Kaynak Ekleme](../windows/how-to-include-resources-at-compile-time.md)<br/>