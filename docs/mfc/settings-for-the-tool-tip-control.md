---
title: Aracı ayarlarını ipucu denetimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tool tips [MFC], activating
- CToolTipCtrl class [MFC], settings
ms.assetid: ff8c5c46-2047-403a-bd98-ffec3d21ee3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 39de60d17dae5a6d7b2965350162117d049c29c8
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951120"
---
# <a name="settings-for-the-tool-tip-control"></a>Araç İpucu Denetimi için Ayarlar
Araç ipucunu denetimini ayarlayabilirsiniz ([CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)) etkin veya devre dışı olmalıdır. Etkin olarak ayarladığınızda, araç ipucunu denetimini imleci bir aracı üzerinde olduğunda görüntülenir. Etkin olmayan olarak ayarladığınızda, imleci bir araç olsa bile araç ipucunu denetimini görünmez. Çağrı [etkinleştirme](../mfc/reference/ctooltipctrl-class.md#activate) etkinleştirmek veya bir araç ipucunu denetimini devre dışı bırakmak için.  
  
 İmleç bir aracı üzerinde olduğunda araç ipucu denetimin sahibi penceresi TTS_ALWAYSTIP stil kullanarak etkin veya devre dışı olup olmadığını araç ipucu görüntülemek için bir etkin araç ipucu ayarlayabilirsiniz. Bu stili kullanmıyorsanız, araç ipucunu denetimini aracın sahibi penceresi etkin olduğunda, ancak etkin olmadığında görüntülenir.  
  
 Çoğu uygulama araç çubukları menü komutlarına denk araçları içerir. Bu araçlar, karşılık gelen menü öğesi olarak aynı metni görüntülemek araç ipucu denetimi için uygun olur. Denetim TTS_NOPREFIX stilde sürece sistem ampersan (&) tüm dizeleri Hızlandırıcı karakterlerinden bir araç ipucu denetimi için geçirilen otomatik olarak kaldırır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CToolTipCtrl kullanma](../mfc/using-ctooltipctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

