---
title: Idispeventsimpleımpl (ATL) kullanarak | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- IDispEventSimpleImpl
dev_langs:
- C++
helpviewer_keywords:
- IDispEventSimpleImpl class, using
ms.assetid: 8640ad1a-4bd0-40a5-b5e4-7322685d7aab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 00dadde438af1b4de820316dd4dc50e773827aca
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46107533"
---
# <a name="using-idispeventsimpleimpl"></a>Idispeventsimpleımpl kullanma

Kullanırken `IDispEventSimpleImpl` olayları işlemek için yapmanız gerekir:

- Öğesinden, bir sınıf türetin [Idispeventsimpleımpl](../atl/reference/idispeventsimpleimpl-class.md).

- Bir olay havuzu eşlemesi sınıfınıza ekleyin.

- Tanımlama [_atl_func_ınfo](../atl/reference/atl-func-info-structure.md) olayları tanımlayan yapılar.

- Olay havuzu kullanarak eşleme girişleri ekleyin [SINK_ENTRY_INFO](reference/composite-control-macros.md#sink_entry_info) makrosu.

- İşlemede ilginizi çeken yöntemleri uygulayın.

- Öneri ve olay kaynağı eşlemesindeki.

## <a name="example"></a>Örnek

Aşağıdaki örnekte nasıl işleneceğini gösterir `DocumentChange` olay harekete Word tarafından **uygulama** nesne. Bu olay üzerinde bir yöntemi olarak tanımlanan `ApplicationEvents` dispinterface.

Örnek dandır [ATLEventHandling örnek](../visual-cpp-samples.md).  

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

## <a name="see-also"></a>Ayrıca Bkz.

[Olay İşleme](../atl/event-handling-and-atl.md)<br/>
[ATLEventHandling örnek](../visual-cpp-samples.md)

