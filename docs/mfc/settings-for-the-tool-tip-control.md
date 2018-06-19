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
ms.openlocfilehash: 4b61fb9450e6206c8f96102b5feeec6fbf3bead3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379957"
---
# <a name="settings-for-the-tool-tip-control"></a>Araç İpucu Denetimi için Ayarlar
Araç ipucunu denetimini ayarlayabilirsiniz ([CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)) etkin veya devre dışı olmalıdır. Etkin olarak ayarladığınızda, araç ipucunu denetimini imleci bir aracı üzerinde olduğunda görüntülenir. Etkin olmayan olarak ayarladığınızda, imleci bir araç olsa bile araç ipucunu denetimini görünmez. Çağrı [etkinleştirme](../mfc/reference/ctooltipctrl-class.md#activate) etkinleştirmek veya bir araç ipucunu denetimini devre dışı bırakmak için.  
  
 İmleç bir aracı üzerinde olduğunda araç ipucu denetimin sahibi penceresini kullanarak etkin veya devre dışı olup olmadığını araç ipucu görüntülemek için bir etkin araç ipucu ayarlayabilirsiniz **TTS_ALWAYSTIP** stili. Bu stili kullanmıyorsanız, araç ipucunu denetimini aracın sahibi penceresi etkin olduğunda, ancak etkin olmadığında görüntülenir.  
  
 Çoğu uygulama araç çubukları menü komutlarına denk araçları içerir. Bu araçlar, karşılık gelen menü öğesi olarak aynı metni görüntülemek araç ipucu denetimi için uygun olur. Sistem denetimi olmadıkça otomatik olarak bir araç ipucu denetimi için geçirilen tüm dizelerden ampersan (&) Hızlandırıcı karakterleri kaldırır. **TTS_NOPREFIX** stili.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CToolTipCtrl kullanma](../mfc/using-ctooltipctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

