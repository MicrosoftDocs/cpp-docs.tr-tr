---
title: Ağaç denetimi etiketini düzenleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- editing tree control labels
- CTreeCtrl class [MFC], editing labels
- label editing in CTreeCtrl class [MFC]
- tree controls [MFC], label editing
ms.assetid: 6cde2ac3-43ee-468f-bac2-cf1a228ad32d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7f9ba5360ddce81061bf73839e1700fed57c9fa7
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43210409"
---
# <a name="tree-control-label-editing"></a>Ağaç Denetimi Etiketini Düzenleme
Kullanıcı, doğrudan bir ağaç denetimindeki öğelerin etiketleri düzenleyebilir ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) olan **TVS_EDITLABELS** stili. Kullanıcı odaklı bir öğenin etiketini tıklayarak düzenleme başlar. Bir uygulama kullanarak düzenleme başlamadan [EditLabel](../mfc/reference/ctreectrl-class.md#editlabel) üye işlevi. Ağaç denetimi bildirim düzenlerken başlar ve ne zaman, iptal edildi veya tamamlandı gönderir. Düzenleme işlemi tamamlandığında uygunsa öğenin etiket güncelleştirmek için sorumlu olursunuz.  
  
 Etiket düzenleme başladığı, bir ağaç denetimi gönderen bir [TVN_BEGINLABELEDIT](/windows/desktop/Controls/tvn-beginlabeledit) bildirim iletisi. Bu bildirim işleyerek, bazı etiketler, düzenlemeye izin ver ve diğer düzenlememeyi önleyecek. 0 döndüren düzenlenmesini sağlar ve sıfır olmayan döndüren engeller.  
  
 Bir ağaç denetimi etiketini düzenleme tamamlandı ya da iptal edildiğinde, gönderen bir [TVN_ENDLABELEDIT](/windows/desktop/Controls/tvn-endlabeledit) bildirim iletisi. *LParam* parametredir adresini bir [NMTVDISPINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtvdispinfoa) yapısı. **Öğesi** üyesi olan bir [TVITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtvitema) öğeyi tanımlayan ve düzenlenmiş metni içeren yapısı. Öğenin etiketi, uygunsa, belki de düzenlenen dize doğruladıktan sonra güncelleştirmek için sorumlu olursunuz. *PszText* üyesi `TV_ITEM` düzenleme iptal edilirse 0'dır.  
  
 Etiket, genellikle yanıt olarak düzenleme sırasında [TVN_BEGINLABELEDIT](/windows/desktop/Controls/tvn-beginlabeledit) bildirim iletisini kullanarak etiketi düzenlemek için kullanılan düzenleme denetimi için bir işaretçi alabilirsiniz [GetEditControl](../mfc/reference/ctreectrl-class.md#geteditcontrol) üyesi işlev. Düzenleme denetiminin çağırabilirsiniz [SetLimitText](../mfc/reference/cedit-class.md#setlimittext) bir kullanıcının girebileceği metin ya da alt kesecek ve atmak geçersiz karakterler düzenleme denetimine miktarını sınırlamak için üye işlevi. Ancak, düzenleme denetiminin yalnızca görüntülendiğini unutmayın *sonra* **TVN_BEGINLABELEDIT** gönderilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTreeCtrl kullanma](../mfc/using-ctreectrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

