---
title: "Araç çubuğu düğmesi özellikleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- size, toolbar buttons
- toolbar buttons (in Toolbar editor), setting properties
- Toolbar editor, toolbar button properties
- status bars, active toolbar button text
- command IDs, toolbar buttons
- width, toolbar buttons
ms.assetid: b2705814-7c5d-4f24-8f77-07559b0cdda2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 98c78922ee3987bf459f01a62253e9835ad3e377
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="toolbar-button-properties"></a>Araç Çubuğu Düğmesi Özellikleri
Araç çubuğu düğmesi özellikleri şunlardır:  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|**KİMLİĞİ**|Düğme için kimliği tanımlar. Aşağı açılan liste ortak sağlar **kimliği** adları.|  
|**Genişlik**|Düğme genişliğini ayarlar. 16 piksel önerilir.|  
|**Yükseklik**|Düğme yüksekliğini ayarlar. Bir düğme yüksekliğini araç çubuğundaki tüm düğmeleri yüksekliğini değiştiğine dikkat edin. 15 piksel önerilir.|  
|**Sor**|Durum çubuğunda görüntülenen ileti tanımlar. \N ve bir ad ekleme Bu araç çubuğu düğmesi için araç ipucu ekler. Daha fazla bilgi için bkz: [araç ipucu oluşturma](../windows/creating-a-tool-tip-for-a-toolbar-button.md).|  
  
 **Genişlik** ve **yükseklik** tüm düğmelere uygulayın. Araç çubuğu oluşturmak için kullanılan bir bit eşlem 2048 en büyük genişliği vardır. Bu nedenle düğmesi genişlik 512'e ayarlayın, yalnızca dört düğme olabilir ve 513 için genişliği ayarlarsanız, yalnızca üç düğme olabilir.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](https://msdn.microsoft.com/library/f45fce5x.aspx) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](https://msdn.microsoft.com/library/xbx3z216.aspx). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
## <a name="requirements"></a>Gereksinimler  
 MFC ya da ATL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Araç çubuğu düğmesi özelliklerini değiştirme](../windows/changing-the-properties-of-a-toolbar-button.md)   
 [Araç çubuğu Düzenleyicisi](../windows/toolbar-editor.md)

