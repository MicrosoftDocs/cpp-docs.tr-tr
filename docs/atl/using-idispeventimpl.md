---
title: Idispeventımpl (ATL) kullanarak | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- IDispEventImpl
dev_langs:
- C++
helpviewer_keywords:
- IDispEventImpl class, using
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 48afac392d02edfd3d312583642367bc6726e536
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106798"
---
# <a name="using-idispeventimpl"></a>Idispeventımpl kullanma

Kullanırken `IDispEventImpl` olayları işlemek için yapmanız gerekir:

- Öğesinden, bir sınıf türetin [Idispeventımpl](../atl/reference/idispeventimpl-class.md).

- Bir olay havuzu eşlemesi sınıfınıza ekleyin.

- Olay havuzu kullanarak eşleme girişleri ekleyin [SINK_ENTRY](reference/composite-control-macros.md#sink_entry) veya [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex) makrosu.

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

[!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventimpl_1.h)]

Aşağıdaki kod NotSoSimple.h içinde görünür. İlgili kod açıklamaları tarafından belirtilir:

[!code-cpp[NVC_ATL_EventHandlingSample#2](../atl/codesnippet/cpp/using-idispeventimpl_2.h)]

## <a name="see-also"></a>Ayrıca Bkz.

[Olay İşleme](../atl/event-handling-and-atl.md)<br/>
[ATLEventHandling örnek](../visual-cpp-samples.md)

