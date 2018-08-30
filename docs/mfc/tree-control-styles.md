---
title: Ağaç denetimi stilleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- TVS_SINGLEEXPAND
- TVS_LINESATROOT
- TVS_HASBUTTONS
- TVS_NOTOOLTIPS
- TVS_HASLINES
dev_langs:
- C++
helpviewer_keywords:
- TVS_LINESATROOT [MFC]
- styles [MFC], CTreeCtrl
- styles [MFC], tree control
- TVS_HASLINES
- TVS_SINGLEEXPAND
- CTreeCtrl class [MFC], styles
- TVS_EDITLABELS [MFC]
- TVS_NOTOOLTIPS [MFC]
- TVS_HASBUTTONS [MFC]
- tree controls [MFC], styles
ms.assetid: f43faebd-a355-479e-888a-bf0673d5e1b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2a448d76236c3467228b2aa57cd71284274687ac
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43200437"
---
# <a name="tree-control-styles"></a>Ağaç Denetimi Stilleri
Ağaç denetimi ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) stilleri bir ağaç denetimin görünümünü yönlerini yönetir. Ağaç denetimi oluştururken ilk stilleri ayarlayın. Alabilir ve kullanarak oluşturduktan sonra ağaç denetimi stilleri değiştirme [GetWindowLong](https://msdn.microsoft.com/library/windows/desktop/ms633584) ve [SetWindowLong](https://msdn.microsoft.com/library/windows/desktop/ms633591) belirterek Windows işlevlerini **GWL_STYLE** için *nIndex* parametresi. Stilleri tam bir listesi için bkz. [ağaç görünümü denetiminin pencere stilleri](/windows/desktop/Controls/tree-view-control-window-styles) Windows SDK.  
  
 **TVS_HASLINES** stili alt öğeleri karşılık gelen kendi üst öğesine bağlamak satırları çizerek bir ağaç denetimin hiyerarşi grafik gösterimi geliştirir. Bu stil hiyerarşinin kökündeki öğeleri bağlamak değil. Bunu yapmak için birleştirmeniz gerekir **TVS_HASLINES** ve **TVS_LINESATROOT** stilleri.  
  
 Kullanıcı genişletebilir veya üst öğesini tıklatarak bir üst öğenin alt öğelerinin listesini Daralt. Sahip bir ağaç denetimi **TVS_SINGLEEXPAND** genişletmek için seçilen öğe ve daraltmak için seçili öğe stili neden olur. Fare tek tıklamayla seçili öğe için kullanılır ve bu öğe kapalı, genişletilir. Seçili öğeyi tek-açık olduğunda tıkladıysanız, daraltılmış.  
  
 Sahip bir ağaç denetimi **TVS_HASBUTTONS** stili, her bir üst öğenin sol tarafı bir düğme ekler. Kullanıcı genişletmek veya daraltmak için üst öğe çift alternatif olarak alt öğeler için düğmesine tıklayabilirsiniz. **TVS_HASBUTTONS** düğmeleri hiyerarşi kökündeki öğeleri için eklemez. Bunu yapmak için birleştirebilirsiniz **TVS_HASLINES**, **TVS_LINESATROOT**, ve **TVS_HASBUTTONS**.  
  
 **TVS_EDITLABELS** stil mümkün kılar kullanıcının ağaç denetim öğesi etiketleri düzenle. Etiketleri düzenleme hakkında daha fazla bilgi için bkz. [ağaç denetimi etiketini düzenleme](../mfc/tree-control-label-editing.md) bu konuda.  
  
 **TVS_NOTOOLTIPS** stili, ağaç görünümü denetimleri otomatik araç ipucu özelliğini devre dışı bırakır. Bu özellik otomatik olarak tüm başlığını şu anda görünür değilse, fare imleci altında öğesinin başlığını içeren bir araç ipucu görüntülenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTreeCtrl kullanma](../mfc/using-ctreectrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

