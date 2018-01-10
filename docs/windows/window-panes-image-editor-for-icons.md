---
title: "Pencere bölmeleri (simgeler için görüntü Düzenleyicisi) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.bitmap
- vc.editors.icon
dev_langs: C++
helpviewer_keywords:
- graphics editor [C++]
- Image editor [C++], panes
ms.assetid: d66ea5b3-e2e2-4fc4-aa99-f50022cc690e
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c4b28d49d698f5bc39d8a3915c635c28ecca4193
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="window-panes-image-editor-for-icons"></a>Pencere Bölmeleri (Simgeler İçin Görüntü Düzenleyicisi)
Görüntü Düzenleyicisi penceresinde bir ayırıcı çubukla ayrılan iki bölme görüntü genellikle görüntüler. Bir görünümdür gerçek boyut ve diğer genişletilir (varsayılan büyütme faktörü 6'dır). Bu iki bölme görünümlerinde otomatik olarak güncelleştirilir: bir bölmesinde yaptığınız değişiklikler hemen gösterilen diğer. İki bölmeleri, tek tek piksel ayırt etmek ve kullanabilirsiniz, görüntü boyutu gerçek görünümünü iş etkisi aynı anda gözlemlemek görüntünüzün büyütülmüş bir görünüm üzerinde çalışmak kolaylaştırır.  
  
 Sol bölmede 1:1 büyütme (varsayılan), resmin görünümünü görüntülemek için gerekli olduğu kadar alan (en fazla yarısı görüntü penceresini) kullanır. Sağ bölmeden yakınlaştırılmış görüntünün (varsayılan olarak 6:1 büyütme) görüntüler. Yapabilecekleriniz [büyütme değiştirmek](../windows/changing-the-magnification-factor-image-editor-for-icons.md) her bölmesini kullanarak **Magnıfy** aracındaki [görüntü Düzenleyicisi araç](../windows/toolbar-image-editor-for-icons.md) veya kısayol tuşları kullanarak.  
  
 Görüntü Düzenleyicisi penceresinde küçük bölmesini genişletmek ve büyük bir görüntü farklı bölümlerinin göstermek için iki bölme kullanabilirsiniz. Bölmesinde seçmek için tıklatın.  
  
 İşaretçinin bölünmüş çubuğunda konumlandırma ve bölme çubuğunu sağa veya sola taşıyarak bölmelerin göreli boyutunu değiştirebilirsiniz. Yalnızca bir bölmesinde çalışmak isterseniz bölme çubuğunu taraflardan tüm taşıyabilirsiniz.  
  
 Görüntü Düzenleyicisi bölmesinde 4 veya daha büyük bir faktörüyle genişletilirse, şunları yapabilirsiniz [piksel kılavuzunu görüntüleme](../windows/displaying-or-hiding-the-pixel-grid-image-editor-for-icons.md) tek tek piksel cinsinden görüntü sınırlandırır.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Gereksinimler  
 Yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)

