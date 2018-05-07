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
ms.openlocfilehash: ef74b656cc85fbdcc29c7965b9398a5cbd2f44e8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="tree-control-image-lists"></a>Ağaç Denetim Görüntü Listeleri
Ağaç denetimi her öğe ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) ilişkili eşlemli görüntüleri çifti olabilir. Görüntüleri öğenin etiketi sol tarafında görünür. Bir görüntü öğesi seçilir ve öğe seçilmediğinde diğer görüntülendiğinde görüntülenir. Örneğin, değil seçildiğinde bir öğe seçildiğinde açık bir klasörde ve kapalı klasörü görüntülenebilir.  
  
 Öğe görüntüleri kullanmak için bir resim listesi oluşturarak oluşturmalısınız bir [Cımagelist](../mfc/reference/cimagelist-class.md) nesne ve kullanarak [CImageList::Create](../mfc/reference/cimagelist-class.md#create) ilişkili resim listesi oluşturmak için işlevi. Ardından istenen bit eşlemler listesine ekleyin ve bu listeyi kullanarak ağaç denetimi ile ilişkilendirebilir [SetImageList](../mfc/reference/ctreectrl-class.md#setimagelist) üye işlevi. Varsayılan olarak, tüm öğeleri ilk resmi seçili ve nonselected durumları için resim listesi görüntüler. Öğe ağaç kullanarak denetim eklerken seçili ve nonselected görüntüleri dizinleri belirterek belirli bir öğe için varsayılan davranışı değiştirebilirsiniz [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) üye işlevi. Kullanarak bir öğe ekledikten sonra dizinleri değiştirebilirsiniz [SetItemImage](../mfc/reference/ctreectrl-class.md#setitemimage) üye işlevi.  
  
 Ağaç denetim görüntü listeleri öğesi görüntülerinde koyulan için tasarlanmış bir katmana görüntüleri de içerebilir. Bir katmana görüntü tabanlı dizini bir ağaç denetim öğesi'nin durumu 11 8 bit sıfır olmayan bir değer belirtir (0, hiçbir katmana resim gösterir). 4-bit, tabanlı bir dizin kullanıldığından katmana görüntüleri görüntü listeleri ilk 15 görüntüleri arasında olmalıdır. Ağaç denetim öğesi durumlarına hakkında daha fazla bilgi için bkz: [ağaç denetim öğesi durumlarına genel bakış](../mfc/tree-control-item-states-overview.md) bu konuda daha önce.  
  
 Bir durum resim listesi belirtilirse, ağaç denetimi durumu görüntüsü için her öğenin simgesini solundaki alan ayırır. Bir uygulama durumu görüntüler, denetlenen ve temizlenmiş onay kutularının gibi uygulama tanımlı öğesi durumlarını belirtmek için kullanabilirsiniz. BITS 12 ile 15 sıfır olmayan bir değer durumu görüntü tabanlı dizinini belirtir (0, hiçbir durumu resmi gösterir).  
  
 Belirterek **I_IMAGECALLBACK** değeri görüntünün dizin yerine öğesi hakkında çizilmesi kadar seçili veya nonselected görüntü belirtme geciktirebilir. **I_IMAGECALLBACK** göndererek uygulama dizini için sorgulamak üzere ağaç denetimi yönlendirir [TVN_GETDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773518) bildirim iletisi.  
  
 [GetImageList](../mfc/reference/ctreectrl-class.md#getimagelist) üye işlevi ağaç denetim resim listesi işleyicisini alır. Bu işlev, daha fazla görüntü listesine eklemek gerektiğinde kullanışlı olur. Görüntü listeleri hakkında daha fazla bilgi için bkz: [kullanarak Cımagelist](../mfc/using-cimagelist.md), [Cımagelist](../mfc/reference/cimagelist-class.md) içinde *MFC başvurusu*, ve [görüntü listeleri](http://msdn.microsoft.com/library/windows/desktop/bb761389) içinde Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTreeCtrl kullanma](../mfc/using-ctreectrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

