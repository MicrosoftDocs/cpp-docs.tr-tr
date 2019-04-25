---
title: İleti eşlemeleri (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- message maps, ATL
- ATL, message handlers
ms.assetid: 9e100400-65c7-4a85-8857-4e6cb6dd7340
ms.openlocfilehash: 1b8b3fcb2f10f975ebdf68a285c7d5e364b9e1b4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62250138"
---
# <a name="message-maps-atl"></a>İleti eşlemeleri (ATL)

İleti eşlemesi işleyici işlevi, belirli bir ileti, komut veya bildirim ile ilişkilendirir. ATL kullanarak [ileti eşleme makroları](../atl/reference/message-map-macros-atl.md), bir pencere için ileti eşlemesi belirtebilirsiniz. Pencere yordamları `CWindowImpl`, `CDialogImpl`, ve `CContainedWindowT` kendi ileti eşlemesi bir pencere iletilerini yönlendirmek.

[İleti işleyici işlevlerini](../atl/message-handler-functions.md) ek bağımsız değişken türü kabul `BOOL&`. Bu bağımsız değişken, bir ileti işlendikten ve varsayılan olarak TRUE olarak ayarlanmış olup olmadığını gösterir. İşleyici işlevi, ardından bağımsız değişken, bir ileti işlenmemiş olduğunu göstermek için FALSE olarak ayarlayabilirsiniz. Bu durumda, ATL ileti Haritası'nda daha fazla işleyici işlevi aramaya devam eder. Bu bağımsız değişken FALSE olarak ayarlayarak, öncelikle bir iletiye yanıt olarak bazı eylemler gerçekleştirme ve varsayılan işlem veya başka bir işleyici işlevi iletiyi işlemeyi tamamladıktan sonra izin.

## <a name="chained-message-maps"></a>Zincirleme ileti eşlemeleri

ATL zinciri ileti eşlemeleri için bu ileti başka bir sınıf içinde tanımlanan ileti eşlemesi için işleme yönlendirir sağlar. Örneğin, tüm windows o sınıfın zincirleme Tekdüzen davranışı sağlamak için ortak ileti ayrı bir sınıf içinde uygulayabilirsiniz. Bir temel sınıf veya bir veri üyesinin sınıfınızın zincirleyebilirsiniz.

ATL ayrıca dinamik bağlama, başka bir nesnenin ileti eşlemesi zincirdeki çalışma zamanında sağlayan destekler. Dinamik zincirleme uygulamak için sizin sınıfınızdan türetilmelidir [CDynamicChain](../atl/reference/cdynamicchain-class.md). Ardından bildirmek [CHAIN_MSG_MAP_DYNAMIC](reference/message-map-macros-atl.md#chain_msg_map_dynamic) makro, ileti eşlemesi. Nesne ve zincirleme ileti eşlemesi tanımlayan benzersiz bir numara CHAIN_MSG_MAP_DYNAMIC gerektirir. Bu benzersiz değer yapılan bir çağrıyla tanımlamalıdır `CDynamicChain::SetChainEntry`.

Bu sınıfın türetildiği sağlanan bildiren bir ileti eşlemesi herhangi bir sınıf için zincirleyebilirsiniz [CMessageMap](../atl/reference/cmessagemap-class.md). `CMessageMap` diğer nesnelere kendi ileti eşlemeleri kullanıma sunmak bir nesne sağlar. Unutmayın `CWindowImpl` zaten türetildiği `CMessageMap`.

## <a name="alternate-message-maps"></a>Diğer ileti eşlemeleri

Son olarak, diğer ileti eşlemeleri ile bildirilen, ATL destekler [ALT_MSG_MAP](reference/message-map-macros-atl.md#alt_msg_map) makrosu. Her alternatif ileti eşlemesi için ALT_MSG_MAP geçirdiğiniz benzersiz bir numara tarafından tanımlanır. Alternatif bir iletiyi kullanarak eşler, bir eşlem içindeki birden çok windows iletileri işleyebilir. Varsayılan olarak, dikkat `CWindowImpl` diğer ileti eşlemeleri kullanmaz. Bu desteği eklemek için geçersiz kılma `WindowProc` yönteminde, `CWindowImpl`-türetilmiş sınıf ve çağrı `ProcessWindowMessage` ileti eşlemesi tanımlayıcısına sahip.

## <a name="see-also"></a>Ayrıca bkz.

[Pencere Uygulama](../atl/implementing-a-window.md)
