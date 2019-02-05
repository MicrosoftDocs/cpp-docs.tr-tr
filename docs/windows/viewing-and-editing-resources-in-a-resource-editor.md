---
title: Kaynakları, kaynak düzenleyicisinde (C++) görüntüleme ve düzenleme
ms.date: 11/04/2016
f1_keywords:
- vs.resourceview
- vc.resvw.resource.previewing
- vs.resvw.resource.previewing
helpviewer_keywords:
- resources [C++], viewing
- layouts, previewing resource
- resource editors [C++], viewing resources
- .rc files [C++], viewing resources
- resources [C++], editing
- properties [C++], resources
- resources [C++], properties
ms.assetid: ba8bdc07-3f60-43c7-aa5c-d5dd11f0966e
ms.openlocfilehash: 02ab58d37f3f188c3d65740b218cb9b2ac799714
ms.sourcegitcommit: 52c05e10b503e834c443ef11e7ca1987e332f876
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/05/2019
ms.locfileid: "55742667"
---
# <a name="viewing-and-editing-resources-in-a-resource-editor-c"></a>Kaynakları, kaynak düzenleyicisinde (C++) görüntüleme ve düzenleme

Her kaynak türüne sahip bir **kaynak** bu kaynak türü için belirli bir düzenleyici. Yeniden düzenleme, yeniden boyutlandırma, denetimleri ve Özellik Ekle veya aksi ilişkili Düzenleyicisi'ni kullanarak bir kaynak özelliklerini değiştirin. Bir kaynak olarak da düzenleyebilirsiniz [metin biçimi](../windows/how-to-open-a-resource-script-file-in-text-format.md) ve [ikili biçimi](../windows/opening-a-resource-for-binary-editing.md).

Bazı kaynak türleri içeri aktarıldı ve çeşitli şekillerde kullanılan tek dosyalardır; Bunlar, bit eşlemler, simgeler, işaretçiler, araç çubukları ve html dosyaları içerir. Böyle kaynaklar dosya adlarına sahip ve [kaynak tanımlayıcıları](../windows/symbols-resource-identifiers.md). Diğer iletişim kutuları, menüler ve Win32 projeleri, dize tablolarında gibi yalnızca bir kaynak betiği (.rc) veya kaynak şablonu (.rct) dosyasının parçası olarak mevcut.

> [!NOTE]
> Kaynağın özelliklerini [Özellikler penceresini kullanarak değiştirilebilir](../windows/changing-the-properties-of-a-resource.md).

## <a name="win32-resources"></a>Win32 kaynakları

Win32 kaynaklarında erişebileceğiniz [kaynak görünümü](../windows/resource-view-window.md) bölmesi.

### <a name="to-view-a-win32-resource-in-a-resource-editor"></a>Bir Win32 kaynağı kaynak düzenleyicide görüntülemek için

1. Seçin **kaynak görünümü** gelen **görünümü** menüsü.

1. Varsa **kaynak görünümü** penceresi seçin en üst penceresine değil **kaynak görünümü** dön getirmek için sekmesinde.

1. Gelen **kaynak görünümü**, görüntülemek istediğiniz kaynakları içeren proje klasörünü genişletin. Örneğin, bir iletişim kutusu kaynağı görüntülemek istiyorsanız, genişletme **iletişim** klasör.

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

1. Örneğin, kaynağa çift tıklatın **IDD_ABOUTBOX**.

   Kaynak uygun Düzenleyicisi'nde açılır. Örneğin, iç kaynak iletişim kutusu kaynakları için açılır **iletişim** Düzenleyici.

   Ayrıca [görüntülemek kaynakları bir (kaynak betiği) .rc dosyasındaki açık bir projeniz zorunda kalmadan](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).

### <a name="to-delete-an-existing-win-32-resource"></a>Mevcut bir Win 32 kaynağı silmek için

1. İçinde **kaynak görünümü**, bir kaynak türü için düğümü genişletin.

2. Sağ tıklayın ve silmek istediğiniz kaynak **Sil** kısayol menüsünden.

   > [!NOTE]
   > Bir belge penceresi dışında bir proje açın .rc dosyası varsa, aynı kısayol menü komutunu kullanarak kaynak silebilirsiniz.

