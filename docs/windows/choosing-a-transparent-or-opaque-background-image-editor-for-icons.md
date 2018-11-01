---
title: Saydam veya Donuk Arka Plan Seçme (Simgeler İçin Görüntü Düzenleyicisi)
ms.date: 11/04/2016
helpviewer_keywords:
- opaque backgrounds [C++]
- colors [C++], image
- Image editor [C++], transparent or opague backgrounds
- images [C++], transparency
- images [C++], opaque background
ms.assetid: 61b743d9-c86b-405d-9a81-0806431b4363
ms.openlocfilehash: a7e4d427a6926d48b5115a1b5bb9ba2ca2d8068c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653537"
---
# <a name="choosing-a-transparent-or-opaque-background-image-editor-for-icons"></a>Saydam veya Donuk Arka Plan Seçme (Simgeler İçin Görüntü Düzenleyicisi)

Taşıdığınızda veya bir görüntüden bir seçimi Kopyala Geçerli arka plan rengiyle uyuşan pikselleri seçimdeki, varsayılan olarak, saydam olan; Hedef konumda piksel gizlememeniz değil.

Donuk bir arka plan için saydam bir arka planından (varsayılan) geçin ve yeniden. Bir seçim aracını kullandığınızda **saydam arka plan** ve **donuk arka plan** seçenekleri görünür **seçeneği** seçicisinde **GörüntüDüzenleyicisi** (aşağıda görüldüğü gibi) araç çubuğu.

![Arka plan seçeneklerini &#45; opak ya da şeffaf](../windows/media/vcimageeditoropaqtranspback.gif "vcImageEditorOpaqTranspBack")<br/>
**Saydam ve donuk seçenekleri** üzerinde **Resim Düzenleyicisi araç çubuğu**

### <a name="to-switch-between-a-transparent-and-opaque-background"></a>Saydam ve donuk arka plan arasında geçiş yapmak için

1. İçinde **görüntü Düzenleyicisi** araç tıklayın **seçeneği** Seçici ve ardından uygun arka plan tıklayın:

   - `Opaque Background (O)`: Varolan bir görüntü seçimi tüm bölümleri tarafından engellenmesidir.

   - `Transparent Background (T)`: Var olan Yansıma geçerli arka plan rengiyle uyuşan parçaları seçimin gösterilmektedir.

\- veya -

- Üzerinde **görüntü** menüsünü seçin veya temizleyin **çizmek opak**.

Bir seçim hangi parçalarının resminin saydam değiştirmek için etkin durumdayken arka plan rengini değiştirebilirsiniz.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Yok.

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Renklerle çalışma](../windows/working-with-color-image-editor-for-icons.md)