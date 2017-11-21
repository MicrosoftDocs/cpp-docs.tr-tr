---
title: "Görüntü listesinden görüntü sürükleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CImageList class [MFC], dragging images from
- dragging images from image lists [MFC]
- image lists [MFC], dragging images from
- images [MFC], dragging from image lists
ms.assetid: af691db8-e4f0-4046-b7b9-9acc68d3713d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ae41d50f227c2fa70091aee4e17bf28a40a9b287
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="dragging-images-from-an-image-list"></a>Görüntü Listesinden Görüntü Sürükleme
[Cımagelist](../mfc/reference/cimagelist-class.md) ekranda görüntü sürükleme işlevler içerir. Sürükleme işlevleri görüntüyü sorunsuz, renk ve imlecin bulunduğu tüm yanıp olmadan taşıyın. Maskelenmiş ve maskelenmemiş görüntüleri sürüklenebilir.  
  
 [BeginDrag başarıyla](../mfc/reference/cimagelist-class.md#begindrag) üye işlevi bir sürükleme işlemi başlar. Parametreleri sürüklemek için resim ve görüntü içindeki etkin nokta konumunu dizini içerir. Etkin nokta görüntünün tam ekran konumu olarak sürükleme işlevleri tanıması tek bir piksel ' dir. Genellikle, bir uygulama etkin nokta ayarlar, böylece fare imlecini, etkin nokta ile örtüşür. [DragMove](../mfc/reference/cimagelist-class.md#dragmove) üye işlevi görüntüyü yeni bir konuma taşır.  
  
 [DragEnter](../mfc/reference/cimagelist-class.md#dragenter) üye işlevi bir pencerede Sürükle görüntünün ilk konumunu ayarlar ve konumunda resim çizer. Parametreleri, görüntü ve penceresi içinde ilk konum koordinatlarını belirten noktası çizmek penceresinde gösteren bir işaretçi içerir. Koordinatlar pencerenin sol üst köşede, istemci alanını göre belirlenir. Aynı tüm koordinatları parametre olarak geçirmesine görüntü sürükleme işlevleri için geçerlidir. Başka bir deyişle, sınır, başlık çubuğu ve menü çubuğunda, gibi pencere öğeleri genişlikleri koordinatları belirtirken dengelemek gerekir. Belirtirseniz bir **NULL** çağrılırken bir pencere tanıtıcının `DragEnter`, masaüstü pencere ile ilişkili aygıt bağlamda resim sürükleme işlevleri çizme ve koordinatlar ekranın sol üst köşesinde göre belirlenir.  
  
 `DragEnter`diğer tüm güncelleştirmeleri verilen penceresine sürükleme işlemi sırasında kilitler. Sürükle ve bırak işlemi, hedef vurgulama gibi bir sürükleme işlemi sırasında herhangi bir çizim yapmanız gerekirse, geçici olarak sürüklenen görüntü kullanarak gizleyebilirsiniz [DragLeave](../mfc/reference/cimagelist-class.md#dragleave) üye işlevi. Aynı zamanda [DragShowNoLock](../mfc/reference/cimagelist-class.md#dragshownolock) üye işlevi.  
  
 Çağrı [EndDrag](../mfc/reference/cimagelist-class.md#enddrag) , bitirdiğinizde görüntü sürükleme.  
  
 [SetDragCursorImage](../mfc/reference/cimagelist-class.md#setdragcursorimage) üye işlevi, geçerli Sürükle görüntüsüyle verilen görüntünün (genellikle bir fare imleci görüntüsü) birleştirerek yeni bir Sürükle görüntüsü oluşturur. Sürükleme işlevleri sürükleme işlemi sırasında yeni görüntüyü kullandığından, Windows'un kullanması gereken [sayı değil geçiş](http://msdn.microsoft.com/library/windows/desktop/ms648396) çağrıldıktan sonra gerçek fare imlecini gizlemek için işlevi `SetDragCursorImage`. Aksi takdirde, sistem iki fare imleçleri sürükleme işlemi boyunca görüntülenebilir.  
  
 Bir uygulama çağırdığında `BeginDrag`, sistem geçici, iç resim listesi oluşturur ve belirtilen kopyaları iç listesine görüntü sürükleyin. Kullanarak geçici Sürükle resim listesi için bir işaretçi alabilirsiniz [GetDragImage](../mfc/reference/cimagelist-class.md#getdragimage) üye işlevi. İşlevi de geçerli Sürükle konumu ve sürükleme görüntü sürükleme konumuna göre uzaklığı alır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Cımagelist kullanma](../mfc/using-cimagelist.md)   
 [Denetimleri](../mfc/controls-mfc.md)

