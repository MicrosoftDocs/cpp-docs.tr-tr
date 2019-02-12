---
title: 'Nasıl yapılır: Kaynaklar (C++) oluştur'
ms.date: 11/04/2016
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
ms.openlocfilehash: 5a0bc6370d0973d63eb16ac992251531aa2e5193
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56152397"
---
# <a name="how-to-create-resources-c"></a>Nasıl yapılır: Kaynaklar (C++) oluştur

> [!NOTE]
> **Kaynak Düzenleyicisi** veya **kaynak görünümü** Express sürümlerinde kullanılamaz.
>
> Bu bilgi, kaynaklar Windows Masaüstü uygulamaları veya evrensel Windows platformu uygulamaları için geçerli değildir. .NET dilleri projelerde kaynak betik dosyalarına kullanmayın. Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [kaynak dosyaları](../windows/resource-files-visual-studio.md), [uygulama kaynaklarını ve kaynak yönetim sistemi](/windows/uwp/app-resources/), ve [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*.

## <a name="create-a-resource-script"></a>Kaynak betiği oluşturma

Önce oluşturun ve yeni kaynakları projenize ekleyin, kaynak betiği (.rc dosyası) oluşturmanız gerekir.

> [!NOTE]
> Kaynak betiği (.rc dosyası) yalnızca Visual Studio IDE'ye yüklenir, varolan bir projeye de ekleyebilirsiniz. Bir tek başına kaynak betiği (proje dışında) oluşturulamıyor. Kaynak şablonları (.rct dosyaları) dilediğiniz zaman oluşturulabilir.

### <a name="to-create-a-resource-script"></a>Kaynak betiği oluşturmak için

1. Mevcut proje klasörünüzde odak yerleştirin **Çözüm Gezgini**, örneğin, *MyProject*.

   > [!NOTE]
   > Proje klasörü çözüm klasöründe ile karıştırmayın **Çözüm Gezgini**. Odak moduna geçirirseniz **çözüm** klasörü, seçimlerinize **Yeni Öğe Ekle** iletişim kutusu farklı olacaktır.

1. Üzerinde **proje** menüsünde **Yeni Öğe Ekle**.

1. İçinde **Yeni Öğe Ekle** iletişim kutusunda **Visual C++** klasörü seçin **kaynak dosyası (.rc)** sağ bölmede.

1. Kaynak kodunuzu için bir ad sağlayın **adı** metin kutusuna ve ardından **açık**.

### <a name="to-open-a-resource-script"></a>Kaynak betiği açmak için

Bir proje açmak zorunda kalmadan, kaynakları bir kaynak betik görüntüleyebilirsiniz. Komut dosyasının'te açılmasını aksine bir belge penceresi açılır **kaynak görünümü** penceresi (dosya içinde bir proje açıkken çalıştığı gibi).

> [!NOTE]
> Bazı komutlar, yalnızca dosya açılan tek başına (proje dışında) olduğunda kullanılabilir. Tek başına bir dosya açıp, proje yüklemeden açmadan anlamına gelir.
>
> Örneğin, bir dosyayı farklı bir biçimde veya farklı bir dosya adı olarak kaydetmek için (olarak **Kaydet** komut dosyası içinde bir proje için kullanılamaz). İlk kullanarak projeyi açarsanız **dosya** > **açın** > **proje**, bu komutları kullanılamaz.

Proje dışındaki kaynak betik açmak için:

1. Gelen **dosya** menüsünde **açık**, ardından **dosya**.

1. İçinde **açık dosya** kaynak betik dosyasına gidin, dosyayı vurgulayın ve seçin iletişim kutusu, **açık**.

Proje dışındaki birden fazla kaynak komut dosyası açmak için:

1. Tek başına hem de kaynak dosyalarını açın. Örneğin, açmak *Source1.rc* ve *Source2.rc*.

1. Gelen **dosya** menüsünde seçin **açık**, ardından **dosya**.

1. İçinde **Dosya Aç** iletişim kutusunda, açmak istediğiniz ilk kaynak betik dosyasına gidin (*Source1.rc*), dosyayı vurgulayın ve seçme **açın**.

1. İkinci .rc dosyasını açmak için önceki adımı yineleyin (*Source2.rc*).

   .Rc dosyaları artık ayrı bir belge pencerelerinde açıktır.

1. Her iki .rc dosyası olduğunda açık, **penceresi** menü (veya .rc dosyaları sağ) seçin **yeni yatay sekme grubu** veya **yeni bir dikey sekme grubu**.

   Aynı anda görüntülemek için windows artık döşenmiş.

Belirli kaynak düzenleyicisinin içinde bir iletişim kutusu gibi bir kaynak açmaya gerek kalmadan proje kaynak betiği (.rc) dosyasının içeriğini görüntülemek istediğinizde zamanlar olabilir. Örneğin, her biri ayrı olarak açmak zorunda kalmadan kaynak dosyasındaki tüm iletişim kutuları arasında bir dize aramak isteyebilirsiniz.

Kaynak dosya, içerdiği tüm kaynakları görüntülemek ve metin düzenleyicisi tarafından desteklenen genel işlemleri tamamlamak için metin biçiminde kolayca açabilirsiniz.

> [!NOTE]
> Kaynak düzenleyicileri .rc doğrudan okunmaz veya `resource.h` dosyaları. Kaynak Derleyicisi bunları kaynak düzenleyicileri tarafından tüketilen .aps dosyalarına derlenir. Bu dosya, bir derleme adımdır ve yalnızca sembolik verileri depolar. (Örneğin, açıklamalar) sembolik değil bilgi işlem ile normal bir derleme olarak derleme işlemi sırasında göz ardı edilir. .Rc dosyasıyla .aps dosyası zaman uyumsuz olarak alır her .rc dosyası yeniden oluşturuldu (kaydettiğinizde, örneğin, kaynak düzenleyicisini .rc dosyasının üzerine yazar ve `resource.h` dosyası). Herhangi bir değişiklik kaynaklardaki .rc dosyasına eklenen kalır ancak .rc dosyasının üzerine sonra açıklamaları kaybolur. Açıklamaları koruma hakkında daha fazla bilgi için bkz: [derleme sırasında kaynak ekleme](../windows/how-to-include-resources-at-compile-time.md).

Kaynak betik dosyasını metin biçiminde açma için:

1. Gelen **dosya** menüsünü seçin **açık**, ardından **dosya**.

1. İçinde **açık dosya** iletişim kutusunda, metin biçiminde görüntülemek istediğiniz kaynak betik dosyasına gidin.

1. Dosyayı vurgulayın ve ardından açılan liste okunu seçin **açık** düğme (düğme sağ taraftaki).

1. Seçin **birlikte Aç** aşağı açılan menüden.

1. İçinde **birlikte Aç** iletişim kutusunda **kaynak kodu (metin) Düzenleyicisi**.

1. Gelen **açık olarak** aşağı açılan listesinden **metin**.

   Kaynak açılır **kaynak kodu** Düzenleyici.

> [!TIP]
> .Rc dosyasına sağ kısayoldur **Çözüm Gezgini**, seçin **birlikte Aç...**  seçip **kaynak kodu (metin) Düzenleyicisi**.

### <a name="to-add-mfc-support"></a>MFC desteği eklemek için

Normalde, kullanarak Windows için Microsoft Foundation Class (MFC) uygulama derleme, [MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md), sihirbaz'in temel özellikleri içeren dosyaları (kaynak betiği (.rc) dosyası dahil) temel bir dizi oluşturur. MFC. Ancak, MFC'ye dayalı olmayan bir Windows uygulaması için bir .rc dosyası düzenlenirken, aşağıdaki MFC özellikler kullanılamaz:

MFC için belirli bazı özellikler, MFC kodu sihirbazları, menü komut istemi dizeleri, birleşik giriş kutusu denetimleri ve ActiveX denetimi barındırma için Liste içeriği içerir.

Kaynak betik dosyası için MFC desteği eklemek için:

1. Kaynak betik dosyasını açın.

1. İçinde **kaynak görünümü**, Kaynaklar klasörünü vurgulayın (örneğin, *MFC.rc*).

1. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window)ayarlayın **MFC modu** özelliğini **True**.

   > [!NOTE]
   > Bu özellik ayarlamanın yanı sıra .rc dosyası bir MFC projesinin bir parçası olmalıdır. Örneğin, yalnızca ayarlamak **MFC modu** için **True** üzerinde bir .rc dosyası bir Win32 projesindeki MFC özellikleri vermeyecektir.

