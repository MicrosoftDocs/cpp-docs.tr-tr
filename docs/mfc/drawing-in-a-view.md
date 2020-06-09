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
ms.openlocfilehash: c60d99fdebcd64ad844bc19918a30beb90b86af3
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618930"
---
# <a name="drawing-in-a-view"></a>Bir Görünümde Çizim Yapma

Uygulamanızdaki neredeyse tüm çizimler görünümün `OnDraw` üye işlevinde oluşur ve bu, görünüm sınıfınıza geçersiz kılmanız gerekir. (Özel durum, [bir görünüm aracılığıyla Kullanıcı girişini yorumlama](interpreting-user-input-through-a-view.md)bölümünde ele alınan fare çizimi olur.) `OnDraw`Geçersiz kılma:

1. Sağladığınız belge üye işlevlerini çağırarak verileri alır.

1. Framework 'ün geçirdiği bir cihaz bağlamı nesnesinin üye işlevlerini çağırarak verileri görüntüler `OnDraw` .

Belgenin verileri bir şekilde değiştiğinde, görünümün değişiklikleri yansıtacak şekilde yeniden çizilmelidir. Genellikle, bu durum Kullanıcı belgedeki bir görünümden değişiklik yaptığında meydana gelir. Bu durumda, Görünüm belgenin [UpdateAllViews](reference/cdocument-class.md#updateallviews) üye işlevini çağırarak aynı belgedeki tüm görünümlere onları güncelleştirebilir. `UpdateAllViews`Her bir görünümün [OnUpdate](reference/cview-class.md#onupdate) üye işlevini çağırır. Varsayılan uygulama, `OnUpdate` görünümün tüm istemci alanını geçersiz kılar. Yalnızca belgenin değiştirilen bölümlerine eşlenen istemci alanının bölgelerini geçersiz kılmak için bunu geçersiz kılabilirsiniz.

Sınıfının `UpdateAllViews` üye işlevi `CDocument` ve `OnUpdate` sınıfının üye işlevi, `CView` belgenin hangi bölümlerinin değiştirildiğini açıklayan bilgileri geçirmenize olanak sağlar. Bu "ipucu" mekanizması, görünümün yeniden çizilemesinin gereken alanı sınırlamanıza olanak tanır. `OnUpdate`iki "ipucu" bağımsız değişkeni alır. **LParam**türünde birinci, *lipucu*, istediğiniz herhangi bir veriyi geçirmenize olanak tanılarken, * türünde, ikinci, *pHint*, `CObject` öğesinden türetilmiş herhangi bir nesneye bir işaretçi geçirmenize olanak sağlar `CObject` .

Bir görünüm geçersiz olduğunda, Windows bunu bir **WM_PAINT** mesajı gönderir. Görünümün [OnPaint](reference/cwnd-class.md#onpaint) Handler Işlevi, [CPaintDC](reference/cpaintdc-class.md) sınıfının bir cihaz bağlamı nesnesi oluşturarak ve görünüminizin üye işlevini çağırarak iletiye yanıt verir `OnDraw` . Normalde bir geçersiz kılma `OnPaint` işleyici işlevi yazmanız gerekmez.

[Cihaz bağlamı](device-contexts.md) , bir cihazın görüntü veya yazıcı gibi çizim öznitelikleri hakkında bilgi Içeren bir Windows veri yapısıdır. Tüm çizim çağrıları bir cihaz bağlamı nesnesi aracılığıyla yapılır. Ekranda çizim için `OnDraw` bir `CPaintDC` nesnesi geçti. Bir yazıcıda çizim için, geçerli yazıcı için ayarlanmış bir [CDC](reference/cdc-class.md) nesnesi geçirilir.

Görünümde çizim için kodunuz önce belgeye bir işaretçi alır, sonra da cihaz bağlamı aracılığıyla çizim çağrısı yapar. Aşağıdaki basit `OnDraw` örnekte işlem gösterilmektedir:

[!code-cpp[NVC_MFCDocView#1](codesnippet/cpp/drawing-in-a-view_1.cpp)]

Bu örnekte, `GetData` işlevi türetilmiş belge sınıfınızın bir üyesi olarak tanımlayacaksınız.

Örnek, görünümde ortalanan ve belgeden aldığı dizeyi yazdırır. `OnDraw`Çağrı ekran çizimi için ise, `CDC` *PDC* içinde geçirilen nesne, `CPaintDC` Oluşturucu zaten çağrılmış olan bir nesnedir `BeginPaint` . Çizim işlevlerine yapılan çağrılar, cihaz bağlamı işaretçisi aracılığıyla yapılır. Cihaz bağlamları ve çizim çağrıları hakkında daha fazla bilgi için bkz. *MFC başvurusunda* [CDC](reference/cdc-class.md) sınıfı ve [pencere nesneleriyle çalışma](working-with-window-objects.md).

Yazma hakkında daha fazla örnek için `OnDraw` bkz. [MFC örnekleri](../overview/visual-cpp-samples.md#mfc-samples).

## <a name="see-also"></a>Ayrıca bkz.

[Görünümleri Kullanma](using-views.md)
