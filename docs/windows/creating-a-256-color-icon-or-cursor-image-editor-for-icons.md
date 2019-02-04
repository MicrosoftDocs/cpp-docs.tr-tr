---
title: 256-Renk Paletini Kullanma (Simgeler İçin Görüntü Düzenleyicisi)
ms.date: 11/04/2016
helpviewer_keywords:
- 256-color palette
- cursors [C++], color
- colors [C++], icons
- colors [C++], cursors
- icons, color
- colors [C++], icons and cursors
- color palettes, 256-color
- palettes, 256-color
ms.assetid: 2738089b-4fd3-4c45-96ae-6a15e4c6b780
ms.openlocfilehash: 4e2f2c9ce58799756137bb47db42e52c97a43d39
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55702901"
---
# <a name="using-the-256-color-palette-image-editor-for-icons"></a>256-Renk Paletini Kullanma (Simgeler İçin Görüntü Düzenleyicisi)

Kullanarak **görüntü** Düzenleyicisi, simgeler ve İmleçler boyutlu büyük (64 × 64) aralarından seçim yapabileceğiniz bir 256-renk paletini sahip olabilir. Kaynak oluşturduktan sonra bir cihaz görüntü stili seçilir.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="to-create-a-256-color-icon-or-cursor"></a>256-renk simgesi veya imleci oluşturma

1. İçinde [kaynak görünümü](../windows/resource-view-window.md), .rc dosyasına sağ tıklayın ve ardından seçin **kaynak Ekle** kısayol menüsünden. (Bir imleç gibi bir .rc dosyasında var olan bir görüntü kaynağı zaten varsa sağ tıklayabilirsiniz **imleç** klasörü ve select **imleci yerleştirin** kısayol menüsünden.)

   > [!NOTE]
   > Projenize bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).

1. İçinde [kaynak Ekle iletişim kutusu](../windows/add-resource-dialog-box.md)seçin **simgesi** veya **imleç** ve **yeni**.

1. Üzerinde **görüntü** menüsünde **yeni cihaz görüntüsü**.

1. 256-renk görüntü stili seçin.

## <a name="to-choose-a-color-from-the-256-color-palette-for-large-icons"></a>Büyük simgeler için 256-renk paletinden bir renk seçmek için

256-renk paletinden bir seçimle çizmek için renk seçmeniz gerekir **renkleri** palette [renkler penceresini](../windows/colors-window-image-editor-for-icons.md).

1. Büyük simgesi veya imleci seçin veya yeni büyük simgesi veya imleci oluşturma.

1. Görüntülenen 256 renkten bir renk seçin **renkleri** palette **renkleri** penceresi.

   Seçili renk geçerli rengi olur **renkleri** palette **renkleri** penceresi.

   > [!NOTE]
   > 256-renk görüntüler için kullanılan ilk paleti tarafından döndürülen palet eşleşen `CreateHalftonePalette` Windows API. Windows Kabuğu için hedeflenen tüm simgeleri palet gerçekleştirme sırasında titreşimini önlemek için bu paletin kullanmanız gerekir.

## <a name="requirements"></a>Gereksinimler

Hiçbiri

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı Tuşları](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Simgeler ve İmleçler: Görüntüleme cihazları için görüntü kaynakları](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)
