---
title: Cihaz Görüntüsü Oluşturma (Simgeler İçin Görüntü Düzenleyicisi)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.icon
- vc.editors.newimagetype
- vc.editors.customimage
- vc.editors.opendeviceimage
helpviewer_keywords:
- cursors [C++], creating
- icons [C++], creating
- display devices [C++], creating image
- images [C++], creating for display devices
- icons [C++], inserting
- New <Device> Image Type dialog box [C++]
- Custom Image dialog box [C++]
- Open <Device> Image dialog box [C++]
ms.assetid: 5a536928-32df-4ace-beb1-1521ce3b871f
ms.openlocfilehash: ce1069f6f410d7a60d631461086ca8870ef679c0
ms.sourcegitcommit: efcc8c97570ddf7631570226c700e8f6ebb6c7be
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2019
ms.locfileid: "55560302"
---
# <a name="creating-a-device-image-image-editor-for-icons"></a>Cihaz Görüntüsü Oluşturma (Simgeler İçin Görüntü Düzenleyicisi)

Yeni simgesi veya imleci kaynak oluşturduğunuzda **görüntü** Düzenleyicisi ilk oluşturur görüntü özel bir stili (32 x 32, 16 renk simgelerinin ve 32 x 32, tek renkli işaretçiler için). Ardından, ilk simgesi veya imleci için görüntüleri farklı boyut ve stil ekleyin ve ek her görüntü, farklı ekran cihazları için gerektiği gibi düzenleyin. Varolan bir görüntü türü veya bir grafik programında oluşturulan bir bit eşlem kesme ve yapıştırma işlemi kullanarak görüntü de düzenleyebilirsiniz.

Simgesi veya imleci kaynak açtığınızda [Resim Düzenleyicisi](../windows/image-editor-for-icons.md), görüntünün en yakın geçerli görüntü cihazı eşleşen varsayılan olarak açılır.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="new-ltdevicegt-image-type-dialog-box"></a>Yeni &lt;cihaz&gt; görüntü türü iletişim kutusu

**Yeni &lt;cihaz&gt; görüntü türü** iletişim kutusu belirtilen bir türün yeni cihaz görüntüsü oluşturmanıza olanak sağlar. Açmak için **yeni \<cihaz > Görüntü** iletişim kutusunda **yeni görüntü tipi** üzerinde **görüntü** menüsü. Dahil edilen aşağıdaki özellikler **hedef görüntü tipi** ve **özel**.

### <a name="target-image-type"></a>Hedef görüntü türü

Mevcut görüntü türlerini listeler. Açmak istediğiniz görüntü türünü seçin:

||||
|-|-|-|
|-16 16 x 16 renk|-48 x 48, 16 renk|-96 x 96 16 renk|
|-16 x 16, 256 renkleri|-48 x 48, 256 renkleri|-96 x 96, 256 renkleri|
|-16 x 16, tek renkli|-48 x 48, tek renkli|-96 x 96, tek renkli|
|-32 x 32 16 renk|-64, x 64 16 renk||
|-32 x 32, 256 renkleri|-64 x 64, 256 renkleri||
|-32 x 32, tek renkli|-64 x 64, tek renkli||

> [!NOTE]
> Bu listede herhangi bir mevcut görüntü görüntülenmez.

### <a name="custom"></a>Özel

Açılır **özel görüntü** içinde oluşturabileceğiniz yeni bir görüntü özel boyutu ve renklerin sayısı ile iletişim kutusu.

**Özel görüntü** iletişim kutusu özel boyutu ve renk sayısını yeni bir görüntü oluşturmanıza olanak sağlar. Dahil edilen aşağıdaki özellikler şunlardır:

|Özellik|Açıklama|
|---|---|
|**Genişlik**|Özel görüntü genişliğini piksel cinsinden (1-512 sınırını 2048) girmeniz için bir alan sağlar.|
|**Yükseklik**|Özel görüntü (1-512 sınırını 2048) piksel cinsinden yüksekliği girmek bir alan sağlar.|
|**Renkler**|Özel görüntü için renk sayısını seçmenize olanak sağlar: 2, 16 veya 256.|

## <a name="open-ltdevicegt-image-dialog-box"></a>Açık &lt;cihaz&gt; görüntü iletişim kutusu

Kullanım **açın &lt;cihaz&gt; görüntü** C++ projelerinde cihaz görüntüleri açmak için iletişim kutusu. Geçerli kaynak (geçerli kaynak bir parçası olan görüntüleri) var olan cihaz görüntülerinde listeler. Dahil edilen aşağıdaki özelliğidir:

|Özellik|Açıklama|
|---|---|
|**Mevcut görüntülerin**|Kaynakta bulunan görüntüleri listeler. Açmak istediğiniz görüntü türü seçin.|

## <a name="to-create-a-new-icon-or-cursor"></a>Yeni simgesi veya imleci oluşturma

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), .rc dosyasına sağ tıklayın ve ardından seçin **kaynak Ekle** kısayol menüsünden. (Bir imleç gibi bir .rc dosyasında var olan bir görüntü kaynağı zaten varsa sağ tıklayabilirsiniz **imleç** klasörü ve select **imleci yerleştirin** kısayol menüsünden.)

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

1. İçinde [kaynak Ekle iletişim kutusu](../windows/add-resource-dialog-box.md)seçin **simgesi** veya **imleç** ve **yeni**. Simgeleri için bu eylem bir 32 x 32 ile 16-renk simgesi bir simge kaynağı oluşturur. İmleçler, bir 32 x 32, tek renkli (2-color) görüntü oluşturulur.

   Bir artı işareti (**+**) görüntü kaynak türünü yanında **kaynak Ekle** iletişim kutusu, geldiğini araç şablonları kullanılabilir. Şablonlar listesinde genişletin, bir şablon seçin veya seçmek için artı işaretini seçin **yeni**.

## <a name="requirements"></a>Gereksinimler

Hiçbiri

## <a name="see-also"></a>Ayrıca Bkz.

[Simgeler ve İmleçler: Görüntüleme cihazları için görüntü kaynakları](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)<br/>
[Hızlandırıcı Tuşları](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Simgeler ve İmleçler: Görüntüleme cihazları için görüntü kaynakları](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)<br/>
[Görüntü menüsü](../windows/image-menu-image-editor-for-icons.md)<br/>
[Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)<br/>
