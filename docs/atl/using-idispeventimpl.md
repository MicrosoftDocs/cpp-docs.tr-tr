---
title: Idispeventımpl (ATL) kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- IDispEventImpl class, using
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
ms.openlocfilehash: c532164788d359c7834759de01407d49c19463ca
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64341477"
---
# <a name="using-idispeventimpl"></a>Using IDispEventImpl

Kullanırken `IDispEventImpl` olayları işlemek için yapmanız gerekir:

- Öğesinden, bir sınıf türetin [Idispeventımpl](../atl/reference/idispeventimpl-class.md).

- Bir olay havuzu eşlemesi sınıfınıza ekleyin.

- Olay havuzu kullanarak eşleme girişleri ekleyin [SINK_ENTRY](reference/composite-control-macros.md#sink_entry) veya [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex) makrosu.

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

[!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventimpl_1.h)]

Aşağıdaki kod NotSoSimple.h içinde görünür. İlgili kod açıklamaları tarafından belirtilir:

[!code-cpp[NVC_ATL_EventHandlingSample#2](../atl/codesnippet/cpp/using-idispeventimpl_2.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Olay İşleme](../atl/event-handling-and-atl.md)<br/>
[ATLEventHandling örnek](../overview/visual-cpp-samples.md)
