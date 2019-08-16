---
title: Ağaç Denetimi Stilleri
ms.date: 11/04/2016
f1_keywords:
- TVS_SINGLEEXPAND
- TVS_LINESATROOT
- TVS_HASBUTTONS
- TVS_NOTOOLTIPS
- TVS_HASLINES
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
ms.openlocfilehash: f5f28025d0349e9bcd95aba50d4110d304fed376
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510943"
---
# <a name="tree-control-styles"></a>Ağaç Denetimi Stilleri

Ağaç denetimi ([Ctreecy](../mfc/reference/ctreectrl-class.md)) stilleri, bir ağaç denetimi görünümünün yönlerini yönetir. Ağaç denetimini oluştururken ilk stilleri ayarlarsınız. Ağaç denetimini oluşturduktan sonra, [GetWindowLong](/windows/win32/api/winuser/nf-winuser-getwindowlongw) ve [SetWindowLong](/windows/win32/api/winuser/nf-winuser-setwindowlongw) Windows Işlevlerini kullanarak, *nIndex* parametresi için **GWL_STYLE** belirterek stilleri alabilir ve değiştirebilirsiniz. Stillerin tüm listesi için bkz. Windows SDK [ağaç görünümü Denetim penceresi stilleri](/windows/win32/Controls/tree-view-control-window-styles) .

**TVS_HASLINES** stili, alt öğeleri karşılık gelen üst öğelerine bağlayan çizgiler çizerek ağaç denetimi hiyerarşisinin grafik gösterimini geliştirir. Bu stil, hiyerarşinin kökündeki öğeleri bağlamaz. Bunu yapmak için **TVS_HASLINES** ve **TVS_LINESATROOT** stillerini birleştirmeniz gerekir.

Kullanıcı üst öğeye çift tıklayarak bir üst öğenin alt öğe listesini genişletebilir veya daraltabilir. **TVS_SINGLEEXPAND** stiline sahip bir ağaç denetimi, öğenin genişlemesine ve seçili öğenin daraltılacak olmasına neden olur. Fare seçili öğeye tek tıklamak için kullanılmışsa ve bu öğe kapalıysa, genişletilir. Seçili öğe açık olduğunda tek tıklanmışsa daraltılır.

**Tvs_hasbuttons** stiline sahip bir ağaç denetimi, her üst öğenin sol tarafına bir düğme ekler. Kullanıcı alt öğeleri genişletmek veya daraltmak için düğmeye tıklayarak üst öğeyi çift tıklayabileceğiniz bir alternatif olarak. **Tvs_hasbuttons** , hiyerarşinin kökündeki öğelere düğme eklemez. Bunu yapmak için **TVS_HASLINES**, **TVS_LINESATROOT**ve **tvs_hasbuttons**birleştirmelisiniz.

**TVS_EDITLABELS** stili, kullanıcının ağaç denetim öğelerinin etiketlerini düzenlemesini mümkün hale getirir. Etiketleri düzenlemeyle ilgili daha fazla bilgi için, bu konunun ilerleyen kısımlarında [Ağaç Denetim etiketi düzenlemesi](../mfc/tree-control-label-editing.md) bölümüne bakın.

**TVS_NOTOOLTIPS** stili, ağaç görünümü denetimlerinin otomatik araç ipucu özelliğini devre dışı bırakır. Bu özellik, tüm başlık Şu anda görünür değilse, fare imleci altındaki öğenin başlığını içeren bir araç ipucunu otomatik olarak görüntüler.

## <a name="see-also"></a>Ayrıca bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
