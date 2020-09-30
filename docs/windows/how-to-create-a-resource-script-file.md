---
title: 'Nasıl yapılır: kaynak oluşturma (C++)'
ms.date: 02/14/2019
f1_keywords:
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
ms.openlocfilehash: 88618a5b1184ce9774a58f575a3fbff2d5e63ba4
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91504422"
---
# <a name="how-to-create-resources-c"></a>Nasıl yapılır: kaynak oluşturma (C++)

Projeniz için şu şekilde kaynak oluşturabilirsiniz:

- Kaynak betik dosyası kullanma.

   > [!NOTE]
   > Kaynak eklemeden önce Bu adım gereklidir.

- Projenize kaynak ekleme ve **kaynak görünümü**kullanma.

- Özelleştirilmiş kaynaklar oluşturmak için bir kaynak şablonu kullanma.

## <a name="use-resource-script-files"></a>Kaynak betik dosyalarını kullan

Projenize yeni kaynaklar oluşturup eklemeden önce, önce bir kaynak betiği (. RC) dosyası oluşturmanız gerekir.

> [!NOTE]
> Yalnızca Visual Studio IDE 'ye yüklenmiş var olan bir projeye kaynak betik dosyası ekleyebilirsiniz. Kaynak şablonu (. rct) dosyaları her zaman oluşturulabilse de, proje dışında tek başına kaynak betiği oluşturamazsınız.

### <a name="to-create-a-resource-script-file"></a>Kaynak betik dosyası oluşturmak için

1. **Çözüm Gezgini**, örneğin *MyProject*gibi mevcut proje klasörünüze odaklayın.

   > [!NOTE]
   > Proje klasörünü **Çözüm Gezgini**çözüm klasörüyle karıştırmayın. **Çözümü çözüm** klasörüne yerleştirirseniz, aynı **Yeni öğe Ekle** seçeneklerine sahip kalmazsınız.

1. Menüsünde **Proje**  >  **Yeni öğe Ekle**' ye gidin.

1. **Visual C++** klasörü seçin ve sağ bölmedeki **kaynak dosyası (. RC)** öğesini seçin.

1. **Ad** metin kutusuna kaynak betik dosyanız için bir ad girin ve **Aç**' ı seçin.

### <a name="to-open-a-resource-script-file"></a>Kaynak betik dosyasını açmak için

Bir proje açık olmadan kaynak betik dosyasındaki kaynakları görüntüleyebilirsiniz. Betik dosyası, **kaynak görünümü**aksine bir belge penceresinde açılır.

> [!NOTE]
> Bazı komutlar yalnızca dosya tek başına açılırsa kullanılabilir, yani proje, önce projeyi yüklemeden bir proje dışında. Örneğin, farklı **Kaydet** komutunu kullanmak ve bir dosyayı farklı biçimde veya dosya adıyla kaydetmek için, dosyanın tek başına açılmalıdır.

- Bir kaynak betik dosyasını bir proje dışında açmak için, menüde **Dosya**  >  **Aç**' a gidin ve **Dosya**' yı seçin. Kaynak betik dosyasına gidin, dosyayı vurgulayın ve **Aç**' ı seçin.

    > [!NOTE]
    > Bir kaynağı açmak için kaynak düzenleyicilerini kullanmadan projenizin kaynak betik dosyasının içeriğini görüntülemek istediğiniz zamanlar olabilir. Örneğin, her birini ayrı ayrı açmak zorunda kalmadan kaynak dosyasındaki tüm iletişim kutularında bir dizeyi aramak isteyebilirsiniz. İçerdiği tüm kaynakları ve metin düzenleyici tarafından desteklenen genel işlemleri görüntülemek için kaynak dosyasını metin biçiminde kolayca açabilirsiniz.
    >
    > Bir kaynak betik dosyasını metin biçiminde açmak için yukarıdaki adımda **Aç** düğmesinin sağ tarafındaki açılır oku kullanın ve **birlikte Aç**' ı seçin. **Kaynak kodu (metin) düzenleyicisini** seçin ve **Aç** açılan listesinden **metin** ' i seçin ve kaynak **kod** düzenleyicisinde açılır.

