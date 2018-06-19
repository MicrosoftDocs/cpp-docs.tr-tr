---
title: 'Sürükle ve bırak: bir bırakma hedefi uygulama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE drag and drop [MFC], implementing drop targets
- OLE drag and drop [MFC], drop target
- drag and drop [MFC], drop target
ms.assetid: 0689f1ec-5326-4008-b226-4b373c881358
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 414437f044869fef7ae48883a88688ad50c9ac5f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344275"
---
# <a name="drag-and-drop-implementing-a-drop-target"></a>Sürükle ve Bırak: Bir Bırakma Hedefi Uygulama
Bu makalede bir bırakma hedefi uygulamanızı nasıl özetlenmektedir. Bırakma hedefi uygulama bir bırakma kaynağı uygulama değerinden biraz daha fazla iş alır ancak hala oldukça basit bir işlemdir. Bu teknikler OLE olmayan uygulamalar için de geçerlidir.  
  
#### <a name="to-implement-a-drop-target"></a>Bırakma hedefi uygulama  
  
1.  Her bir görünümde bir bırakma hedefi olmasını istediğiniz uygulama için bir üye değişkeni ekleyin. Bu üye değişkeni türü olmalıdır `COleDropTarget` veya ondan türetilmiş bir sınıf.  
  
2.  İşler görünümü sınıfınızın işlevden `WM_CREATE` ileti (genellikle `OnCreate`), yeni üye değişkenin çağrı `Register` üye işlevi. `Revoke` görünümünüzü kaldırıldığı zaman otomatik olarak sizin için çağrılır.  
  
3.  Aşağıdaki işlevleri geçersiz kılar. Uygulamanızın genelinde aynı davranışı istiyorsanız, bu view sınıfı işlevleri geçersiz kılar. Yalıtılmış durumlarda davranışını değiştirmek veya dışı bırakarak etkinleştirmek istediğiniz istiyorsanız`CView` windows, bu işlevleri geçersiz kılma, `COleDropTarget`-türetilmiş sınıf.  
  
    |Geçersiz kıl|İzin vermek için|  
    |--------------|--------------|  
    |`OnDragEnter`|Bırakma işlemleri penceresinde gerçekleşecek. İmleç ilk penceresi girdiğinde çağrılır.|  
    |`OnDragLeave`|Sürükleme işlemi belirtilen pencere ayrıldığında özel davranışı.|  
    |`OnDragOver`|Bırakma işlemleri penceresinde gerçekleşecek. İmleç penceresi sürüklendiğinde çağrılır.|  
    |`OnDrop`|Belirtilen penceresine bırakılan veri işleme.|  
    |`OnScrollBy`|Kaydırma hedef penceresinde gerekli olduğunda özel davranışı.|  
  
 MAINVIEW bakın. CPP dosya başka bir deyişle MFC OLE örnek bölümü [OCLIENT](../visual-cpp-samples.md) bir örneği bu işlevlerin nasıl birlikte çalışır.  
  
 Daha fazla bilgi için bkz.:  
  
-   [Bırakma kaynağı uygulama](../mfc/drag-and-drop-implementing-a-drop-source.md)  
  
-   [Oluşturma ve OLE veri nesneleri ve veri kaynaklarını yok etme](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [OLE veri nesneleri ve veri kaynakları düzenleme](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sürükleme ve bırakma (OLE)](../mfc/drag-and-drop-ole.md)   
 [COleDropTarget Sınıfı](../mfc/reference/coledroptarget-class.md)
