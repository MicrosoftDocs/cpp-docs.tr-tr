---
title: 'Sürükle ve bırak: özelleştirme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- drag and drop [MFC], implementing in non-OLE applications
- drag and drop [MFC], customizing behavior
- drag and  [MFC], COleDataSource object
- drag and drop [MFC], calling DoDragDrop
- OLE drag and drop [MFC], customizing behavior
ms.assetid: 03369d3e-46bf-4140-b58c-d0c9657cf38a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 59ec5a5a493106750fa7bb8c7ec31b8dbb011070
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344249"
---
# <a name="drag-and-drop-customizing"></a>Sürükle ve Bırak: Özelleştirme
Sürükle ve bırak özelliğinin varsayılan uygulama, çoğu uygulama için yeterlidir. Ancak, bazı uygulamalarda bu standart davranış değiştirilmesi gerekebilir. Bu makalede bu varsayılanları değiştirmek için gerekli adımları açıklanmaktadır. Ayrıca, bileşik belgeler açılan kaynakları olarak desteklemeyen uygulamalar oluşturmak için bu tekniği kullanabilirsiniz.  
  
 Standart OLE sürükle ve bırak davranışını özelleştirme veya OLE dışı uygulama varsa, oluşturmalısınız bir `COleDataSource` verileri içeren nesne. Kullanıcı bir Sürükle ve bırak işlemi başladığında, kodunuzu çağırmalıdır `DoDragDrop` sürükle ve bırak işlemleri destekleyen diğer sınıflardan yerine bu nesneden işlevi.  
  
 İsteğe bağlı olarak, oluşturabileceğiniz bir `COleDropSource` açılır denetlemek ve bazı işlevlerini değiştirmek istediğiniz davranışı türüne bağlı olarak geçersiz kılmak için nesne. Bu açılan kaynak nesnesi sonra geçirilir `COleDataSource::DoDragDrop` bu işlevler varsayılan davranışını değiştirmek için. Bu farklı seçenekler, uygulamanızda sürükle ve bırak işlemleri desteklemek nasıl esneklik büyük bir bölümünü izin verin. Veri kaynakları hakkında daha fazla bilgi için bkz: [veri nesneleri ve veri kaynakları (OLE)](../mfc/data-objects-and-data-sources-ole.md).  
  
 Sürükle ve bırak işlemleri özelleştirmek için aşağıdaki işlevleri geçersiz kılabilirsiniz:  
  
|Geçersiz kıl|Özelleştirmek için|  
|--------------|------------------|  
|`OnBeginDrag`|Çağırdıktan sonra nasıl sürükleyerek başlatılan `DoDragDrop`.|  
|`GiveFeedback`|Farklı açılan sonuçlar için imlecin görünümü gibi görsel geri bildirim.|  
|`QueryContinueDrag`|Sürükle ve bırak işlemi sonlandırma. Bu işlev sürükleme işlemi sırasında değiştiricisi anahtar durumlar denetlemenizi sağlar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sürükleme ve bırakma (OLE)](../mfc/drag-and-drop-ole.md)   
 [COleDropSource sınıfı](../mfc/reference/coledropsource-class.md)   
 [COleDataSource Sınıfı](../mfc/reference/coledatasource-class.md)
