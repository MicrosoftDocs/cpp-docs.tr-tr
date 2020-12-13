---
description: 'Hakkında daha fazla bilgi edinin: IDispEventSimpleImpl kullanma'
title: IDispEventSimpleImpl (ATL) kullanma
ms.date: 08/19/2019
helpviewer_keywords:
- IDispEventSimpleImpl class, using
ms.assetid: 8640ad1a-4bd0-40a5-b5e4-7322685d7aab
ms.openlocfilehash: c0b3f6a0ecdcaae084d3f5d62c19745ee15ac6e9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138170"
---
# <a name="using-idispeventsimpleimpl"></a>IDispEventSimpleImpl kullanma

`IDispEventSimpleImpl`Olayları işlemek için kullanırken şunları yapmanız gerekir:

- [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)'den sınıfınızı türetirsiniz.

- Sınıfınıza bir olay havuzu eşlemesi ekleyin.

- Olayları açıklayan [_ATL_FUNC_INFO](../atl/reference/atl-func-info-structure.md) yapılarını tanımlayın.

- [SINK_ENTRY_INFO](reference/composite-control-macros.md#sink_entry_info) makrosunu kullanarak olay havuzu eşlemesine girdi ekleyin.

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

[!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventsimpleimpl_1.h)]

Yalnızca bu örnekte kullanılan tür kitaplığından alınan bilgiler, Word nesnesinin CLSID 'SI `Application` ve ARABIRIMIN IID 'si olur `ApplicationEvents` . Bu bilgiler yalnızca derleme zamanında kullanılır.

Aşağıdaki kod Simple. h içinde görüntülenir. İlgili kod açıklamalara göre belirtilmiştir:

[!code-cpp[NVC_ATL_EventHandlingSample#3](../atl/codesnippet/cpp/using-idispeventsimpleimpl_2.h)]

Aşağıdaki kod basit. cpp öğesinden yapılır:

[!code-cpp[NVC_ATL_EventHandlingSample#4](../atl/codesnippet/cpp/using-idispeventsimpleimpl_3.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Olay Işleme](../atl/event-handling-and-atl.md)<br/>
[ATLEventHandling örneği](../overview/visual-cpp-samples.md)
