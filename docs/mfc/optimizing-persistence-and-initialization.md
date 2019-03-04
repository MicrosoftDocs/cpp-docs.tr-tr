---
title: Kalıcılığı ve Başlatmayı İyileştirme
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], optimizing
- performance, ActiveX controls
- optimization, ActiveX controls
- optimizing performance, ActiveX controls
ms.assetid: e821e19e-b9eb-49ab-b719-0743420ba80b
ms.openlocfilehash: 294d9c43f5f767329c04932c574485d7dca704e9
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57261955"
---
# <a name="optimizing-persistence-and-initialization"></a>Kalıcılığı ve Başlatmayı İyileştirme

Varsayılan olarak, tarafından işlenen kalıcılığı ve başlatmayı denetiminde `DoPropExchange` üye işlevi. Tipik bir denetiminde bu işlevi birçok çağrıları içeren **PX_** işlevleri (`PX_Color`, `PX_Font`, vb.), her bir özellik için bir tane.

Bu yaklaşımın avantajı vardır, tek bir `DoPropExchange` uygulama başlatma, kalıcı ikili biçimde ve bazı kapsayıcıları tarafından kullanılan tüm "özellik-paketi" biçiminde kalıcılığı için kullanılabilir. Bu bir işlev özellikleri ve varsayılan değerleri tek bir kullanışlı yerde ilgili tüm bilgileri sağlar.

Ancak, bu genellik düzeyine erişir çoğaltamaz verimliliği gelir. **PX_** işlevleri kendi esnekliğinde doğal olarak daha az olan çok katmanlı uygulamaları aracılığıyla daha doğrudan, ancak daha az esnek bir yaklaşım verimli alın. Ayrıca, bir denetim için varsayılan bir değer geçerse bir **PX_** işlev durumlarda varsayılan değer mutlaka kullanılamaz olduğunda bile her zaman varsayılan değer belirtilmelidir. Varsayılan değer oluşturma ölçeklenebilmesi kolay görev (örneğin, bir ortam özelliği değeri alındığında) sonra ek ise, gereksiz iş varsayılan değeri yok olarak kullanıldığı durumlarda yapılır.

Denetiminizin geçersiz kılarak denetiminizin ikili Kalıcılık performansını iyileştirebilir `Serialize` işlevi. Bu üye işlevini varsayılan uygulamasını çağrıda, `DoPropExchange` işlevi. Bunu kılarak, ikili Kalıcılık için daha doğrudan bir uygulama sağlayabilirsiniz. Örneğin, şunları göz önünde bulundurun `DoPropExchange` işlevi:

[!code-cpp[NVC_MFC_AxOpt#1](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_1.cpp)]

Bu denetimin ikili Kalıcılık performansını artırmak için kılabilirsiniz `Serialize` gibi işlev:

[!code-cpp[NVC_MFC_AxOpt#2](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_2.cpp)]

`dwVersion` Yerel değişken, denetimin kalıcı durumunu sürümü yüklü veya kaydedilmiş algılamak için kullanılabilir. Çağırmak yerine bu değişkeni kullanabilirsiniz [CPropExchange::GetVersion](../mfc/reference/cpropexchange-class.md#getversion).

Küçük bir alan için kalıcı biçiminde kaydetmek için bir **BOOL** özelliği (tarafından üretilen biçim ile uyumlu kalmasını sağlamak için `PX_Bool`), özellik olarak depolayabilir bir **bayt**gibi:

[!code-cpp[NVC_MFC_AxOpt#3](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_3.cpp)]

Atama yerine yük durumda, geçici bir değişkene kullanılır ve ardından değeri atanır unutmayın *m_boolProp* için bir **bayt** başvuru. Atama yöntemi yalnızca bir bayt neden *m_boolProp* değiştirilmesini, başlatılmamış kalan bayt çıkılıyor.

Aynı denetim için geçersiz kılarak denetimin başlatma iyileştirebilirsiniz [COleControl::OnResetState](../mfc/reference/colecontrol-class.md#onresetstate) gibi:

[!code-cpp[NVC_MFC_AxOpt#4](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_4.cpp)]

Ancak `Serialize` ve `OnResetState` geçersiz kılınmış, `DoPropExchange` işlevi saklanır sağlam özellik paketi biçiminde kalıcılığı için hala kullanıldığından. Üç bağımsız olarak hangi Kalıcılık düzeneğini kapsayıcı denetimin özelliklerini tutarlı olarak yöneten emin olmak için bu işlevler sağlamak önemlidir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri: En iyi duruma getirme](../mfc/mfc-activex-controls-optimization.md)
