---
title: İletişim kutusu çubukları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, control bars
- CDialogBar class [MFC], dialog bars
- control bars [MFC], dialog bars
- dialog bars
- dialog bars [MFC], about dialog bars
ms.assetid: 485c8055-6bb0-4051-8417-dd2971499321
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c7c68ca2725d25b493003ad7d847176c7dd8d17d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348813"
---
# <a name="dialog-bars"></a>İletişim Kutusu Çubukları
Bir iletişim çubuğu araç, bir tür olduğundan, [denetim çubuğu](../mfc/control-bars.md) herhangi bir tür denetimi içerebilir. Kalıcı olmayan iletişim kutusunun özelliklere sahip olduğu bir [CDialogBar](../mfc/reference/cdialogbar-class.md) nesnesi, daha güçlü bir araç sağlar.  
  
 Araç çubuğu arasında birkaç önemli farklılıklar vardır ve bir `CDialogBar` nesnesi. A `CDialogBar` nesnesi ile Visual C++ iletişim kutusu Düzenleyicisi oluşturabilir ve herhangi bir tür Windows denetimi içerebilir bir iletişim şablonunu kaynaktan, oluşturulur. Kullanıcı denetimine denetiminden sekmesinde. Ve bir hizalama stili üst çerçeve penceresi herhangi bir kısmını ile iletişim çubuğu hizalama veya üst boyutlandırılır durumunda bile yerinde bırakın belirtebilirsiniz. Bir iletişim çubuğu denetimleri çeşitli ile aşağıdaki şekilde gösterilmiştir.  
  
 ![VC iletişim çubuğu](../mfc/media/vc378t1.gif "vc378t1")  
Bir iletişim çubuğu  
  
 İle çalışma diğer bakımlardan bir `CDialogBar` nesnesidir kalıcı olmayan iletişim kutusu ile çalışmayı gibi. Tasarım ve iletişim kutusu kaynağı oluşturmak için iletişim kutusu düzenleyicisi kullanın.  
  
 İletişim kutusu çubukları virtues düğmeleri dışında denetimlerini içerebilir biridir.  
  
 Kendi iletişim sınıflarından normal olsa `CDialog`, genellikle bir iletişim çubuğu için kendi sınıf türetin değil. İletişim kutusu çubukları olan bir ana penceresi ve herhangi bir iletişim çubuğu denetim bildirimi iletileri uzantılar gibi **BN_CLICKED** veya **EN_CHANGE**, iletişim kutusu çubuğu, ana pencereyi üst gönderilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı arabirimi öğeleri](../mfc/user-interface-elements-mfc.md)   
 [Örnek](../visual-cpp-samples.md)

