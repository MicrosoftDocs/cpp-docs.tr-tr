---
title: "Aracı ayarlarını ipucu denetimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- tool tips [MFC], activating
- CToolTipCtrl class [MFC], settings
ms.assetid: ff8c5c46-2047-403a-bd98-ffec3d21ee3a
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c7e88956ab7c7fe1c03d10a8519aedad4767e48e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="settings-for-the-tool-tip-control"></a>Araç İpucu Denetimi için Ayarlar
Araç ipucunu denetimini ayarlayabilirsiniz ([CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)) etkin veya devre dışı olmalıdır. Etkin olarak ayarladığınızda, araç ipucunu denetimini imleci bir aracı üzerinde olduğunda görüntülenir. Etkin olmayan olarak ayarladığınızda, imleci bir araç olsa bile araç ipucunu denetimini görünmez. Çağrı [etkinleştirme](../mfc/reference/ctooltipctrl-class.md#activate) etkinleştirmek veya bir araç ipucunu denetimini devre dışı bırakmak için.  
  
 İmleç bir aracı üzerinde olduğunda araç ipucu denetimin sahibi penceresini kullanarak etkin veya devre dışı olup olmadığını araç ipucu görüntülemek için bir etkin araç ipucu ayarlayabilirsiniz **TTS_ALWAYSTIP** stili. Bu stili kullanmıyorsanız, araç ipucunu denetimini aracın sahibi penceresi etkin olduğunda, ancak etkin olmadığında görüntülenir.  
  
 Çoğu uygulama araç çubukları menü komutlarına denk araçları içerir. Bu araçlar, karşılık gelen menü öğesi olarak aynı metni görüntülemek araç ipucu denetimi için uygun olur. Sistem denetimi olmadıkça otomatik olarak bir araç ipucu denetimi için geçirilen tüm dizelerden ampersan (&) Hızlandırıcı karakterleri kaldırır. **TTS_NOPREFIX** stili.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CToolTipCtrl kullanma](../mfc/using-ctooltipctrl.md)   
 [Denetimleri](../mfc/controls-mfc.md)

