---
title: Bir iletişim kutusu (C++) ActiveX denetimleri ekleme ve görüntüleme
ms.date: 11/04/2016
f1_keywords:
- vc.controls.activex
- vc.editors.dialog.insertActiveXControls
helpviewer_keywords:
- dialog boxes [C++], adding ActiveX controls
- ActiveX controls [C++], adding to dialog boxes
- Insert ActiveX Control dialog box [C++]
- controls [C++], editing properties
- ActiveX controls [C++], properties
ms.assetid: e1c2e3ae-e1b0-40d3-9766-623007073856
ms.openlocfilehash: 139407ec1d4e1bfad6bb06854dc24b86ce7014e8
ms.sourcegitcommit: b488462a6e035131121e6f32d8f3b108cc798b5e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55293617"
---
# <a name="viewing-and-adding-activex-controls-to-a-dialog-box-c"></a>Bir iletişim kutusu (C++) ActiveX denetimleri ekleme ve görüntüleme

Visual Studio, iletişim kutusuna ActiveX denetimleri eklemenize olanak tanır.

**ActiveX denetimi Ekle** iletişim kutusu kullanırken, iletişim kutusuna ActiveX denetimleri eklemenize olanak sağlayan [iletişim kutusu Düzenleyicisi](../windows/dialog-editor.md). Bu iletişim kutusunda, aşağıdaki özellikleri içerir:

|Özellik|Açıklama|
|---|---|
|**ActiveX denetimi**|ActiveX denetimleri listesini görüntüler. Bu iletişim kutusundan bir denetim ekleme, bir sarmalayıcı sınıfı oluşturmaz. Sarmalayıcı sınıf ihtiyacınız varsa, [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code) oluşturmak için (daha fazla bilgi için [sınıf ekleme](../ide/adding-a-class-visual-cpp.md)). Bu iletişim kutusunda bir ActiveX denetimi görünmüyorsa, satıcının yönergelerine göre denetim yükleme deneyin.|
|**Yolu**|ActiveX denetimi içinde bulunan dosyayı görüntüler.|

Denetimlerinde yerleştirebilirsiniz **araç kutusu** penceresi kolay erişim için. Daha fazla bilgi için [araç kutusu](/visualstudio/ide/reference/).

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="to-see-the-activex-controls-you-have-available"></a>ActiveX denetimlerini görmek için elinizde

1. Bir iletişim kutusu, iletişim kutusu Düzenleyicisi'nde açın.

1. Herhangi bir iletişim kutusunun gövdesinde sağ tıklayın.

1. Kısayol menüsünde **ActiveX denetimi Ekle**.

   **ActiveX denetimi Ekle** iletişim kutusu görüntülenirse, sisteminizdeki tüm ActiveX denetimlerini gösterme. ActiveX denetimi dosyasının yolu iletişim kutusunun en altında görünür.

## <a name="to-add-an-activex-control-to-a-dialog-box"></a>İletişim kutusuna ActiveX denetimi eklemek için

1. İçinde **ActiveX denetimi Ekle** iletişim kutusunda, istediğiniz, iletişim kutusuna ekleyin ve denetimi seçin **Tamam**.

   Denetim, düzenlemek veya başka bir denetimde olduğu gibi işleyicileri için oluşturma iletişim kutusunda görüntülenir.

   > [!NOTE]
   > ActiveX denetimlerine ekleyebilirsiniz [araç penceresi](/visualstudio/ide/reference/toolbox).

   > [!CAUTION]
   > ActiveX denetimleri, sisteminizdeki tüm dağıtmak için geçerli olmayabilir. Lütfen denetimleri yüklü yazılımlar için lisans sözleşmesi bakın veya yazılım şirketine başvurun.

   Denetimlerinde yerleştirebilirsiniz **araç kutusu** penceresi kolay erişim için. Daha fazla bilgi için [araç kutusu](/visualstudio/ide/reference/toolbox).

## <a name="to-edit-properties-for-an-activex-control"></a>ActiveX denetimi özelliklerini düzenlemek için

ActiveX denetimleri bağımsız satıcıları tarafından sağlanan kendi özellikleri ve özellikleri ile donatıldı gelebilir. ActiveX denetimleri için özellikleri görüntülenir **özellikleri** penceresi. ActiveX denetiminin yazarlar tarafından oluşturulan tüm özellik sayfaları ek olarak, görüntülenen **özellikler sayfaları** iletişim kutusu (görüntülemek için **özellik sayfası** belirlibirActiveXdenetimiiçintıklayın **Özellik sayfası** düğmesine [Özellikler penceresi](/visualstudio/ide/reference/properties-window)).

Çeşitli sekmelere ActiveX denetiminin bir parçası olarak gelen özellik sayfalarını bağlı olarak bir ActiveX denetimi için özellik sayfası görüntülenir.

> [!NOTE]
> Aşağıdaki yordam, özellik sayfasını kullanarak ActiveX denetimlerini düzenlemek için geçerlidir. Ayrıca göz atabilir ve ActiveX özellikleri yeni Düzenle **özellikleri** penceresi.

1. Seçin **ActiveX** denetimi.

1. Üzerinde **görünümü** menüsünde **özellik sayfası** ve özelliklerini görüntüleyin.

1. Özellik sayfasında gerekli değişiklikleri yapın.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)<br/>
[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)<br/>
[ActiveX Denetim Kapsayıcıları](../mfc/activex-control-containers.md)<br/>
[İletişim Kutusuna ActiveX Denetimleri Ekleme ve Görüntüleme](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md)<br/>
[İletişim Kutusu Düzenleyicisi Sekmesi, Araç Kutusu](../windows/dialog-editor-tab-toolbox.md)<br/>
[Kaynak dosyaları](../windows/resource-files-visual-studio.md)<br/>
