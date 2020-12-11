---
description: 'Hakkında daha fazla bilgi edinin: Ileti haritaları (ATL)'
title: İleti haritaları (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- message maps, ATL
- ATL, message handlers
ms.assetid: 9e100400-65c7-4a85-8857-4e6cb6dd7340
ms.openlocfilehash: c5b3340abbfbc66ac710ab716e3daa38dd7cd6df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159524"
---
# <a name="message-maps-atl"></a>İleti haritaları (ATL)

İleti eşleme, bir işleyici işlevini belirli bir ileti, komut veya bildirimle ilişkilendirir. ATL 'nin [ileti eşleme makrolarını](../atl/reference/message-map-macros-atl.md)kullanarak, bir pencere için bir ileti haritası belirtebilirsiniz. , Ve içindeki pencere `CWindowImpl` yordamları `CDialogImpl` `CContainedWindowT` ileti eşlemesine bir pencerenin iletilerini doğrudan yönlendirir.

[İleti işleyici işlevleri](../atl/message-handler-functions.md) , türünde ek bir bağımsız değişken kabul eder `BOOL&` . Bu bağımsız değişken, bir iletinin işlenip işlenmediğini belirtir ve varsayılan olarak TRUE olarak ayarlanır. Bir işleyici işlevi daha sonra bir ileti işlenmemiş olduğunu göstermek için bağımsız değişkenini FALSE olarak ayarlayabilir. Bu durumda, ATL ileti eşlemesinde bir işleyici işlevini daha fazla aramaya devam eder. Bu bağımsız değişkeni FALSE olarak ayarlayarak, önce bir iletiye yanıt olarak bazı eylemler gerçekleştirebilir ve ardından varsayılan işleme ya da başka bir işleyici işlevinin iletiyi işlemeyi bitirmesini izin verebilirsiniz.

## <a name="chained-message-maps"></a>Zincirleme Ileti haritaları

ATL Ayrıca, ileti işlemeyi başka bir sınıfta tanımlanan bir ileti eşlemesine yönlendiren ileti eşlemelerini zincirlemenize de olanak tanır. Örneğin, bu sınıfa tüm Windows zincirleme için Tekdüzen davranışı sağlamak üzere ayrı bir sınıfta ortak ileti işleme uygulayabilirsiniz. Bir temel sınıfa veya sınıfınızın bir veri üyesine zincirleyebilirsiniz.

ATL Ayrıca, çalışma zamanında başka bir nesnenin ileti eşlemesine zincirlemenize olanak tanıyan dinamik zincirlemeyi de destekler. Dinamik zincirleme uygulamak için, sınıfı [cdynamiczincirinden](../atl/reference/cdynamicchain-class.md)türetmeniz gerekir. Ardından ileti Haritalarınızın [CHAIN_MSG_MAP_DYNAMIC](reference/message-map-macros-atl.md#chain_msg_map_dynamic) makrosunu bildirin. CHAIN_MSG_MAP_DYNAMIC, nesne ve zincirleme yaptığınız ileti haritasını tanımlayan benzersiz bir sayı gerektirir. Bu benzersiz değeri öğesine çağrısıyla tanımlamanız gerekir `CDynamicChain::SetChainEntry` .

Sınıfın [CMessageMap](../atl/reference/cmessagemap-class.md)öğesinden türediği bir ileti eşlemesi bildiren herhangi bir sınıfa zincirleyebilirsiniz. `CMessageMap` bir nesnenin ileti eşlemelerini diğer nesnelerle kullanıma almasına izin verir. `CWindowImpl`Zaten öğesinden türetildiğine unutmayın `CMessageMap` .

## <a name="alternate-message-maps"></a>Alternatif Ileti eşlemeleri

Son olarak, ATL [ALT_MSG_MAP](reference/message-map-macros-atl.md#alt_msg_map) makrolarıyla belirtilen alternatif ileti eşlemelerini destekler. Her alternatif ileti eşlemesi, ALT_MSG_MAP geçirdiğiniz benzersiz bir sayı ile tanımlanır. Alternatif ileti eşlemelerini kullanarak, bir haritada birden çok pencere iletilerini işleyebilirsiniz. Varsayılan olarak, `CWindowImpl` alternatif ileti haritaları kullanmaz. Bu desteği eklemek için, `WindowProc` `CWindowImpl` türetilmiş sınıfdaki yöntemi geçersiz kılın ve `ProcessWindowMessage` ileti haritası tanımlayıcısıyla çağırın.

## <a name="see-also"></a>Ayrıca bkz.

[Pencere uygulama](../atl/implementing-a-window.md)