## <a name="create-a-resource"></a>Kaynak oluşturma

Yeni bir varsayılan kaynak (bir şablona bağlı olmayan bir kaynak) veya bir şablon sonra desenli bir kaynak olarak bir kaynak oluşturabilirsiniz.

Yeni bir kaynak oluşturduğunuzda, Visual C++ benzersiz bir ad, örneğin atar `IDD_Dialog1`. Bu kaynak kimliği için ilişkili kaynak Düzenleyicisi'ni veya kaynak özellikleri düzenleyerek özelleştirebilirsiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window).

> [!NOTE]
> Visual Studio tarafından ayrılmış bir kaynak adı ya belirtmeyin. Ayrılmış adları DESIGNINFO, HWB, ve TEXTINCLUDE ve ayırtılmış ID 255tir.

**Kaynak görünümü** penceresi, kaynak dosyaları projenize dahil görüntüler. En üst düzey klasör genişletme (örneğin, *Project1.rc*) dosya ve her kaynak türünün genişleterek o türün her bir kaynağın gösterir içindeki kaynak türleri gösterir.

> [!TIP]
> Kaynak Görünümü penceresi açmak için seçmeniz **kaynak görünümü** üzerinde **görünümü** menü (veya **Ctrl** + **Shift**  +  **E**).
>
> Kullanım sağ **kaynak görünümü** penceresini komutları kısayol menüsü başlatın veya sabitlemek veya pencerenin çıkarmak için başlık çubuğunu çift tıklatın. Başlık çubuğunun sağ pencereyi davranışını denetlemenize izin ek komutlar sağlar. Daha fazla bilgi için [Windows Yönetim](/visualstudio/ide/customizing-window-layouts-in-visual-studio).

