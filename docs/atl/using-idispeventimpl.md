---
description: 'Hakkında daha fazla bilgi edinin: IDispEventImpl kullanma'
title: IDispEventImpl (ATL) kullanma
ms.date: 08/19/2019
helpviewer_keywords:
- IDispEventImpl class, using
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
ms.openlocfilehash: 4ddab52eeac3c409b32393e8b8b07a85019143c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157184"
---
# <a name="using-idispeventimpl"></a>IDispEventImpl kullanma

`IDispEventImpl`Olayları işlemek için kullanırken şunları yapmanız gerekir:

- Sınıfınızı [IDispEventImpl](../atl/reference/idispeventimpl-class.md)konumundan türet.

- Sınıfınıza bir olay havuzu eşlemesi ekleyin.

- [SINK_ENTRY](reference/composite-control-macros.md#sink_entry) veya [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex) makrosunu kullanarak olay havuzu eşlemesine girdi ekleyin.

- İşleme ilgilendiğiniz yöntemleri uygulayın.

- Olay kaynağını öner ve geri al.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, `DocumentChange` Word 'Ün **uygulama** nesnesi tarafından tetiklenen olayın nasıl işleneceği gösterilmektedir. Bu olay, dispınterface üzerinde bir yöntem olarak tanımlanır `ApplicationEvents` .

Örnek, [ATLEventHandling](../overview/visual-cpp-samples.md)örneğinden yapılır.

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

Örnek, `#import` Word 'ün tür kitaplığından gerekli üst bilgi dosyalarını oluşturmak için kullanır. Bu örneği Word 'ün diğer sürümleriyle birlikte kullanmak istiyorsanız, doğru mso dll dosyasını belirtmeniz gerekir. Örneğin, Office 2000 mso9.dll sağlar ve OfficeXP mso.dll sağlar. Bu kod, *pch. h* 'Den (Visual Studio 2017 ve önceki sürümlerde *stdadfx. h* ) basitleştirilmiştir:

[!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventimpl_1.h)]

Aşağıdaki kod NotSoSimple. h içinde görüntülenir. İlgili kod açıklamalara göre belirtilmiştir:

[!code-cpp[NVC_ATL_EventHandlingSample#2](../atl/codesnippet/cpp/using-idispeventimpl_2.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Olay Işleme](../atl/event-handling-and-atl.md)<br/>
[ATLEventHandling örneği](../overview/visual-cpp-samples.md)
