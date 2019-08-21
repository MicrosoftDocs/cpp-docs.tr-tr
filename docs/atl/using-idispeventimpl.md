---
title: IDispEventImpl (ATL) kullanma
ms.date: 08/19/2019
helpviewer_keywords:
- IDispEventImpl class, using
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
ms.openlocfilehash: 9684781ba99d96e2c58d450ee0ff892374e33aef
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630593"
---
# <a name="using-idispeventimpl"></a>IDispEventImpl kullanma

Olayları işlemek `IDispEventImpl` için kullanırken şunları yapmanız gerekir:

- Sınıfınızı [IDispEventImpl](../atl/reference/idispeventimpl-class.md)konumundan türet.

- Sınıfınıza bir olay havuzu eşlemesi ekleyin.

- [SINK_ENTRY](reference/composite-control-macros.md#sink_entry) veya [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex) makrosunu kullanarak olay havuzu eşlemesine girdi ekleyin.

- İşleme ilgilendiğiniz yöntemleri uygulayın.

- Olay kaynağını öner ve geri al.

## <a name="example"></a>Örnek

Aşağıdaki örnekte, Word 'ün **uygulama** nesnesi tarafından `DocumentChange` tetiklenen olayın nasıl işleneceği gösterilmektedir. Bu olay, `ApplicationEvents` dispınterface üzerinde bir yöntem olarak tanımlanır.

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

Örnek, Word `#import` 'ün tür kitaplığından gerekli üst bilgi dosyalarını oluşturmak için kullanır. Bu örneği Word 'ün diğer sürümleriyle birlikte kullanmak istiyorsanız, doğru mso dll dosyasını belirtmeniz gerekir. Örneğin, Office 2000 Mso9. dll ve OfficeXP, Mso. dll dosyasını sağlar. Bu kod, *pch. h* 'Den (Visual Studio 2017 ve önceki sürümlerde*stdadfx. h* ) basitleştirilmiştir:

[!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventimpl_1.h)]

Aşağıdaki kod NotSoSimple. h içinde görüntülenir. İlgili kod açıklamalara göre belirtilmiştir:

[!code-cpp[NVC_ATL_EventHandlingSample#2](../atl/codesnippet/cpp/using-idispeventimpl_2.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Olay İşleme](../atl/event-handling-and-atl.md)<br/>
[ATLEventHandling örneği](../overview/visual-cpp-samples.md)
