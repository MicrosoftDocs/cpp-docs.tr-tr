---
title: 'Nasıl yapılır: Kaynak (C++) oluştur'
ms.date: 11/04/2016
f1_keywords:
- vs.resourceview.F1
- vc.editors.insertresource
- vc.editors.newcustomresource
helpviewer_keywords:
- toolbars [C++], resources
- resource toolbars
- resources [C++], creating
- resources [C++], viewing
- Resource View window
- resources [C++], adding
- Add Resource dialog box [C++]
- Custom Resource Type dialog box [C++]
ms.assetid: aad44914-9145-45a3-a7d8-9de89b366716
ms.openlocfilehash: fdf158bab7894497dbcfb147eb2c6e061879be75
ms.sourcegitcommit: 63c072f5e941989636f5a2b13800b68bb7129931
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2019
ms.locfileid: "55764057"
---
# <a name="how-to-create-a-resource-c"></a>Nasıl yapılır: Kaynak (C++) oluştur

**Kaynak görünümü** penceresi projelerinizde içerdiği kaynak dosyaları görüntüler. En üst düzey klasör (örneğin, Project1.rc) genişleterek, .rc dosyası içine kaynak türlerini gösterir. Her kaynak türünün genişleterek o türün tek tek kaynakları gösterir.

> [!NOTE]
> Bu bilgiler, Evrensel Windows platformu uygulamalarında kaynakları için geçerli değildir. Hakkında daha fazla bilgi için bkz: [uygulama kaynaklarını ve kaynak yönetim sistemi](/windows/uwp/app-resources/).

> [!NOTE]
> **Kaynak görünümü** Express sürümlerinde desteklenmez.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*.

> [!NOTE]
> Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

**Kaynak görünümü** penceresi kullanan **kaynak Ekle** kaynakları bir C++ Windows masaüstü uygulaması projesine eklemek için iletişim kutusu. Bu iletişim kutusunda, aşağıdaki özelliklere sahiptir:

|Özellik|Açıklama|
|---|---|
|**Kaynak Türü**|Oluşturmak istediğiniz kaynak türünü belirtir.<br/><br/>Ek kaynaklar ortaya çıkarmak için imleç ve iletişim kutusunu kaynak kategorileri genişletebilirsiniz. Bu kaynaklar ...\Microsoft Visual Studio içinde bulunan `version`\VC\VCResourceTemplates\\< LCID\>\mfc.rct. .Rct dosyaları ekleme, bu dizine koymanız gerekir ya da belirtmeniz gerekir bir [yolunu](../windows/how-to-specify-include-directories-for-resources.md) bunlar için. Daha sonra bu dosyalarındaki kaynaklar ikinci düzeyde uygun kategorisi altında görünür. Ekleyebileceğiniz .rct dosyaları sayısı önceden belirlenmiş bir sınır yoktur.<br/><br/>Ağaç denetimi üst düzeyde gösterilen kaynağı Visual Studio tarafından sağlanan varsayılan kaynaklardır.|
|**Yeni**|İçinde seçtiğiniz türüne göre bir kaynak oluşturur **kaynak türü** kutusu. Kaynak uygun Düzenleyicisi'nde açılır. Bir iletişim kutusu kaynağı oluşturursanız, örneğin, açılır [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md).|
|**İçeri Aktar**|Açılır **alma** içinde gidebilirsiniz bir kaynağa, iletişim kutusu geçerli projenize aktarmak istediğiniz. Bir bit eşlem simgesi, imleç, HTML kaynak dosyası, ses alabilirsiniz (. WAV) kaynak dosyası veya özel kaynak dosyası.|
|**Özel**|Açılır **yeni özel kaynak** içinde oluşturabileceğiniz özel bir kaynak iletişim kutusu. Özel kaynaklar yalnızca ikili düzenleyicide düzenleyebilirsiniz.|

