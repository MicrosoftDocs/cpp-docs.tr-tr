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
ms.openlocfilehash: 3c0158bfc24eb86f88695b58943989fbb7cac435
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382043"
---
# <a name="tree-control-styles"></a>Ağaç Denetimi Stilleri
Ağaç denetimi ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) stilleri yöneten bir ağaç denetimin görünümünü yönlerini. Ağaç denetimi oluşturduğunuzda, ilk stilleri ayarlama. Alabilir ve kullanarak oluşturduktan sonra ağaç denetimi stilleri değiştirme [GetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633584) ve [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) belirterek Windows işlevleri **GWL_STYLE** için `nIndex` parametresi. Stilleri tam bir listesi için bkz: [ağaç görünümü denetimi pencere stilleri](http://msdn.microsoft.com/library/windows/desktop/bb760013) Windows SDK.  
  
 **TVS_HASLINES** stili alt öğeleri, ilgili üst öğeye bağlamak satırlar çizme tarafından bir ağaç denetimin hiyerarşi grafik gösterimi geliştirir. Bu stili, hiyerarşi kök öğe bağlantı vermiyor. Bunu yapmak için birleştirmeniz gerekir **TVS_HASLINES** ve **TVS_LINESATROOT** stilleri.  
  
 Kullanıcı genişletin veya üst öğesini çift tıklatarak bir üst öğenin alt öğeleri listesi daraltın. Sahip bir ağaç denetimi **TVS_SINGLEEXPAND** stili genişletmek için seçili öğe ve daraltmak için seçili öğe neden olur. Fare tek tıklamayla seçili öğe için kullanılır ve bu öğe kapalı, genişletilir. Seçili öğeyi tek-açık olduğunda tıkladıysanız daraltılmış.  
  
 Sahip bir ağaç denetimi **TVS_HASBUTTONS** stili solundaki her bir üst öğe için bir düğme ekler. Kullanıcı genişletmek veya üst öğeyi çift alternatif olarak alt öğeleri daraltmak için düğmeyi tıklatabilirsiniz. **TVS_HASBUTTONS** düğmeleri hiyerarşi kökünde öğelerine eklemez. Bunu yapmak için birleştirmeniz gerekir **TVS_HASLINES**, **TVS_LINESATROOT**, ve **TVS_HASBUTTONS**.  
  
 **TVS_EDITLABELS** stili mümkün kılar kullanıcı ağaç denetim öğesi etiketleri düzenlemek. Etiketleri düzenleme hakkında daha fazla bilgi için bkz: [ağaç denetimi etiketini düzenleme](../mfc/tree-control-label-editing.md) bu konuda daha sonra.  
  
 **TVS_NOTOOLTIPS** stili, ağaç görünümü denetimleri otomatik araç ipucu özelliğini devre dışı bırakır. Bu özellik, tüm başlığını şu anda görünmüyorsa, fare imleci altında öğesinin içeren bir araç ipucu otomatik olarak görüntüler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTreeCtrl kullanma](../mfc/using-ctreectrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

