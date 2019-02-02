---
title: Pencere Bölmeleri (Simgeler İçin Görüntü Düzenleyicisi)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.bitmap
- vc.editors.icon
helpviewer_keywords:
- graphics editor [C++]
- Image editor [C++], panes
- Image editor [C++], magnification
- grids, pixel
- pixel grid, Image editor
- Image editor [C++], pixel grid
- Image editor [C++], grid settings
- grid settings, Image editor
ms.assetid: d66ea5b3-e2e2-4fc4-aa99-f50022cc690e
ms.openlocfilehash: 72b7cf056147cdbd216d861f0e710da423951c5a
ms.sourcegitcommit: efcc8c97570ddf7631570226c700e8f6ebb6c7be
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2019
ms.locfileid: "55560315"
---
# <a name="window-panes-image-editor-for-icons"></a>Pencere Bölmeleri (Simgeler İçin Görüntü Düzenleyicisi)

**Resim Düzenleyicisi** penceresi genellikle görüntüler görüntüyü bir ayırıcı çubukla ayırarak iki bölme. Bir görünümdür gerçek boyut ve diğer genişletilir (varsayılan büyütme faktörü 6'dır). Bu iki bölme görünümlerde otomatik olarak güncelleştirilir: bir bölmesinde yaptığınız değişiklikler hemen gösterilen diğer. İki bölme içinde tek tek her piksel ayırmak ve kullanabilirsiniz, aynı zamanda, görüntünün boyutu gerçek görünümünü iş etkisi gözlemleyin görüntünüzü genişletilmiş bir görünüm üzerinde çalışmayı kolaylaştırır.

Sol bölmede gerektiği kadar bu alanı kullanır (en fazla yarısını **görüntü** pencere) görüntünüzü 1:1 büyütme görünümünü (varsayılan) görüntülemek için. Sağ bölmede, yakınlaştırılmış görüntü (varsayılan olarak 6:1 büyütme) görüntüler. Her bölmesini kullanarak büyütme değiştirebilirsiniz **Magnıfy** aracındaki [Resim Düzenleyicisi araç çubuğu](../windows/toolbar-image-editor-for-icons.md) veya kısayol tuşları kullanarak.

Daha küçük bölmesinde genişletebilirsiniz **Resim Düzenleyicisi** penceresi ve büyük bir görüntü, farklı bölgelerde göstermek için iki bölme kullanın. Seçmek için içinde Bölmesi'ni seçin.

İşaretçinin bölünmüş çubuğunda konumlandırma ve bölme çubuğunu sağa veya sola taşıyarak bölmelerin göreli boyutlarını değiştirebilirsiniz. Yalnızca bir bölmesinde çalışmak istiyorsanız bölme çubuğunu taraflardan tüm taşıyabilirsiniz.

Varsa **Resim Düzenleyicisi** bölmesi faktörü olarak 4 ile genişletilmiş veya daha büyük, tek tek her piksel görüntüde sınırlandıran bir piksel kılavuzunu görüntüleyebilir.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="to-change-the-magnification-factor"></a>Büyütme katsayısını değiştirmek için

Varsayılan olarak, **görüntü** Düzenleyicisi gerçek boyutta sol bölmede görünümü gösterilir ve görünüm 6 sağ bölmesinde zaman gerçek boyut. Büyütme katsayısını (çalışma alanı altındaki durum çubuğunda görülen) resmi gerçek boyutuna ve görüntülenen boyut arasındaki oran ' dir. Varsayılan faktörü 6 ve aralık 1 ile 10.

1. Seçin **Resim Düzenleyicisi** Büyütme katsayısı değiştirmek istediğiniz bölmesi.

1. Üzerinde [Resim Düzenleyicisi araç çubuğu](../windows/toolbar-image-editor-for-icons.md), sağındaki oku seçerek [Büyüteç aracına](../windows/toolbar-image-editor-for-icons.md) katsayısını menüden seçin: **1 X**, **2 X**, **6 X**, veya **8 X**.

   > [!NOTE]
   > Katsayısını listelenenler dışında seçilecek **Magnıfy** aracı, kısayol tuşlarını kullanın.

## <a name="to-display-or-hide-the-pixel-grid"></a>Görüntülenecek veya piksel kılavuzunu Gizle

Tüm **Resim Düzenleyicisi** bölmeleri katsayısını 4 veya daha büyük ile tek tek her piksel görüntüde sınırlandıran bir kılavuz görüntüleyebilirsiniz.

1. Üzerinde **görüntü** menüsünde **Kılavuz ayarları**.

1. Seçin **piksel kılavuzunu** onay kutusunu kılavuz görüntülemek veya ızgarasını için onay kutusunu temizleyin.

> [!TIP]
> İmlecinizi bir araç çubuğu düğmenin üzerine geldiğinizde araç ipuçlarında görünür. Bu ipuçları her düğmesinin işlevini belirlemenize yardımcı olabilir.

## <a name="requirements"></a>Gereksinimler

Hiçbiri

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı Tuşları](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)