**Yeni özel kaynak** iletişim kutusunda bir C++ projesinde yeni bir özel kaynak oluşturmanıza olanak sağlar. Bu iletişim kutusunda, aşağıdaki özellikler vardır:

|Özellik|Açıklama|
|---|---|
|**Kaynak Türü**|Özel kaynak türü adını girmek metin kutusu sağlar. Visual C++, çıktığınızda adı otomatik olarak büyük **yeni özel kaynak** iletişim kutusu.|

Yeni bir kaynak oluşturduğunuzda, Visual C++ benzersiz bir ad, örneğin atar `IDD_Dialog1`. Bu kaynak kimliği için ilişkili kaynak Düzenleyicisi'ni veya kaynak özellikleri düzenleyerek özelleştirebilirsiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window).

Yeni bir varsayılan kaynak (bir şablona bağlı olmayan bir kaynak) veya sonra desenli bir kaynak olarak bir kaynak oluşturmak bir [şablon](../windows/how-to-use-resource-templates.md).

> [!NOTE]
> Visual Studio tarafından ayrılmış bir kaynak adı ya belirtmeyin. Ayrılmış adları DESIGNINFO, HWB, ve TEXTINCLUDE ve ayırtılmış ID 255tir.

## <a name="to-open-the-resource-view-window"></a>Kaynak Görünümü penceresi açmak için

Seçin **kaynak görünümü** üzerinde **görünümü** menüsü.

   \- veya -

Tuşuna **Ctrl** + **Shift** + **E**.

> [!TIP]
> Sağ tıklayabilirsiniz **kaynak görünümü** penceresi kısayol menüsü komutları başlatmak için. Ayrıca, sabitleme veya pencerenin çıkarmak için başlık çubuğunu çift tıklatabilirsiniz. Başlık çubuğunun sağ pencereyi davranışını denetlemenize izin ek komutlar verir. Daha fazla bilgi için [Windows Yönetim](/visualstudio/ide/customizing-window-layouts-in-visual-studio).

## <a name="to-create-a-new-resource-in-resource-view"></a>Kaynak Görünümü'nde yeni bir kaynak oluşturmak için

1. Bir .rc dosyasında odaklanarak **kaynak görünümü**seçin **Düzenle** menü ve **kaynak Ekle** (veya .rc dosyasına sağ tıklayın **KaynakGörünümü** ve **kaynak Ekle** kısayol menüsünden).

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

1. İçinde **kaynak Ekle** iletişim kutusunda, projenize eklemek istediğiniz kaynak türünü seçin.

## <a name="to-create-a-new-resource-in-solution-explorer"></a>Çözüm Gezgini içinde yeni bir kaynak oluşturmak için

1. İçinde **Çözüm Gezgini**, proje klasörü sağ tıklatın ve seçin **Ekle**, ardından **kaynak Ekle** kısayol menüsünde.

   Bu adım, projenizde zaten bir .rc dosyası yoksa oluşturur. Sonra belirli kaynak türlerine yeni .rc dosyasına eklemek için bu adımı yineleyebilirsiniz.

2. İçinde **kaynak Ekle** iletişim kutusunda, projenize eklemek istediğiniz kaynak türünü seçin.

## <a name="to-create-a-new-resource-in-class-view"></a>Sınıf Görünümü'nde yeni bir kaynak oluşturmak için

1. İçinde [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code)sınıfınıza sağ tıklatın ve seçin **Ekle**, ardından **kaynak Ekle** kısayol menüsünden.

2. İçinde **kaynak Ekle** iletişim kutusunda, projenize eklemek istediğiniz kaynak türünü seçin.

## <a name="to-create-a-new-resource-from-the-project-menu"></a>Proje menüsünden Yeni bir kaynak oluşturmak için

Gelen **proje** menüsünde seçin **kaynak Ekle**.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Dosyalarıyla Çalışma](../windows/working-with-resource-files.md)<br/>
[Kaynak dosyaları](../windows/resource-files-visual-studio.md)<br/>
[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
