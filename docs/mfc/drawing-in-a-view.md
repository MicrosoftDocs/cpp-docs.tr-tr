---
title: "Bir görünümde çizim yapma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- drawing [MFC], in views
- views [MFC], printing
- views [MFC], updating
- printing [MFC], views
- views [MFC], rendering
- printing views [MFC]
- paint messages in view class [MFC]
- device contexts, screen drawings
ms.assetid: e3761db6-0f19-4482-a4cd-ac38ef7c4d3a
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3457597edce1b7ce36b132d1bdd16d286cb94d03
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="drawing-in-a-view"></a>Bir Görünümde Çizim Yapma
Neredeyse tüm çizim uygulamanızda görünümün içinde gerçekleşir `OnDraw` görünümü sınıfında geçersiz kılmanız gerekir üye işlevi. (Çizim, ele fare istisnadır [yorumlama kullanıcı girişi aracılığıyla bir görünümü](../mfc/interpreting-user-input-through-a-view.md).) `OnDraw` Geçersiz kıl:  
  
1.  Veri üye işlevleri sağladığınız belge çağırarak alır.  
  
2.  Üye işlevleri framework geçirir bir cihaz bağlamı nesnesinin çağırarak verileri görüntüler `OnDraw`.  
  
 Belge verileri başka bir yolla değiştiğinde görünümü değişiklikleri yansıtacak şekilde yeniden gerekir. Genellikle, kullanıcı belgenin bir görünümü aracılığıyla bir değişiklik yaptığında bu gerçekleşir. Bu durumda, belgenin görünümü çağrıları [UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews) kendilerini güncelleştirmek için aynı belge tüm görünümleri bildirmek için üye işlevi. `UpdateAllViews`Her görünümün çağırır [in](../mfc/reference/cview-class.md#onupdate) üye işlevi. Varsayılan uygulaması `OnUpdate` görünümün tüm istemci alanını geçersiz kılar. Yalnızca istemci alanını belgenin değiştirilmiş bölümleri eşleme bölgelerinin geçersiz kılmak için geçersiz kılabilirsiniz.  
  
 `UpdateAllViews` Sınıfının üye işlevini **CDocument** ve `OnUpdate` sınıfının üye işlevini `CView` belge bölümlerini değiştirildi açıklayan bilgileri geçirdiğiniz izin verir. Bu "İpucu" mekanizması görünümü yeniden boyutlandırmaya gerekir alanı kısıtlamanıza olanak sağlar. `OnUpdate`iki "İpucu" bağımsız değişkeni alır. İlk `lHint`, türü **LPARAM**, istediğiniz, ikinci olmakla herhangi bir veri geçirdiğiniz sağlar `pHint`, türü `CObject`*, türetilmiş herhangi bir nesneye bir işaretçi geçirdiğiniz sağlar `CObject`.  
  
 Görünüm geçersiz hale geldiğinde, Windows, gönderdiği bir `WM_PAINT` ileti. Görünümün [OnPaint](../mfc/reference/cwnd-class.md#onpaint) işleyici işlevi sınıfın bir cihaz bağlamı nesnesi oluşturarak iletisine yanıt [CPaintDC](../mfc/reference/cpaintdc-class.md) ve, görünümün çağırır `OnDraw` üye işlevi. Normalde bir geçersiz kılma yazma gerekmez `OnPaint` işleyici işlevi.  
  
 A [cihaz bağlamı](../mfc/device-contexts.md) bir görüntü veya yazıcı gibi bir aygıtı çizim öznitelikleri hakkında bilgi içeren bir Windows veri yapısıdır. Tüm çizim çağrılar bir aygıt-context nesnesi yapılır. Ekranda çizim `OnDraw` geçirilen bir `CPaintDC` nesnesi. Bir yazıcıda çizim için geçirilen bir [CDC](../mfc/reference/cdc-class.md) nesnesi için geçerli yazıcı ayarlayın.  
  
 Kodunuzu görünümde çizim için ilk belge için bir işaretçi alır ve sonra çizim çağrılar aracılığıyla cihaz bağlamı. Aşağıdaki basit `OnDraw` örnek işlemi gösterilmektedir:  
  
 [!code-cpp[NVC_MFCDocView#1](../mfc/codesnippet/cpp/drawing-in-a-view_1.cpp)]  
  
 Bu örnekte, tanımlayın `GetData` türetilmiş belge sınıfınızın bir üyesi olarak işlev.  
  
 Örnek görünümü içinde ortalanmış belgeden alır ne olursa olsun dize yazdırır. Varsa `OnDraw` çağrıdır ekran çizim için `CDC` nesnesi geçirildi `pDC` olan bir `CPaintDC` olan Oluşturucusu zaten adlı `BeginPaint`. İşlevler çizim çağrılar cihaz bağlamı işaretçiyi yapılır. Cihaz bağlamları ve çizim çağrıları hakkında daha fazla bilgi için bkz [CDC](../mfc/reference/cdc-class.md) içinde *MFC başvurusu* ve [pencere nesneleriyle çalışma](../mfc/working-with-window-objects.md).  
  
 Daha fazla nasıl yazılacağını örnekleri için `OnDraw`, bkz: [MFC örnekleri](../visual-cpp-samples.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görünümleri Kullanma](../mfc/using-views.md)

