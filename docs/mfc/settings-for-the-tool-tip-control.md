---
title: "Aracı ayarlarını ipucu denetimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- tool tips [MFC], activating
- CToolTipCtrl class [MFC], settings
ms.assetid: ff8c5c46-2047-403a-bd98-ffec3d21ee3a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 406e35b6ab694ca972d4cd6add0dcca7586e5005
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="settings-for-the-tool-tip-control"></a>Araç İpucu Denetimi için Ayarlar
Araç ipucunu denetimini ayarlayabilirsiniz ([CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)) etkin veya devre dışı olmalıdır. Etkin olarak ayarladığınızda, araç ipucunu denetimini imleci bir aracı üzerinde olduğunda görüntülenir. Etkin olmayan olarak ayarladığınızda, imleci bir araç olsa bile araç ipucunu denetimini görünmez. Çağrı [etkinleştirme](../mfc/reference/ctooltipctrl-class.md#activate) etkinleştirmek veya bir araç ipucunu denetimini devre dışı bırakmak için.  
  
 İmleç bir aracı üzerinde olduğunda araç ipucu denetimin sahibi penceresini kullanarak etkin veya devre dışı olup olmadığını araç ipucu görüntülemek için bir etkin araç ipucu ayarlayabilirsiniz **TTS_ALWAYSTIP** stili. Bu stili kullanmıyorsanız, araç ipucunu denetimini aracın sahibi penceresi etkin olduğunda, ancak etkin olmadığında görüntülenir.  
  
 Çoğu uygulama araç çubukları menü komutlarına denk araçları içerir. Bu araçlar, karşılık gelen menü öğesi olarak aynı metni görüntülemek araç ipucu denetimi için uygun olur. Sistem denetimi olmadıkça otomatik olarak bir araç ipucu denetimi için geçirilen tüm dizelerden ampersan (&) Hızlandırıcı karakterleri kaldırır. **TTS_NOPREFIX** stili.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CToolTipCtrl kullanma](../mfc/using-ctooltipctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

