---
title: Özel fırça (simgeler için görüntü Düzenleyicisi) oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- colors [C++], brush
- brushes, colors
- brushes, creating custom
- images [C++], creating custom brushes
- graphics [C++], custom brushes
- custom brushes
ms.assetid: 750881aa-6f47-4de9-8ca6-a7a12afc6383
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bd4a25b208232c8a0923e33156730fc5612219a5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388205"
---
# <a name="creating-a-custom-brush-image-editor-for-icons"></a>Özel Fırça Oluşturma (Simgeler İçin Görüntü Düzenleyicisi)

Özel fırça almak ve biri gibi kullanabileceğiniz görüntünün dikdörtgen kısmıdır **görüntü** düzenleyicinin hazır Fırçalar. Seçime göre gerçekleştirebileceğiniz tüm işlemler bir özel fırça üzerinde gerçekleştirebilirsiniz.

### <a name="to-create-a-custom-brush-from-a-portion-of-an-image"></a>Bir görüntüyü bölümünden özel Fırça oluşturma

1. [Görüntünün seçin](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md) fırça için kullanmak istediğiniz.

2. Bulunduran **Shift** aşağı anahtar, seçimdeki tıklayın ve görüntünün arasında sürükleyin.

   \- veya -

3. Gelen **görüntü** menüsünde seçin **fırça olarak kullanma seçimi**.

   Seçimdeki renkleri arasında görüntüyü dağıtır özel bir fırça seçiminizi olur. Seçimin bir kopyasını sürükleyerek yol boyunca bırakılır. Daha yavaş sürükleyin, kopya yapılmaz.

   > [!NOTE]
   > Tıklayarak **seçimi bir fırça olarak kullanma** olmadan önce görüntünün bir kısmı seçerek görüntünün tamamını fırça olarak kullanır. Özel fırça kullanarak sonucu olup, seçtiğiniz üzerinde de bağlıdır bir [opak veya saydam arka plan](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).

Özel fırça geçerli arka plan rengiyle uyuşan piksellerde normalde saydam: var olan görüntünün üzerine boyama değil. Mevcut görüntü arka plan rengi piksel boyama bu davranışı değiştirebilirsiniz.

Özel efektler çeşitli oluşturmak için özel bir fırça gibi bir damga ya da bir şablon kullanabilirsiniz.

### <a name="to-draw-custom-brush-shapes-in-the-background-color"></a>Arka plan rengi özel fırça şekiller çizmek için

1. [Donuk veya saydam bir arka plan seçme](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).

2. [Arka plan rengini ayarlamak](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md) çizmek istediğiniz rengi.

3. Özel fırça çizmek istediğiniz yere getirin.

4. Sağ fare düğmesine tıklayın. Arka plan rengi özel fırça donuk tüm bölümlerinin çekilir.

### <a name="to-double-or-halve-the-custom-brush-size"></a>Özel fırça boyutunu edilmesiyle yarıya ya da çift

1. Basın **artı** (**+**) fırça boyutunu çift anahtarı veya **eksi işareti** (**-**), edilmesiyle yarıya için anahtarı .

### <a name="to-cancel-the-custom-brush"></a>Özel fırça iptal etmek için

1. Tuşuna **Esc** veya başka bir çizim Aracı'nı seçin.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Yok.

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Grafik kaynakları düzenleme](../windows/editing-graphical-resources-image-editor-for-icons.md)<br/>
[Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)