Kullanım **kaynak Ekle** iletişim kutusunda, aşağıdaki özelliklere sahip bir C++ Windows masaüstü uygulaması projesi kaynak eklemek için:

|Özellik|Açıklama|
|-|-|
|**Kaynak Türü**|Oluşturmak istediğiniz kaynak türünü belirtir.<br/><br/>Ek kaynaklar ortaya çıkarmak için imleç ve iletişim kutusunu kaynak kategorileri genişletebilirsiniz. Bu kaynaklar ...\Microsoft Visual Studio içinde bulunan \<sürüm\>\VC\VCResourceTemplates\\< LCID\>\mfc.rct. .Rct dosyaları eklerseniz, bunları bu dizine yerleştirin veya başka bir tane belirtin [yolunu](../windows/how-to-specify-include-directories-for-resources.md). Daha sonra bu dosyalarındaki kaynaklar ikinci düzeyde uygun kategorisi altında görünür. Ekleyebileceğiniz .rct dosyaları sayısı önceden belirlenmiş bir sınır yoktur.<br/><br/>Ağaç denetimi üst düzeyde gösterilen kaynağı Visual Studio tarafından sağlanan varsayılan kaynaklardır.|
|**Yeni**|Seçili türüne göre bir kaynak oluşturur **kaynak türü** kutusuna ve kaynak uygun Düzenleyicisi'nde açılır. Bir iletişim kutusu kaynağı oluşturursanız, örneğin, açılır [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md).|
|**İçeri Aktar**|Açılır **alma** geçerli projenize aktarmak istediğiniz yere gidebilirsiniz kaynağa, iletişim kutusu. Aktarabilirsiniz bir bit eşlem simgesi, imleç, HTML, ses (. WAV) veya özel kaynak dosyası.|
|**Özel**|Açılır **yeni özel kaynak** özel bir kaynak oluşturabileceğiniz bir iletişim kutusu. Özel kaynaklar ikili düzenleyicide yalnızca düzenlenebilir.|

Kullanım **yeni özel kaynak** iletişim kutusu, bir C++ projesinde aşağıdaki özelliklerle yeni bir özel kaynak oluşturmak için:

|Özellik|Açıklama|
|-|-|
|**Kaynak Türü**|Özel kaynak türü adını girmek için metin kutusu sağlar. Visual C++, çıktığınızda adı otomatik olarak büyük **yeni özel kaynak** iletişim kutusu.|

### <a name="to-create-a-new-resource"></a>Yeni bir kaynak oluşturmak için

Aşağıdakileri kullanarak yeni bir kaynak oluşturabilirsiniz:

- İçinde **kaynak görünümü**, .rc dosyanızı seçin ve ardından seçin **Düzenle** menüsünü seçip **kaynak Ekle**. İçinde **kaynak Ekle** iletişim kutusunda, projenize eklemek istediğiniz kaynak türünü seçin.

   > [!TIP]
   > Ayrıca bir .rc dosyasında sağ **kaynak görünümü** ve **kaynak Ekle** kısayol menüsünden.

- İçinde **Çözüm Gezgini**, proje klasörü sağ tıklatın ve seçin **Ekle**, ardından **kaynak Ekle** kısayol menüsünde. İçinde **kaynak Ekle** iletişim kutusunda, projenize eklemek istediğiniz kaynak türünü seçin.

   > [!NOTE]
   > Bu adım, projenizde zaten bir .rc dosyası yoksa oluşturur. Sonra belirli kaynak türlerine yeni .rc dosyasına eklemek için bu adımı yineleyebilirsiniz.

