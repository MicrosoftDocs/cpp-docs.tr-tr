---
title: "İleti eşlemeleri (ATL) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- message maps, ATL
- ATL, message handlers
ms.assetid: 9e100400-65c7-4a85-8857-4e6cb6dd7340
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1e708fea75c594c7bb9504515c80222ad901c335
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="message-maps-atl"></a>İleti eşlemeleri (ATL)
İleti eşlemesi işleyici işlevi belirli ileti, komut veya bildirim ile ilişkilendirir. ATL'ın kullanarak [ileti eşleme makroları](../atl/reference/message-map-macros-atl.md), bir pencere için ileti eşlemesi belirtebilirsiniz. Pencere yordamları `CWindowImpl`, `CDialogImpl`, ve `CContainedWindowT` kendi ileti eşlemesi pencerenin iletileri doğrudan.  
  
 [İleti işleyici işlevleri](../atl/message-handler-functions.md) türünde bir ek bağımsız değişken kabul `BOOL&`. Bu bağımsız değişken bir ileti işleme ve ayarlanmış olup olmadığını gösterir `TRUE` varsayılan olarak. Bir işleyici işlevi bağımsız değişken sonra ayarlamak `FALSE` , bir ileti işlenmemiş olduğunu belirtmek için. Bu durumda, ATL ileti eşlemesi içinde daha fazla işleyici işlevi aramaya devam eder. Bu bağımsız değişken ayarlayarak `FALSE`, önce bir iletisine yanıt olarak bazı eylemler gerçekleştirme ve varsayılan işleme veya ileti işleme tamamlamak için başka bir işleyici işlevi izin.  
  
## <a name="chained-message-maps"></a>Zincirleme ileti eşlemeleri  
 ATL zinciri ileti eşlemeleri için hangi ileti başka bir sınıf içinde tanımlanan ileti eşlemesi için işleme yönlendirir sağlar. Örneğin, tüm windows o sınıfın zincirleme için Tekdüzen davranışı sağlamak için ortak ileti ayrı bir sınıfta işleme uygulayabilirsiniz. Bir taban sınıf veya veri üyesi sınıfınız zincir.  
  
 ATL ayrıca dinamik zincirleme, başka bir nesnenin ileti eşlemesi zinciri için çalışma zamanında sağlayan destekler. Dinamik zincirleme uygulamak için sınıfından türetilen [CDynamicChain](../atl/reference/cdynamicchain-class.md). Ardından bildirme [CHAIN_MSG_MAP_DYNAMIC](reference/message-map-macros-atl.md#chain_msg_map_dynamic) makro ileti eşlemesi içinde. `CHAIN_MSG_MAP_DYNAMIC`Nesne ve zincirleme ileti eşlemesi tanımlayan benzersiz bir numara gerektirir. Bu çağrı aracılığıyla benzersiz bir değer tanımlamanız gerekir `CDynamicChain::SetChainEntry`.  
  
 Sınıfın türetildiği sağlanan bildiren bir ileti eşlemesi herhangi bir sınıf için zincir [CMessageMap](../atl/reference/cmessagemap-class.md). `CMessageMap`kendi ileti eşlemeleri diğer nesnelere kullanıma sunmak bir nesne sağlar. Unutmayın `CWindowImpl` zaten türeyen `CMessageMap`.  
  
## <a name="alternate-message-maps"></a>Diğer ileti eşlemeleri  
 Son olarak, diğer ileti eşlemeleri, ile bildirilen ATL destekleyen [ALT_MSG_MAP](reference/message-map-macros-atl.md#alt_msg_map) makrosu. Her alternatif ileti eşlemesi geçişi için benzersiz bir numara ile tanımlanan `ALT_MSG_MAP`. Alternatif bir iletiyi kullanarak eşler, bir harita birden çok windows iletilerini işleyebilir. Varsayılan olarak, unutmayın `CWindowImpl` alternatif ileti eşlemeleri kullanmaz. Bu destek eklemek için geçersiz kılma `WindowProc` yönteminde, `CWindowImpl`-türetilmiş sınıf ve arama `ProcessWindowMessage` ileti eşlemesi tanımlayıcısına sahip.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencere Uygulama](../atl/implementing-a-window.md)