- Birden çok kaynak komut dosyası açmak için, açmak istediğiniz her dosya için yukarıdaki aynı adımı izleyin, örneğin, *Source1. RC* ve *source2. RC*. Sonra, her iki. rc dosyası ayrı belgeler **penceresinde** açık olduğunda, pencere menüsünü kullanın veya dosyalardan birine sağ tıklayıp **Yeni yatay sekme grubu** ya da **Yeni dikey sekme grubu**' nu seçin. Pencereler artık aynı anda görüntüleyebilmeniz için döşenir.

> [!TIP]
> Kaynak betik dosyalarını **Çözüm Gezgini**' de. rc dosyasına sağ tıklayıp, **birlikte Aç** ' ı seçerek **kaynak kodu (metin) Düzenleyicisi**' ni seçebilirsiniz.

[MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md)'Nı kullanarak Windows Için bir Microsoft Foundation Class (MFC) uygulaması oluşturduğunuzda, sihirbaz MFC 'nin temel özelliklerini içeren bir kaynak betiği (. RC) dosyası gibi temel bir dosya kümesi oluşturur. Ancak, MFC 'ye bağlı olmayan Windows uygulamaları için bir. rc dosyası düzenlenirken bu MFC 'ye özgü özellikler kullanılamaz. Buna kod sihirbazları, menü istem dizeleri, Birleşik giriş kutusu denetimleri için liste içerikleri ve ActiveX denetimi barındırma dahildir.

- Kaynak betik dosyası açıkken MFC desteği eklemek için, **kaynak görünümü**' de Kaynaklar klasörünü vurgulayın (örneğin, *MFC. RC*). Ardından [Özellikler penceresi](/visualstudio/ide/reference/properties-window), **MFC modunu** **doğru**olarak ayarlayın.

  > [!NOTE]
  > **MFC modunu**ayarlamanın yanı sıra,. rc dosyası bir MFC projesinin parçası olmalıdır. Yalnızca bir Win32 projesindeki bir. rc dosyasında **MFC modunun** **true** olarak ayarlanması, MFC özellikleri vermez.

## <a name="create-resources"></a>Kaynak oluşturma

Bir kaynağı, bir şablonu temel alan bir kaynağı veya bir şablondan sonra desenli kaynak olarak gösteren yeni bir varsayılan kaynak olarak oluşturabilirsiniz.

Projelerinize dahil edilen kaynak dosyalarını göstermek için **kaynak görünümü** penceresini kullanın. En üstteki klasörü genişleterek, örneğin, *Project1. RC*, bu dosya içindeki kaynak türlerini gösterir. Her kaynak türünü, bu türdeki tek tek kaynakları göstermek için genişletin.

> [!TIP]
> **Kaynak görünümü** penceresini açmak için menü **View**  >  **diğer Windows**kaynak görünümü görüntüle ' ye gidin  >  **Resource View** veya **CTRL** + **SHIFT** + **E**tuşlarına basın.

Ayrıca, komutların kısayol menüsünü başlatmak için **kaynak görünümü** penceresine sağ tıklama ya da pencereyi sabitlemek ve çıkarmak için başlık çubuğuna çift tıklayabilmeniz gerekir. Pencerenin davranışını denetleyen komutlar için başlık çubuğuna sağ tıklayın. Daha fazla bilgi için bkz. [Windows yönetimi](/visualstudio/ide/customizing-window-layouts-in-visual-studio).

**Kaynak görünümü** Windows, bir C++ Windows masaüstü uygulaması projesine kaynak eklemek için aşağıdaki özelliklerle **Kaynak Ekle** iletişim kutusunu içerir:

