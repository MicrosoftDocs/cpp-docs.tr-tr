---
title: "Kalıcılığı ve başlatmayı iyileştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], optimizing
- performance, ActiveX controls
- optimization, ActiveX controls
- optimizing performance, ActiveX controls
ms.assetid: e821e19e-b9eb-49ab-b719-0743420ba80b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eeddfe4c67de2e96d42c7714619463ae3be45187
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="optimizing-persistence-and-initialization"></a>Kalıcılığı ve Başlatmayı İyileştirme
Varsayılan olarak, kalıcılığı ve başlatmayı denetiminde tarafından işlenen `DoPropExchange` üye işlevi. Tipik bir denetiminde birkaç çağrıları bu işlevi içeren **PX_** işlevleri (`PX_Color`, `PX_Font`, vb.), her bir özellik için bir tane.  
  
 Bu yaklaşımın avantajı vardır, tek bir `DoPropExchange` uygulama başlatma, ikili biçimde Kalıcılık ve bazı kapsayıcıları tarafından kullanılan sözde "özellik-paketi" biçiminde kalıcılığı için kullanılabilir. Bu bir işlev özellikleri ve varsayılan değerlerine uygun tek bir yerde ilgili tüm bilgileri sağlar.  
  
 Ancak, bu sayılanların genel verimliliği ödün verme pahasına olur. **PX_** işlevler kendiliğinden daha az çok katmanlı uygulamaları aracılığıyla kendi esnekliğinde daha doğrudan, ancak daha az esnek yaklaşımlar verimli alın. Ayrıca, bir denetim için varsayılan bir değer geçerse bir **PX_** işlev durumlarda varsayılan değeri mutlaka kullanılamaz olduğunda bile her zaman varsayılan değer sağlanmalıdır. Varsayılan değer oluşturma ölçeklendirebilmek kolay değildir görev (örneğin, bir ortam özelliğinden değeri alındığında) sonra ek ise, gereksiz iş varsayılan değeri yok olarak kullanıldığı durumlarda yapılır.  
  
 Denetiminizin geçersiz kılarak denetiminizin ikili Kalıcılık performansını iyileştirebilir `Serialize` işlevi. Bu üye işlevi varsayılan uygulaması için bir çağrı yapar, `DoPropExchange` işlevi. Bunu kılarak daha doğrudan uygulama ikili kalıcılığı için sağlayabilir. Örneğin, şunları göz önünde bulundurun `DoPropExchange` işlevi:  
  
 [!code-cpp[NVC_MFC_AxOpt#1](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_1.cpp)]  
  
 Bu denetimin ikili Kalıcılık performansını artırmak için kılabilirsiniz `Serialize` gibi işlev:  
  
 [!code-cpp[NVC_MFC_AxOpt#2](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_2.cpp)]  
  
 `dwVersion` Yerel değişken, denetimin kalıcı durumunu sürümü yüklü veya kaydedilmiş algılamak için kullanılabilir. Çağırmak yerine bu değişkeni kullanabilirsiniz [CPropExchange::GetVersion](../mfc/reference/cpropexchange-class.md#getversion).  
  
 Kalıcı biçimde küçük bir alanı kaydetmek için bir **BOOL** özelliği (ve tarafından üretilen biçim ile uyumlu tutmak için `PX_Bool`), özellik olarak depolayabilirsiniz bir **bayt**aşağıdaki gibi:  
  
 [!code-cpp[NVC_MFC_AxOpt#3](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_3.cpp)]  
  
 Atama yerine yük durumda, geçici bir değişken kullanılır ve ardından değeri atanır unutmayın `m_boolProp` için bir **bayt** başvuru. Atama tekniği yalnızca tek baytlık içinde oluşturacağı `m_boolProp` değiştirilen, bırakarak başlatılmadı kalan bayt sayısı.  
  
 Aynı denetimi için geçersiz kılarak denetimin başlatma iyileştirebilirsiniz [COleControl::OnResetState](../mfc/reference/colecontrol-class.md#onresetstate) gibi:  
  
 [!code-cpp[NVC_MFC_AxOpt#4](../mfc/codesnippet/cpp/optimizing-persistence-and-initialization_4.cpp)]  
  
 Ancak `Serialize` ve `OnResetState` geçersiz kılınmışsa, `DoPropExchange` işlevi saklanması sağlam özellik paketi biçiminde kalıcılığı için hala kullanıldığından. Üç bağımsız olarak hangi Kalıcılık düzeneğini kapsayıcı denetimi özelliklerini tutarlı olarak yönetir emin olmak için bu işlevlerin sağlamak önemlidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ActiveX Denetimleri: İyileştirme](../mfc/mfc-activex-controls-optimization.md)

