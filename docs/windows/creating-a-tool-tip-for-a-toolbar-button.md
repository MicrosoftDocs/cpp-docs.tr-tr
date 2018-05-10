---
title: Araç çubuğu düğmesi için araç ipucu oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tool tips [C++], adding to toolbar buttons
- "\nin tool tip"
- toolbar buttons [C++], tool tips
- buttons [C++], tool tips
- Toolbar editor, creating tool tips
ms.assetid: 0af65342-fd78-4e78-8d0d-dc68f7fc462e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 41c2fa538a7888a2f14ae34fde9133b2872d13ba
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="creating-a-tool-tip-for-a-toolbar-button"></a>Araç Çubuğu Düğmesi İçin Araç İpucu Oluşturma
### <a name="to-create-a-tool-tip"></a>Araç İpucu oluşturmak için  
  
1.  Araç çubuğu düğmesini seçin.  
  
2.  İçinde [Özellikler penceresini](/visualstudio/ide/reference/properties-window), **komut istemi** özellik alanı düğmesinin ileti sonra; durum çubuğu için bir açıklama ekleyin, \n ve araç ipucu adı ekleyin.  
  
 Bir ortak bir araç ipucu WordPad bulunan Yazdır düğmesine örneğidir:  
  
 1. WordPad'i açmak.  
  
 2. Fare işaretçisini üzerine gelerek **yazdırma** araç çubuğu düğmesi.  
  
 3. Word 'yazdırma' artık bildirim altında fare işaretçisini kayan.  
  
 4. Durum çubuğu (en altında WordPad penceresinin) bakmak - bunu şimdi metni "etkin belgeyi yazdırır" gösterdiğine dikkat edin.  
  
 "Araç ipucu adı" Adım 3 'yazdırma', 'yazdırır etkin belgeyi' adım 4'ten ise "açıklaması durum çubuğu düğmesini."  
  
 Bu efekti kullanarak istiyorsanız **araç** Düzenleyicisi, ayarladığınız **komut istemi** özelliğine **etkin document\nPrint yazdırır**.  
  
> [!NOTE]
>  Komut istemi metni kullanarak düzenleyebilirsiniz [Özellikler penceresini](/visualstudio/ide/reference/properties-window).  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
 Gereksinimler  
  
 MFC ya da ATL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Oluşturma, taşıma ve düzenleme araç çubuğu düğmeleri](../windows/creating-moving-and-editing-toolbar-buttons.md)   
 [Araç Çubuğu Düzenleyicisi](../windows/toolbar-editor.md)

