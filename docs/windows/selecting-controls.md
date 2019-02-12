---
title: Denetimleri Seçme
ms.date: 11/04/2016
helpviewer_keywords:
- Dialog Editor [C++], selecting controls
- dominant controls
- dialog box controls [C++], selecting in editor
- controls [C++], selecting
- size, controls
- controls [C++], dominant
- controls [C++], removing from groups
- Dialog Editor [C++], dominant control
ms.assetid: 27f05450-4550-4229-9f4c-2c9e06365596
ms.openlocfilehash: a0a21942f6e2c37b96a7a704fadbb9bacc4761c8
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56149680"
---
# <a name="selecting-controls"></a>Denetimleri Seçme

Boyuta denetimleri seçin, hizalama, taşıyın, kopyalayın, veya silin ve ardından istediğiniz işlemi tamamlayın. Çoğu durumda, boyutu ve hizalama araçları kullanmak üzere birden fazla denetim seçmeniz gerekir [iletişim kutusu araç çubuğunu](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).

Bir denetim seçili durumdayken, etrafında gölgeli bir kenarlık kesintisiz (etkin) sahip veya boş (etkin olmayan) "boyutlandırma tutamaçlarını" küçük kareler, zaman içinde seçim kenarlığı görüntülenir. Birden çok Denetim seçildiğinde, baskın denetimi düz boyutlandırma ve diğer seçilen tüm denetimleri boş boyutlandırma tutamaçlarını sahip olduğunuz.

Boyutlandırma ya da birden çok denetimi hizalama **iletişim** Düzenleyicisi kullanır "baskın denetimi" diğer denetimlerin nasıl boyutlandırılmış veya hizalı belirlemek için. Varsayılan olarak, baskın denetim seçili ilk bir denetimdir.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="to-select-multiple-controls"></a>Birden çok denetim seçin

1. İçinde [araç penceresi](/visualstudio/ide/reference/toolbox)seçin **işaretçi** aracı.

1. İletişim kutusunda istediğiniz denetimlerin çevresinde bir seçim kutusu çizmek için işaretçiyi sürükleyin.

   Fare düğmesini bıraktığınızda, tüm denetimleri iç ve seçim kutusu seçili kesişen.

   \- veya -

   Basılı **Shift** anahtar ve seçime dahil etmek istediğiniz denetimleri seçin.

   \- veya -

   Basılı **Ctrl** anahtar ve seçime dahil etmek istediğiniz denetimleri seçin.

## <a name="to-remove-a-control-from-a-group-of-selected-controls-or-to-add-a-control-to-a-group-of-selected-controls"></a>Bir denetim seçili denetimlerin bir gruptan kaldırmak için veya bir denetim seçili denetimlerin bir gruba eklemek için

1. Seçili denetimleri grubuyla basılı **Shift** anahtar ve mevcut seçime Ekle veya kaldırmak istediğiniz denetimi seçin.

   > [!NOTE]
   > Basılı **Ctrl** anahtarı ve bir seçim içindeki bir kontrolü seçme hale getirir, bu seçimdeki baskın denetim.

## <a name="to-specify-the-dominant-control"></a>Baskın denetimi belirtmek için

1. Basılı **Ctrl** anahtar ve diğer denetimleri konumunu ve boyutunu etkilemek için kullanmak istediğiniz denetimi *ilk*.

> [!NOTE]
> Bağımlı denetimlerin tutamaçları boş baskın denetimi boyutlandırma tutamaçlarını düz bağlıdır. Baskın denetimi tüm daha fazla yeniden boyutlandırma veya hizalama temel alır.

## <a name="to-change-the-dominant-control"></a>Baskın denetimi değiştirmek için

1. Şu anda seçili tüm denetimlerin dışındaki tıklayarak geçerli seçimi temizleyin.

1. Farklı bir denetim ilk seçerek önceki yordamı yineleyin.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)<br/>
[Denetimler](../mfc/controls-mfc.md)