| Özellik | Açıklama |
|---|---|
| **Kaynak Türü** | Oluşturmak istediğiniz kaynak türünü belirtin.<br/><br/>' Da bulunan ek kaynakları açığa çıkarmak için imleci ve iletişim kutusu kaynak kategorilerini genişletebilirsiniz *. \Microsoft Visual Studio \<version\> \Vc\vcresourcetemplates \\<LCID \> \mfc.exe*. . Rct dosyaları eklemeniz gerekiyorsa, bunları buraya koyun ya da başka bir [içerme yolu](./how-to-include-resources-at-compile-time.md)belirtin. Ağaç denetimindeki en üst düzeyde gösterilen kaynaklar, Visual Studio tarafından sunulan varsayılan kaynaklardır. . Rct dosyalarındaki kaynaklar, uygun kategorinin altında ikinci düzeyde görüntülenir. Ekleyebileceğiniz. rct dosyaları sayısında önceden ayarlanmış bir sınır yoktur.<br/><br/> |
| **Yeni** | Kaynak **türü** kutusunda seçilen türe göre bir kaynak oluşturun ve kaynağı uygun düzenleyicide açın.<br/><br/>Örneğin, bir iletişim kaynağı oluşturursanız, kaynağı [Iletişim kutusu düzenleyicisinde](../windows/dialog-editor.md)açar. |
| **İçeri Aktarma** | Geçerli projenize aktarmak istediğiniz kaynağa gitmek için **Içeri aktar** iletişim kutusunu açın.<br/><br/>Bir bit eşlem, simge, imleç, HTML, ses (. WAV) veya özel kaynak dosyası. |
| **Özel** | Özel bir kaynak oluşturmak için **Yeni özel kaynak** iletişim kutusunu açın.<br/><br/>Ayrıca, özel kaynak türünün adını girebileceğiniz bir metin kutusu sağlayan bir **kaynak türü** özelliği de içerir. Visual C++, çıkarken adı otomatik olarak büyük harfe dönüştürür. Özel kaynaklar yalnızca [Ikili düzenleyicide](../windows/binary-editor.md)düzenlenir. |

Yeni bir kaynak oluşturduğunuzda Visual C++ buna benzersiz bir ad atar, örneğin, `IDD_Dialog1` . Bu kaynak KIMLIĞINI, ilişkili kaynak düzenleyicisinde veya [Özellikler penceresi](/visualstudio/ide/reference/properties-window)kaynak özelliklerini düzenleyerek özelleştirebilirsiniz.

> [!NOTE]
> Visual Studio tarafından ayrılan bir kaynak adı veya KIMLIĞI belirtmeyin. Ayrılmış adlar `DESIGNINFO` ,, `HWB` ve `TEXTINCLUDE` ve ayrılmış kimliğidir `255` .

### <a name="to-create-a-resource"></a>Bir kaynak oluşturmak için

- **Kaynak görünümü**' de,. RC dosyanızı seçin, sonra kaynağı **Düzenle**' yi kullanın  >  **Add Resource** ve projenize eklenecek kaynak türünü seçin.

   > [!TIP]
   > Ayrıca, **kaynak görünümü** ' de. rc dosyasına sağ tıklayıp kısayol menüsünden **Kaynak Ekle** ' yi seçebilirsiniz.

- **Çözüm Gezgini**, proje klasörüne sağ tıklayın, Kaynak Ekle **Ekle**' yi seçin  >  **Add Resource** ve projenize eklenecek kaynak türünü seçin.

   > [!NOTE]
   > Projenizde zaten bir. rc dosyanız yoksa, bu adım bir tane oluşturur. Ardından, yeni. rc dosyasına belirli kaynak türlerini eklemek için bu adımı yineleyebilirsiniz.

- [Sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code), sınıfa sağ tıklayın, kaynak **Ekle ' yi seçin**  >  **Add Resource** ve projenize eklenecek kaynak türünü seçin.

- Menü **projesi**  >  **Kaynak Ekle**öğesini kullanın.

## <a name="use-resource-templates"></a>Kaynak Şablonları Kullanma

