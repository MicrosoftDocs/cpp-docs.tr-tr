---
title: Renk (simgeler için görüntü Düzenleyicisi) ile çalışma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.image.color
dev_langs:
- C++
helpviewer_keywords:
- images [C++], background colors
- Image editor [C++], Colors Palette
- colors [C++], image
- Colors Palette, Image editor
- palettes, Image editor colors
- foreground colors [C++], Image editor
- colors [C++]
ms.assetid: d34ff96f-241d-494f-abdd-13811ada8cd3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 200c71b6d2196251c8db3542b2b1b2ce88fdff85
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315541"
---
# <a name="working-with-color-image-editor-for-icons"></a>Renklerle Çalışma (Simgeler İçin Görüntü Düzenleyicisi)

**Resim Düzenleyicisi** özellikle işleyen ve renk özelleştirme birçok özellik içerir. Bir ön plan veya arka plan rengini ayarlamak, sınırlanmış alanları rengi ile doldurmak veya bir rengi geçerli bir ön plan veya arka plan rengi olarak kullanılacak bir görüntü seçin. Araçlarını kullanabileceğiniz [Resim Düzenleyicisi araç çubuğu](../windows/toolbar-image-editor-for-icons.md) renk paletindeki açık griyi birlikte [renkler penceresini](../windows/colors-window-image-editor-for-icons.md) görüntüleri oluşturmak için.

Tek renkli ve 16 renk görüntülerini tüm renkleri gösterilen **renkleri** palette **renkleri** penceresi. Ek olarak 16 standart renkler, kendi özel renkler oluşturabilirsiniz. Herhangi bir palet renkleri değiştirme, görüntü içinde karşılık gelen renk hemen değişir.

256-renk simgesi ve imleç görüntü ile çalışırken **renkleri** özelliğinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window) kullanılır. Daha fazla bilgi için [256-renk simgesi veya imleci oluşturma](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md).

> [!NOTE]
> Kullanarak **Resim Düzenleyicisi**, 32 bitlik resimleri görüntüleyebilirsiniz, ancak onları düzenleyemezsiniz.

TRUE-Renk görüntülerini de oluşturulabilir. Ancak gerçek renk örnekleri tam palette görünmez **renkleri** penceresi; bunlar yalnızca ön plan veya arka plan renk göstergesi alanında görüntülenir. Doğru renk kullanılarak oluşturulur [Özel Renk Seçici iletişim kutusu](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md). Daha fazla bilgi için [özelleştirme veya renklerini değiştirme](../windows/customizing-or-changing-colors-image-editor-for-icons.md).

Disk üzerinde özelleştirilmiş renk paletlerini kaydetme ve bunları gerektiği şekilde yeniden yükleyin. En son kullanılan renk paletini kayıt defterine kaydedilen ve Visual Studio'yu yeniden başlattığınızda otomatik olarak yüklenir.

- [Ön plan veya arka plan renklerini seçme](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md)

- [Sınırlı bir alanını görüntü renk ile doldurma](../windows/filling-a-bounded-area-of-an-image-with-a-color-image-editor-for-icons.md)

- [Renk başka yerde kullanmak üzere görüntüden](../windows/picking-up-a-color-from-an-image-to-use-elsewhere-image-editor-for-icons.md)

- [Saydam veya donuk arka plan seçme](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)

- [Seçimdeki renkleri ters çevirme](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md)

- [Renkleri özelleştirme veya değiştirme](../windows/customizing-or-changing-colors-image-editor-for-icons.md)

- [Renk paletlerini kaydetme ve farklı yükleniyor](../windows/saving-and-loading-different-color-palettes-image-editor-for-icons.md)

- [Renkler penceresi](../windows/colors-window-image-editor-for-icons.md)

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Yok.

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)  