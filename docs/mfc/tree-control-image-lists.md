---
title: Ağaç denetim görüntü listeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- images [MFC], lists in tree controls
- tree controls [MFC], image lists
- CTreeCtrl class [MFC], image lists
ms.assetid: f560c4f2-20d2-4d28-ac33-4017e65fb0a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 184a68ec29e806b5bb914d8744ff5c1f334db5ea
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43203772"
---
# <a name="tree-control-image-lists"></a>Ağaç Denetim Görüntü Listeleri
Ağaç denetimindeki her bir öğe ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) ile ilişkili bit eşlemli görüntülerin çifti olabilir. Görüntüleri bir öğenin etiket sol tarafında görünür. Bir görüntü öğesi seçilir ve diğer öğe seçilmediğinde görüntülendiğinde görüntülenir. Örneğin, yok seçildiğinde bir öğe seçildiğinde bir klasör Aç ve kapalı klasör görüntülenebilir.  
  
 Öğe resimlerinin kullanmak için bir görüntü listesi oluşturarak oluşturmalısınız bir [Cımagelist](../mfc/reference/cimagelist-class.md) nesne ve kullanarak [CImageList::Create](../mfc/reference/cimagelist-class.md#create) ilişkili görüntü listesini oluşturmak için işlevi. Ardından istenen bit eşlemler listeye ekleyin ve bu listeyi kullanarak ağaç denetimi ile ilişkilendirebilir [SetImageList](../mfc/reference/ctreectrl-class.md#setimagelist) üye işlevi. Varsayılan olarak, tüm öğeleri ilk görüntü seçili ve nonselected durumları için resim listesi görüntülenir. Öğesini kullanarak ağaç denetimine eklerken seçilen ve nonselected görüntülerin dizinleri belirterek belirli bir öğe için varsayılan davranışı değiştirebilirsiniz [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) üye işlevi. Kullanarak bir öğe eklendikten sonra dizinleri değiştirebilirsiniz [SetItemImage](../mfc/reference/ctreectrl-class.md#setitemimage) üye işlevi.  
  
 Ağaç denetim görüntü listeleri, öğe görüntülerinde koyulmuş için tasarlanmış katmana görüntüleri de içerebilir. Bir katmana görüntünün bir tabanlı dizinini bit 8 ila 11 arasındaki bir ağaç denetimi öğenin durumu sıfır olmayan bir değer belirtir (0, katmana görüntü gösterir). 4-bit, bir tabanlı bir dizin kullanıldığından katmana görüntüleri görüntü listeleri ilk 15 görüntüleri arasında olmalıdır. Ağaç denetim öğesi durumlarına hakkında daha fazla bilgi için bkz: [ağaç denetim öğesi durumlarına genel bakış](../mfc/tree-control-item-states-overview.md) bu konuda daha önce.  
  
 Durum görüntü listesi belirtilmişse, bir ağaç denetimi durumu görüntüsü her öğenin simgesinin solundaki alanı ayırır. Uygulamanın, uygulama tanımlı öğesi durumları göstermek için onay kutularının işaretli ve işaretsiz gibi durum görüntüleri kullanabilirsiniz. Durum görüntüsünün bir tabanlı dizinini bit 12 ile 15 sıfır olmayan bir değer belirtir (0, durumu görüntü gösterir).  
  
 Belirterek **I_IMAGECALLBACK** değeri bir görüntünün dizinini yerine yaklaşık çizilmesini öğesi olana kadar seçilen veya nonselected görüntü belirtme erteleyebilirsiniz. **I_IMAGECALLBACK** göndererek uygulama dizini için Sorgulanacak ağaç denetimi yönlendirir [TVN_GETDISPINFO](/windows/desktop/Controls/tvn-getdispinfo) bildirim iletisi.  
  
 [GetImageList](../mfc/reference/ctreectrl-class.md#getimagelist) üye işlevi bir ağaç denetim görüntü listesinin tanıtıcı alır. Daha fazla görüntü listeye eklemeniz gerekiyorsa, bu işlev yararlıdır. Görüntü listeleri hakkında daha fazla bilgi için bkz: [Cımagelist kullanma](../mfc/using-cimagelist.md), [Cımagelist](../mfc/reference/cimagelist-class.md) içinde *MFC başvurusu*, ve [görüntü listeleri](https://msdn.microsoft.com/library/windows/desktop/bb761389) içinde Windows SDK'sı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTreeCtrl kullanma](../mfc/using-ctreectrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