Kaynak şablonu,. rct dosyası olarak kaydettiğiniz özelleştirilmiş bir kaynaktır. Kaynak şablonu daha sonra kaynak oluşturmak için bir başlangıç noktası olarak görev yapar. Kaynak şablonları, standart denetimler veya yinelenen öğeler gibi özellikleri paylaşan ek kaynakların veya kaynak gruplarının geliştirilmesi sırasında zaman kazandırır. Örneğin, çeşitli iletişim kutularında şirket logosu simgesiyle bir Yardım düğmesi eklemek istiyorsanız, yeni bir iletişim kutusu şablonu oluşturun ve Yardım düğmesi ve logosu ile özelleştirin.

Bir kaynak şablonunu özelleştirdikten sonra, yeni kaynak şablonunun **Kaynak Ekle** iletişim kutusunda kaynak türü altında görünmesi için değişiklikleri şablon klasörüne veya ekleme yolunda belirtilen konuma kaydedin. Artık, gereken sıklıkta yeni kaynak şablonunu kullanabilirsiniz.

> [!NOTE]
> Kaynak Düzenleyicisi otomatik olarak benzersiz bir kaynak KIMLIĞI sağlar. [Kaynak özelliklerini](./resource-editors.md) gerektiği şekilde gözden geçirin.

> [!NOTE]
> Dile özgü şablon dosyalarını ana şablon dizininin alt dizinlerinde yerleştir. Örneğin, yalnızca Ingilizce şablon dosyaları *.. \\<kaynak şablonu dizini \> \ 1033*' a gidin.
>
> Visual Studio, *\Program Files\Microsoft Visual Studio \<version\> \vc\vcresourcetemplates*, *\Program Files\Microsoft Visual Studio \<version> \vc\vcresourcetemplates \\<LCID \> * (İngilizce için 1033 LCID gibi) veya [ekleme yolundaki](./how-to-include-resources-at-compile-time.md)herhangi bir yerde bulunan yeni. rct dosyalarını arar. . Rct dosyalarınızı başka bir konumda depolamayı tercih ediyorsanız, konumu ekleme yoluna eklemeniz gerekir.

### <a name="to-create-and-use-a-resource-template"></a>Kaynak şablonu oluşturmak ve kullanmak için

1. **Çözüm Gezgini**, projenize sağ tıklayın ve Ekle **Add**  >  **Yeni öğe**Ekle ' yi seçin.

1. **Şablonlar:** bölmesinde **Kaynak şablon dosyası (. rct)** öğesini seçin.

1. Yeni *. rct* dosyanız için bir ad ve konum belirtin ve **Aç**' ı seçin.

   Yeni *. rct* dosyası projenize eklenir ve **kaynaklar** klasörü altında **Çözüm Gezgini** görüntülenir.

1. Bir belge penceresinde açmak için *. rct* dosyasına çift tıklayın. Kaynak eklemek için belge penceresinde dosyaya sağ tıklayın ve **Kaynak Ekle**' yi seçin.

   Eklenen kaynaklarınızı özelleştirebilir ve *. rct* dosyasını kaydedebilirsiniz.

1. **Kaynak görünümü** bölmesinde, *. RC* dosyasına sağ tıklayın ve **Kaynak Ekle**' yi seçin.

1. Kaynak **+** düğümünü genişletmek ve bu kaynak için kullanılabilen şablonları görüntülemek için bir kaynağın yanındaki artı işaretini () seçin.

1. Kullanmak istediğiniz şablona çift tıklayın.

   Eklenen kaynağı kaynak düzenleyicisinde gerektiği gibi değiştirebilirsiniz.

### <a name="to-convert-an-existing-resource-file-to-a-template"></a>Var olan bir kaynak dosyasını bir şablona dönüştürmek için

Kaynak betik dosyası açıkken, menüde **Dosya**  >  ** \<*filename*> farklı kaydet**' e gidin. Bir konum belirtip **Tamam**' ı seçin.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak dosyaları](../windows/resource-files-visual-studio.md)<br/>
[Nasıl yapılır: kaynakları yönetme](../windows/how-to-copy-resources.md)<br/>
[Nasıl yapılır: derleme zamanında kaynakları dahil etme](../windows/how-to-include-resources-at-compile-time.md)<br/>