## <a name="resources-in-managed-projects"></a>Yönetilen projelerde kaynakları

Yönetilen projelere kaynak betik dosyalarına kullanmayın çünkü kaynaklarınızdan açmalısınız **Çözüm Gezgini**. Kullanabileceğiniz [Resim Düzenleyicisi](../windows/image-editor-for-icons.md) ve [ikili düzenleyiciyi](binary-editor.md) yönetilen projelerde kaynak dosyalarıyla çalışmak için. Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır. Visual Studio kaynak düzenleyicileri eklenmiş kaynakları düzenlemeyi desteklemez.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

### <a name="to-view-a-managed-resource-in-a-resource-editor"></a>Yönetilen kaynak bir kaynak Düzenleyicisi'nde görüntülemek için

İçinde **Çözüm Gezgini**, kaynak, örneğin, çift **Bitmap1.bmp**.

   Kaynak uygun Düzenleyicisi'nde açılır.

### <a name="to-delete-an-existing-managed-resource"></a>Mevcut bir yönetilen kaynak silinemedi

İçinde **Çözüm Gezgini**, seçin ve silmek istediğiniz kaynağa sağ **Sil** kısayol menüsünden.

## <a name="changing-the-properties-of-resources"></a>Kaynak özelliklerini değiştirme

### <a name="to-edit-the-properties-of-a-resource"></a>Kaynağın özelliklerini düzenlemek için

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), seçin ve düzenlemek istediğiniz kaynağa sağ **özellikleri** kısayol menüsünden.

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

1. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), kaynak özelliklerini değiştirin.

### <a name="to-undo-a-change-made-to-the-properties-of-a-resource"></a>Bir kaynak özelliklerine yapılan bir değişikliği geri almak için

1. Kaynak odak olduğundan emin olun **kaynak görünümü**.

1. Seçin **geri** gelen **Düzenle** menüsü.

## <a name="previewing-resources"></a>Kaynakları Önizleme

Kaynaklarınızı açmaya gerek kalmadan grafik kaynağı görüntülemek olanak Önizleme. Kaynak Tanımlayıcıları sayılara değiştiğinden bunlara derlenmiş sonra Önizleme de yürütülebilir dosyalar için yararlıdır. Bu sayısal tanımlayıcıları genellikle yeterli bilgi sağlamayan olduğundan, kaynakları Önizleme hızlıca belirlemenize yardımcı olur.

Görsel düzeni aşağıdaki kaynak türlerinin önizlemesini görebilirsiniz:

- Bit eşlem

- İletişim kutusu

- Simge

- Menü

- İmleç

- Araç Çubuğu

Görsel Önizleme işlevi Hızlandırıcı, bildirimi, dize tablosu ve sürüm bilgileri kaynakları için geçerli değildir.

### <a name="to-preview-resources"></a>Kaynakları Önizleme

1. İçinde [kaynak görünümü](../windows/resource-view-window.md) veya seçin, kaynak, örneğin, bir belge penceresi **IDD_ABOUTBOX**.

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

1. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window)seçin **özellik sayfaları** düğmesi.

   \- veya -

   Üzerinde **görünümü** menüsünde **özellik sayfaları**.

   **Özellik sayfası** kaynak açar, kaynak önizlemesi görüntüleniyor. Ardından **yukarı** ve **aşağı** ağaç gezinmek için ok tuşlarını denetlemek de **kaynak görünümü** ya da belge penceresini. **Özellik sayfası** açık kalır ve odaklı ve önizlenebilir herhangi bir kaynağa göster.

> [!NOTE]
> Kaynakları Önizleme için Win32 gerektirir.

## <a name="requirements"></a>Gereksinimler

Hiçbiri

## <a name="see-also"></a>Ayrıca bkz.

[Nasıl yapılır: Proje Dışındaki Kaynak Betik Dosyasını Açma (Tek Başına)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)<br/>
[Kaynak Düzenleyicileri](../windows/resource-editors.md)