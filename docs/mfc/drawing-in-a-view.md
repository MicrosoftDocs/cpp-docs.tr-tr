---
title: Bir Görünümde Çizim Yapma
ms.date: 11/04/2016
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
ms.openlocfilehash: 227c4614bad42706893301c69882c3f40af12e2f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214350"
---
# <a name="drawing-in-a-view"></a>Bir Görünümde Çizim Yapma

Uygulamanızdaki neredeyse tüm çizimler görünümün `OnDraw` üye işlevinde meydana gelir ve bu, görünüm sınıfınıza geçersiz kılmanız gerekir. (Özel durum, [bir görünüm aracılığıyla Kullanıcı girişini yorumlama](../mfc/interpreting-user-input-through-a-view.md)bölümünde ele alınan fare çizimi olur.) `OnDraw` geçersiz kıl:

1. Sağladığınız belge üye işlevlerini çağırarak verileri alır.

1. Çerçevenin `OnDraw`aktardığı bir cihaz bağlamı nesnesinin üye işlevlerini çağırarak verileri görüntüler.

Belgenin verileri bir şekilde değiştiğinde, görünümün değişiklikleri yansıtacak şekilde yeniden çizilmelidir. Genellikle, bu durum Kullanıcı belgedeki bir görünümden değişiklik yaptığında meydana gelir. Bu durumda, Görünüm belgenin [UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews) üye işlevini çağırarak aynı belgedeki tüm görünümlere onları güncelleştirebilir. `UpdateAllViews` her bir görünümün [OnUpdate](../mfc/reference/cview-class.md#onupdate) üye işlevini çağırır. `OnUpdate` varsayılan uygulama, görünümün tüm istemci alanını geçersiz kılar. Yalnızca belgenin değiştirilen bölümlerine eşlenen istemci alanının bölgelerini geçersiz kılmak için bunu geçersiz kılabilirsiniz.

Sınıf `CDocument` `UpdateAllViews` üye işlevi ve `CView` `OnUpdate` üye işlevi, belgenin hangi bölümlerinin değiştirildiğini açıklayan bilgileri geçirmenize olanak sağlar. Bu "ipucu" mekanizması, görünümün yeniden çizilemesinin gereken alanı sınırlamanıza olanak tanır. `OnUpdate` iki "ipucu" bağımsız değişkeni alır. **LParam**türünde birinci, *lipucu*, istediğiniz herhangi bir veriyi geçirmenize olanak sağlar, ancak `CObject`* türünde, ikinci, *pHint*, `CObject`türetilmiş herhangi bir nesneye bir işaretçi geçirmenize olanak sağlar.

Bir görünüm geçersiz olduğunda, Windows bunu bir **WM_PAINT** mesajı gönderir. Görünümün [OnPaint](../mfc/reference/cwnd-class.md#onpaint) Handler Işlevi, [CPaintDC](../mfc/reference/cpaintdc-class.md) sınıfının bir cihaz bağlamı nesnesi oluşturarak ve görünüminizin `OnDraw` üye işlevini çağırarak iletiye yanıt verir. Normalde bir geçersiz kılma `OnPaint` işleyici işlevi yazmanız gerekmez.

[Cihaz bağlamı](../mfc/device-contexts.md) , bir cihazın görüntü veya yazıcı gibi çizim öznitelikleri hakkında bilgi Içeren bir Windows veri yapısıdır. Tüm çizim çağrıları bir cihaz bağlamı nesnesi aracılığıyla yapılır. Ekranda çizim için `OnDraw` `CPaintDC` bir nesne geçirilir. Bir yazıcıda çizim için, geçerli yazıcı için ayarlanmış bir [CDC](../mfc/reference/cdc-class.md) nesnesi geçirilir.

Görünümde çizim için kodunuz önce belgeye bir işaretçi alır, sonra da cihaz bağlamı aracılığıyla çizim çağrısı yapar. Aşağıdaki basit `OnDraw` örneği süreci göstermektedir:

[!code-cpp[NVC_MFCDocView#1](../mfc/codesnippet/cpp/drawing-in-a-view_1.cpp)]

Bu örnekte, `GetData` işlevini türetilen belge sınıfınızın bir üyesi olarak tanımlayacaksınız.

Örnek, görünümde ortalanan ve belgeden aldığı dizeyi yazdırır. `OnDraw` çağrısı ekran çizimi için ise, *PDC* 'de geçirilen `CDC` nesnesi, oluşturucu zaten `BeginPaint`olarak çağrılmış olan bir `CPaintDC`. Çizim işlevlerine yapılan çağrılar, cihaz bağlamı işaretçisi aracılığıyla yapılır. Cihaz bağlamları ve çizim çağrıları hakkında daha fazla bilgi için bkz. *MFC başvurusunda* [CDC](../mfc/reference/cdc-class.md) sınıfı ve [pencere nesneleriyle çalışma](../mfc/working-with-window-objects.md).

`OnDraw`yazma hakkında daha fazla örnek için bkz. [MFC örnekleri](../overview/visual-cpp-samples.md#mfc-samples).

## <a name="see-also"></a>Ayrıca bkz.

[Görünümleri Kullanma](../mfc/using-views.md)
