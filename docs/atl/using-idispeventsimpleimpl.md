---
title: Using IDispEventSimpleImpl (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- IDispEventSimpleImpl class, using
ms.assetid: 8640ad1a-4bd0-40a5-b5e4-7322685d7aab
ms.openlocfilehash: 40edca3a99fb6e9d57d617e79d0bd37ebbfcd4ad
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58768570"
---
# <a name="using-idispeventsimpleimpl"></a>Using IDispEventSimpleImpl

Kullanırken `IDispEventSimpleImpl` olayları işlemek için yapmanız gerekir:

- Öğesinden, bir sınıf türetin [Idispeventsimpleımpl](../atl/reference/idispeventsimpleimpl-class.md).

- Bir olay havuzu eşlemesi sınıfınıza ekleyin.

- Tanımlama [_atl_func_ınfo](../atl/reference/atl-func-info-structure.md) olayları tanımlayan yapılar.

- Olay havuzu kullanarak eşleme girişleri ekleyin [SINK_ENTRY_INFO](reference/composite-control-macros.md#sink_entry_info) makrosu.

- İşlemede ilginizi çeken yöntemleri uygulayın.

- Öneri ve olay kaynağı eşlemesindeki.

## <a name="example"></a>Örnek

Aşağıdaki örnekte nasıl işleneceğini gösterir `DocumentChange` olay harekete Word tarafından **uygulama** nesne. Bu olay üzerinde bir yöntemi olarak tanımlanan `ApplicationEvents` dispinterface.

Örnek dandır [ATLEventHandling örnek](../overview/visual-cpp-samples.md).

```cpp
[ uuid(000209F7-0000-0000-C000-000000000046), hidden ]
dispinterface ApplicationEvents {
properties:
methods:
    [id(0x00000001), restricted, hidden]
    void Startup();

    [id(0x00000002)]
    void Quit();

    [id(0x00000003)]
    void DocumentChange();
};
```

Örnekte `#import` Word'ün tür kitaplığından gereken üst bilgi dosyaları oluşturmak için. Word'ün diğer sürümleri bu örneği kullanmak istiyorsanız, doğru mso dll dosyası belirtmeniz gerekir. Örneğin, Office 2000 mso9.dll ve OfficeXP mso.dll sağlar. Bu kod, stdafx.h basitleştirilir:

[!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventsimpleimpl_1.h)]

Yalnızca tür kitaplığındaki aslında bu örnekte kullanılan Word'ün CLSID bilgilerdir `Application` nesne ve Laboratuvardaki `ApplicationEvents` arabirimi. Bu bilgiler, yalnızca derleme zamanında kullanılır.

Aşağıdaki kod Simple.h içinde görünür. İlgili kod açıklamaları tarafından belirtilir:

[!code-cpp[NVC_ATL_EventHandlingSample#3](../atl/codesnippet/cpp/using-idispeventsimpleimpl_2.h)]

Aşağıdaki kod, Simple.cpp şöyledir:

[!code-cpp[NVC_ATL_EventHandlingSample#4](../atl/codesnippet/cpp/using-idispeventsimpleimpl_3.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Olay İşleme](../atl/event-handling-and-atl.md)<br/>
[ATLEventHandling örnek](../overview/visual-cpp-samples.md)
