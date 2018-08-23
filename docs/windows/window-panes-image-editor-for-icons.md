---
title: Pencere bölmeleri (simgeler için görüntü Düzenleyicisi) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.bitmap
- vc.editors.icon
dev_langs:
- C++
helpviewer_keywords:
- graphics editor [C++]
- Image editor [C++], panes
ms.assetid: d66ea5b3-e2e2-4fc4-aa99-f50022cc690e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 02cc8fed4056199787c3108d287945bb8a0ae7dd
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42594112"
---
# <a name="window-panes-image-editor-for-icons"></a>Pencere Bölmeleri (Simgeler İçin Görüntü Düzenleyicisi)

**Resim Düzenleyicisi** penceresi genellikle görüntüler görüntüyü bir ayırıcı çubukla ayırarak iki bölme. Bir görünümdür gerçek boyut ve diğer genişletilir (varsayılan büyütme faktörü 6'dır). Bu iki bölme görünümlerde otomatik olarak güncelleştirilir: bir bölmesinde yaptığınız değişiklikler hemen gösterilen diğer. İki bölme içinde tek tek her piksel ayırmak ve kullanabilirsiniz, aynı zamanda, görüntünün boyutu gerçek görünümünü iş etkisi gözlemleyin görüntünüzü genişletilmiş bir görünüm üzerinde çalışmayı kolaylaştırır.

Sol bölmede gerektiği kadar bu alanı kullanır (en fazla yarısını **görüntü** pencere) görüntünüzü 1:1 büyütme görünümünü (varsayılan) görüntülemek için. Sağ bölmede, yakınlaştırılmış görüntü (varsayılan olarak 6:1 büyütme) görüntüler. Yapabilecekleriniz [büyütme değiştirme](../windows/changing-the-magnification-factor-image-editor-for-icons.md) her bölmesini kullanarak **Magnıfy** aracındaki [Resim Düzenleyicisi araç çubuğu](../windows/toolbar-image-editor-for-icons.md) veya kısayol tuşları kullanarak.

Daha küçük bölmesinde genişletebilirsiniz **Resim Düzenleyicisi** penceresi ve büyük bir görüntü, farklı bölgelerde göstermek için iki bölme kullanın. Bölmesinde seçmek için tıklayın.

İşaretçinin bölünmüş çubuğunda konumlandırma ve bölme çubuğunu sağa veya sola taşıyarak bölmelerin göreli boyutlarını değiştirebilirsiniz. Yalnızca bir bölmesinde çalışmak istiyorsanız bölme çubuğunu taraflardan tüm taşıyabilirsiniz.

Varsa **görüntü Düzenleyicisi** bölmesi faktörü olarak 4 ile genişletilmiş veya daha büyük, yapabilecekleriniz [piksel kılavuzunu görüntüleme](../windows/displaying-or-hiding-the-pixel-grid-image-editor-for-icons.md) , tek tek her piksel görüntüde sınırlandırır.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Yok.

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)  
[Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)