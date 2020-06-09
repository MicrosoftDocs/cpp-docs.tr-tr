---
title: Kalıcılığı ve Başlatmayı İyileştirme
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], optimizing
- performance, ActiveX controls
- optimization, ActiveX controls
- optimizing performance, ActiveX controls
ms.assetid: e821e19e-b9eb-49ab-b719-0743420ba80b
ms.openlocfilehash: 57b98f7e2e4f9e23175b8b01c2e37ff49c499949
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623992"
---
# <a name="optimizing-persistence-and-initialization"></a>Kalıcılığı ve Başlatmayı İyileştirme

Varsayılan olarak, bir denetimdeki Kalıcılık ve başlatma, üye işlevi tarafından işlenir `DoPropExchange` . Tipik denetimde, bu işlev **PX_** `PX_Color` `PX_Font` her bir özellik için bir tane olmak üzere birkaç px_ işleve (,, vb.) çağrı içerir.

Bu yaklaşım, tek bir `DoPropExchange` uygulamanın başlatma için kullanılabilmesi, ikili biçimde kalıcı hale getirme ve bu nedenle bazı kapsayıcılar tarafından kullanılan "özellik-paket" biçiminde Kalıcılık için kullanılması avantajına sahiptir. Bu bir işlev, özelliklerle ilgili tüm bilgileri ve bunların varsayılan değerlerini tek bir uygun yerde sağlar.

Ancak, bu asıl değer verimlilik masrafına gelir. **Px_** işlevleri, daha doğrudan daha az esneklik, ancak daha az esnek, yaklaşımdan çok katmanlı uygulamalar aracılığıyla esneklik elde edilir. Ayrıca, bir denetim **px_** işlevine varsayılan bir değer geçirirse, varsayılan değer kullanılması gerekli olmasa bile bu varsayılan değer her seferinde sağlanmalıdır. Varsayılan değerin oluşturulması önemsiz olmayan bir görevdir (örneğin, değer bir ortam özelliğinden elde edildiğinde), daha sonra varsayılan değerin kullanıldığı durumlarda fazladan, gereksiz iş yapılır.

Denetiminizin işlevini geçersiz kılarak denetiminizin ikili Kalıcılık performansını geliştirebilirsiniz `Serialize` . Bu üye işlevinin varsayılan uygulanması, işleviniz için bir çağrı yapar `DoPropExchange` . Geçersiz kılarak, ikili Kalıcılık için daha doğrudan bir uygulama sağlayabilirsiniz. Örneğin, bu işlevi göz önünde bulundurun `DoPropExchange` :

[!code-cpp[NVC_MFC_AxOpt#1](codesnippet/cpp/optimizing-persistence-and-initialization_1.cpp)]

Bu denetimin ikili kalıcılığının performansını artırmak için, `Serialize` işlevi şu şekilde geçersiz kılabilirsiniz:

[!code-cpp[NVC_MFC_AxOpt#2](codesnippet/cpp/optimizing-persistence-and-initialization_2.cpp)]

`dwVersion`Yerel değişken, denetimin kalıcı durumunun yüklenmekte veya kaydedilmekte olduğunu algılamak için kullanılabilir. [CPropExchange:: GetVersion](reference/cpropexchange-class.md#getversion)çağırmak yerine bu değişkeni kullanabilirsiniz.

Bir **bool** özelliği için kalıcı biçimde küçük bir boşluk kaydetmek için (ve tarafından üretilen biçimde uyumlu tutmak için `PX_Bool` ), özelliği aşağıdaki gibi bir **bayt**olarak saklayabilirsiniz:

[!code-cpp[NVC_MFC_AxOpt#3](codesnippet/cpp/optimizing-persistence-and-initialization_3.cpp)]

Yük durumunda, geçici bir değişken kullanıldığını ve bu değerin bir **bayt** başvurusuna *m_boolProp* atamak yerine değerinin atandığını unutmayın. Atama tekniği yalnızca bir bayt *m_boolProp* değiştirilmekte ve kalan baytlar başlatılmamış olarak bırakılır.

Aynı denetim için, aşağıdaki gibi [Copacontrol:: OnResetState](reference/colecontrol-class.md#onresetstate) öğesini geçersiz kılarak denetimin başlatılmasını en iyi duruma getirebilirsiniz:

[!code-cpp[NVC_MFC_AxOpt#4](codesnippet/cpp/optimizing-persistence-and-initialization_4.cpp)]

`Serialize`, Ancak `OnResetState` geçersiz kılınmışsa, `DoPropExchange` özelliği özellik paketi biçiminde kalıcı olarak kullanıldığı için işlev bozulmadan tutulmalıdır. Kapsayıcının kullandığı Kalıcılık mekanizmasından bağımsız olarak denetimin özelliklerini tutarlı bir şekilde yönettiğinden emin olmak için bu işlevlerin üçünü de korumak önemlidir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Denetimleri: İyileştirme](mfc-activex-controls-optimization.md)