- İçinde [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code)sınıfınıza sağ tıklatın ve seçin **Ekle**. Seçin **kaynak Ekle** kısayol menüsünden ve projenize eklemek istediğiniz kaynak türünü seçin.

- İçinde **proje** menüsünde seçin **kaynak Ekle**.

## <a name="create-a-resource-template"></a>Kaynak şablonu oluştur

Kaynak şablon bir .rct dosyası olarak kaydettiğiniz bir özelleştirilmiş bir kaynaktır. Kaynak şablonu, ardından kaynakları oluşturmak için bir başlangıç noktası olarak görev yapar. Kaynak şablonları, ek kaynaklar veya standart denetimler gibi özellikleri paylaşmaz veya öğeleri yinelenen kaynak gruplarını geliştirmede zamandan tasarruf edin. Örneğin, birçok iletişim kutularında Yardım düğmeye sahip bir şirket logosu simgesi dahil etmek istiyorsanız, yeni bir iletişim kutusu şablonu oluşturun ve Yardım düğmesini ve logosu ile özelleştirebilir.

Kaynak şablonu özelleştirdikten sonra şablonu klasörüne (veya INCLUDE yolu belirtilen konuma) yaptığınız değişiklikleri kaydedin, böylece yeni kaynak şablonu kaynak türüne altında görünür **kaynak Ekle** iletişim kutusu. Artık yeni kaynak şablonu sıklıkta gerektiği şekilde kullanabilirsiniz.

> [!NOTE]
> Kaynak Düzenleyicisi bir kaynağın benzersiz kimliği otomatik olarak sağlar. Düzeltebilir [kaynak özellikleri](../windows/changing-the-properties-of-a-resource.md) gerektiğinde.

> [!NOTE]
> Dile özgü şablon dosyaları ana şablon dizininin alt dizinlerde yerleştirin. Örneğin, yalnızca İngilizce şablon dosyalarında yerleştirmek... \\< kaynak şablon dizini\>\1033. Visual Studio, Visual Studio \Program yeni RCT dosyaları arar \<sürüm\>\Program Visual Studio içinde \VC\VCResourceTemplates \<sürüm > \VC\VCResourceTemplates\\< LCID\> (örneğin, 1033 İngilizce) *veya* yerinde [yolunu](../windows/how-to-specify-include-directories-for-resources.md). Başka bir konumda, örneğin Belgelerim RCT dosyalarınızı depolamak isterseniz Visual Studio RCT dosyanızı bulabilmesi için bu klasör yoluna eklemeniz gerekir.

### <a name="to-create-a-resource-template"></a>Kaynak şablonu oluşturmak için

1. İçinde **Çözüm Gezgini**, projenize sağ tıklayın.

1. Kısayol menüsünden seçin **Ekle**, ardından **Yeni Öğe Ekle**.

1. İçinde **Yeni Öğe Ekle** iletişim kutusundaki **şablonları:** bölmesinde **kaynak şablon dosyası (.rct)**.

1. Bir ad ve yeni .rct dosyanız için bir konum girin ve seçin **açık**.

   Yeni .rct dosyası projenize eklenir ve görünür **Çözüm Gezgini** altında **kaynakları** klasör.

1. Bu belge penceresinde .rct dosyasına çift tıklayarak açın. Kaynakları eklemek için belge penceresinde dosyasını sağ tıklatın ve seçin **kaynak Ekle**.

   Bu kaynaklar özelleştirebilir ve .rct dosyayı kaydedin.

### <a name="to-convert-an-existing-resource-file-to-a-template"></a>Mevcut bir kaynak dosyası için bir şablonu dönüştürmek için

1. Tek başına bir dosya olarak .rc dosyasını açın.

1. Üzerinde **dosya** menüsünde **Kaydet \< *filename*> olarak**.

1. Bir konum belirtin ve seçin **Tamam**.

### <a name="to-create-a-new-resource-from-a-template"></a>Bir şablondan yeni bir kaynak oluşturmak için

1. İçinde **kaynak görünümü** bölmesinde .rc dosyasını sağ tıklatın ve seçin **kaynak Ekle** kısayol menüsünden.

1. İçinde **kaynak Ekle** iletişim kutusunda, artı işaretini seçin (**+**) kaynak düğümünü genişletin ve o kaynak için kullanılabilir tüm şablonları görüntülemek için bir kaynak yanında.

1. Kullanmak istediğiniz şablonu çift tıklatın.

1. Eklenen kaynak, kaynak düzenleyicisinde gerektiği gibi değiştirin.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak dosyaları](../windows/resource-files-visual-studio.md)<br/>
[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)<br/>