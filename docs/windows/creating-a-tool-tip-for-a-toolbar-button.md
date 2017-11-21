---
title: "Araç çubuğu düğmesi için araç ipucu oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- tool tips [C++], adding to toolbar buttons
- "\nin tool tip"
- toolbar buttons [C++], tool tips
- buttons [C++], tool tips
- Toolbar editor, creating tool tips
ms.assetid: 0af65342-fd78-4e78-8d0d-dc68f7fc462e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e9399341f19a614783c0f8f873051ed048d89b35
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](https://msdn.microsoft.com/library/f45fce5x.aspx) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](https://msdn.microsoft.com/library/xbx3z216.aspx). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
 Gereksinimler  
  
 MFC ya da ATL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Oluşturma, taşıma ve düzenleme araç çubuğu düğmeleri](../windows/creating-moving-and-editing-toolbar-buttons.md)   
 [Araç çubuğu Düzenleyicisi](../windows/toolbar-editor.md)

