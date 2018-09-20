---
title: Bir görünümde çizim yapma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d3df6ac176669114c70ebdd17985068d6b383c37
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398813"
---
# <a name="drawing-in-a-view"></a>Bir Görünümde Çizim Yapma

Görünümün neredeyse tüm çizim uygulamanızda gerçekleşir `OnDraw` görünümü sınıfınızda geçersiz kılmanız gerekir üye işlevi. (Çizim, ele fare istisnadır [yorumlama kullanıcı girişi aracılığıyla bir görünümü](../mfc/interpreting-user-input-through-a-view.md).) `OnDraw` Geçersiz kıl:

1. Belge sağladığınız üye işlevlerini çağırarak verileri alır.

1. Framework geçirir bir cihaz bağlamı nesnesinin üye işlevlerini çağırarak verileri görüntüler `OnDraw`.

Bir belgenin verilerinin herhangi bir şekilde değiştiğinde görünüm değişiklikleri yansıtacak şekilde yeniden gerekir. Bu genellikle kullanıcının belgeye bir görünüm aracılığıyla bir değişiklik yaptığında gerçekleşir. Bu durumda, belgenin görünümü çağrıları [UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews) kendilerini güncelleştirmek için aynı belgedeki tüm görünümlerde bildirmek için üye işlevi. `UpdateAllViews` Her görünüm çağırır [OnUpdate](../mfc/reference/cview-class.md#onupdate) üye işlevi. Varsayılan uygulaması `OnUpdate` görünümün tüm istemci alanını geçersiz kılar. Bu yalnızca istemci alanını eşlemek için belgenin değiştirilmiş bölümleri bölgeleri geçersiz kılabilirsiniz.

`UpdateAllViews` Sınıfının üye işlevinde `CDocument` ve `OnUpdate` sınıfının üye işlevinde `CView` belgenin hangi bölümlerinin değiştirilmiş açıklayan bilgileri geçirdiğiniz sağlar. Bu "İpucu" mekanizması görünümü yeniden çizmeniz gerekir alan kısıtlamanıza olanak tanır. `OnUpdate` iki "İpucu" bağımsız değişkeni alır. Birincisi, *lHint*, türü **LPARAM**, istediğiniz gibi ikinci olmakla birlikte, tüm verileri sağlar *pHint*, türü `CObject`*, türetilmiş herhangi bir nesne, geçirdiğiniz bir işaretçi sağlar gelen `CObject`.

Görünüm geçersiz hale geldiğinde, Windows, gönderdiği bir **WM_PAINT** ileti. Görünümün [OnPaint](../mfc/reference/cwnd-class.md#onpaint) işleyici işlevi, bir cihaz bağlamındaki nesne sınıfı oluşturarak iletiye yanıt [CPaintDC](../mfc/reference/cpaintdc-class.md) ve görünümünüzün çağırır `OnDraw` üye işlevi. Normalde bir geçersiz kılma yazma gerekmez `OnPaint` işleyicisi işlevi.

A [cihaz bağlamı](../mfc/device-contexts.md) bir cihazın bir görüntü veya yazıcı gibi çizim öznitelikleri hakkında bilgi içeren bir Windows veri yapısıdır. Tüm çizim çağrıları, bir cihaz bağlamındaki nesne ile yapılır. Ekranda çizim `OnDraw` geçirilen bir `CPaintDC` nesne. Yazıcı çizmek için geçirilen bir [CDC](../mfc/reference/cdc-class.md) nesne geçerli yazıcıyı ayarlayın.

Görünümü çizmek için kodunuzu ilk belgeye bir işaretçi alır, ardından cihaz bağlamı aracılığıyla çizim çağrısı yapar. Aşağıdaki basit `OnDraw` örnek işlemini gösterir:

[!code-cpp[NVC_MFCDocView#1](../mfc/codesnippet/cpp/drawing-in-a-view_1.cpp)]

Bu örnekte tanımlayın `GetData` belge türetilmiş sınıfınızın bir üye olarak işlev.

Örnek Görünümü'nde ortalanmış belgeden alır herhangi bir dize yazdırır. Varsa `OnDraw` çağrıdır ekran çizim için `CDC` geçirilen nesne *pDC* olduğu bir `CPaintDC` , Oluşturucusu zaten adlı sahiptir `BeginPaint`. İşlevleri çizim çağrıları, cihaz bağlam işaretçiyle yapılır. Cihaz bağlamları ve çizim çağrıları hakkında daha fazla bilgi için bkz. [CDC](../mfc/reference/cdc-class.md) içinde *MFC başvurusu* ve [pencere nesneleriyle çalışma](../mfc/working-with-window-objects.md).

Yazma konusunda daha fazla örnek için `OnDraw`, bkz: [MFC örnekleri](../visual-cpp-samples.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Görünümleri Kullanma](../mfc/using-views.md)

