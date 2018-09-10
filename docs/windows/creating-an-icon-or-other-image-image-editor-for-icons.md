---
title: Simge veya başka görüntü (simgeler için görüntü Düzenleyicisi) oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.bitmap
dev_langs:
- C++
helpviewer_keywords:
- bitmaps [C++]
- images [C++], creating
- resources [C++], creating images
- bitmaps [C++], creating
- graphics [C++], creating
- Image editor [C++], creating images
ms.assetid: 66db3fb2-cfc1-48a2-9bdd-53f61eb7ee30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 82479dab780fce677eeee84c4ccde880fe19d2bc
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44314917"
---
# <a name="creating-an-icon-or-other-image-image-editor-for-icons"></a>Simge veya Başka Görüntü Oluşturma (Simgeler İçin Görüntü Düzenleyicisi)

Yeni bir görüntü (bit eşlemi, simge, imleç veya araç) oluşturmak ve görünümünü özelleştirmek için görüntü Düzenleyicisi'ni kullanın. Desenli sonra yeni bir bit eşlem oluşturabilirsiniz bir [şablon](../windows/how-to-use-resource-templates.md).

### <a name="to-add-a-new-image-resource-to-an-unmanaged-c-project"></a>Yönetilmeyen C++ projesinde yeni bir görüntü kaynağı eklemek için

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), .rc dosyasına sağ tıklayın ve ardından seçin **kaynak Ekle** kısayol menüsünden. (Bir imleç gibi bir .rc dosyasında var olan bir görüntü kaynağı zaten varsa, yalnızca sağ tıklayabilirsiniz **imleç** klasörü ve select **imleci yerleştirin** kısayol menüsünden.)

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

2. İçinde [kaynak Ekle iletişim kutusu](../windows/add-resource-dialog-box.md), oluşturmak istediğiniz görüntü kaynak türünü seçin (**bit eşlem**, örneğin) ardından **yeni**.

   Bir artı işareti (**+**) görüntü kaynak türünü yanında **kaynak Ekle** iletişim kutusu, geldiğini araç şablonları kullanılabilir. Şablonlar listesinde genişletin, bir şablon seçin ve tıklayın artı işaretine tıklayın **yeni**.

### <a name="to-add-a-new-image-resource-to-a-project-in-a-net-programming-language"></a>Yeni bir görüntü kaynağı bir programlama dilinde bir .NET projesine eklemek için

1. İçinde **Çözüm Gezgini**, proje klasörüne sağ tıklayın (örneğin, `WindowsApplication1`).

2. Kısayol menüsünden tıklayın **Ekle**, ardından **Yeni Öğe Ekle**.

3. İçinde **kategorileri** bölmesini genişletin **yerel proje öğeleri** klasörü seçin **kaynakları**.

4. İçinde **şablonları** bölmesinde, projenize eklemek istediğiniz kaynak türünü seçin.

   Projenizde kaynağa eklenir **Çözüm Gezgini** ve kaynak açılır [Resim Düzenleyicisi](../windows/image-editor-for-icons.md). Artık, görüntünüzü değiştirmek için görüntü Düzenleyicisi'nde kullanılabilir olan tüm araçları da kullanabilirsiniz. Görüntüleri yönetilen bir projeye ekleme ile ilgili daha fazla bilgi için bkz: [tasarım zamanında bir resim yükleme](/dotnet/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms).

   > [!NOTE]
   > Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır. Visual Studio kaynak düzenleyicileri eklenmiş kaynakları düzenlemeyi desteklemez. Daha fazla bilgi için [Creating Resource Files](/dotnet/framework/resources/creating-resource-files-for-desktop-apps) içinde *.NET Framework Geliştirici Kılavuzu*.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Yok.

## <a name="see-also"></a>Ayrıca Bkz.

[Simgeler ve İmleçler: görüntüleme cihazları için görüntü kaynakları](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)  
[Bit Eşlemleri Araç Çubuklarına Dönüştürme](../windows/converting-bitmaps-to-toolbars.md)  
[Yeni Araç Çubukları Oluşturma](../windows/creating-new-toolbars.md)  
[Grafik kaynakları düzenleme](../windows/editing-graphical-resources-image-editor-for-icons.md)  
[Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)