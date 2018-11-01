---
title: Cihaz Görüntülerinde Saydam veya Ters Bölgeler Oluşturma (Simgeler İçin Görüntü Düzenleyicisi)
ms.date: 11/04/2016
helpviewer_keywords:
- cursors [C++], screen regions
- inverse colors [C++], device images
- transparent regions, device images
- transparency, device images
- Image editor [C++], device images
- inverse regions, device images
- cursors [C++], transparent regions
- screen colors
- regions, transparent
- icons [C++], transparent regions
- display devices [C++], transparent and screen regions
- transparent regions in devices
- regions, inverse
- colors [C++], Image editor
- device projects [C++], transparent images
- icons [C++], screen regions
ms.assetid: a994954b-b039-4391-a535-58d1fa10fc3b
ms.openlocfilehash: 3c4f5aa0b63259fbe42c353525e52319db1b0667
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626648"
---
# <a name="creating-transparent-or-inverse-regions-in-device-images-image-editor-for-icons"></a>Cihaz Görüntülerinde Saydam veya Ters Bölgeler Oluşturma (Simgeler İçin Görüntü Düzenleyicisi)

İçinde [Resim Düzenleyicisi](../windows/image-editor-for-icons.md), ilk simgesi veya imleci görüntünün saydam bir öznitelik vardır. Simge ve imleç görüntü dikdörtgen olsa da, görüntünün bölümlerini şeffaf olduğundan çok bunu görünmez; temel alınan görüntünün ekranında simgesi veya imleci gösterilir. Simge sürüklediğinizde, bir ters renkte bölümleri görünebilir. Ekran rengi ve ters renk ayarlayarak bu etkiyi oluşturmak [renkler penceresini](../windows/colors-window-image-editor-for-icons.md).

Ekran ve ters renk simgeleri uygulamak ve İmleçler şekil ve türetilmiş görüntü renk ya da ters bölgeleri belirleyin. Renkleri özniteliklerle işlediği görüntünün parçalarını gösterir. Düzenleme ekranı rengi ve ters renk özniteliklerini temsil eden renklerini değiştirebilirsiniz. Bu değişiklikler simgesi veya imleci uygulamanızın görünümünü etkilemez.

> [!NOTE]
> İletişim kutuları ve menü komutları gördüğünüz içinde açıklanana göre farklılık **yardımcı** bağlı olarak, etkin ayarlarınıza ve sürüm. Ayarlarınızı değiştirmek için seçin **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için [Visual Studio IDE'yi kişiselleştirme](/visualstudio/ide/personalizing-the-visual-studio-ide).

### <a name="to-create-transparent-or-inverse-regions"></a>Saydam veya ters bölgeler oluşturma

1. İçinde **renkleri** penceresinde tıklayın **ekran rengi** Seçici veya **ters renk** Seçici.

2. Ekran veya ters renk, resim çizim aracı kullanma uygulayın. Çizim Araçları ile ilgili daha fazla bilgi için bkz: [çizim aracı kullanma](using-a-drawing-tool-image-editor-for-icons.md).

### <a name="to-change-the-screen-or-inverse-color"></a>Ekran veya ters rengini değiştirmek için

1. Şunlardan birini seçin **ekran rengi** Seçici veya **ters renk** Seçici.

2. Bir renk seçin **renkleri** palette **renkleri** penceresi.

   Tamamlayıcı renk diğer Seçicisi otomatik olarak atanır.

   > [!TIP]
   > Çift tıkladığınızda, **ekran rengi** veya **ters renk** Seçici, [Özel Renk Seçici iletişim kutusu](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md) görünür.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Yok.

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Simgeler ve İmleçler: görüntüleme cihazları için görüntü kaynakları](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)