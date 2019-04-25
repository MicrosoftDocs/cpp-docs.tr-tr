---
title: ATL nesnesini oluşturulamaz yapma
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.ATL.objects
helpviewer_keywords:
- noncreatable ATL objects
- ATL projects, noncreatable objects
ms.assetid: 80d0bca2-dea0-4801-9a85-6243124437f6
ms.openlocfilehash: 966c7c1e42cd707726a8ca65bb80914c29ad582e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62200152"
---
# <a name="making-an-atl-object-noncreatable"></a>ATL nesnesini oluşturulamaz yapma

Bir istemci doğrudan nesne oluşturulamıyor bir ATL tabanlı COM nesnesi özniteliklerini değiştirebilirsiniz. Bu durumda, nesne başka bir nesne üzerinde bir yöntem çağrısının döndürülen yerine doğrudan oluşturulur.

## <a name="to-make-an-object-noncreatable"></a>Nesnesini oluşturulamaz yapma

1. Kaldırma [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) nesne. Noncreatable ancak kaydedilecek denetim nesnesi istiyorsanız, OBJECT_ENTRY_AUTO ile değiştirin [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](object-map-macros.md#object_entry_non_createable_ex_auto).

1. Ekleme [noncreatable](../../windows/noncreatable.md) .IDL dosyasındaki coclass özniteliği. Örneğin:

    ```
    [uuid(A1992E3D-3CF0-11D0-826F-00A0C90F2851),
    helpstring("MyObject"),
    noncreatable]
    coclass MyObject
    {
        [default] interface IMyInterface;
    }
    ```

## <a name="see-also"></a>Ayrıca bkz.

[ATL Projesi Sihirbazı](../../atl/reference/atl-project-wizard.md)<br/>
[Visual C++ Proje Türleri](../../build/reference/visual-cpp-project-types.md)<br/>
[ATL ve C Çalışma Zamanı Koduyla Programlama](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[ATL COM Nesnelerinin Temelleri](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[Varsayılan ATL Projesi Yapılandırmaları](../../atl/reference/default-atl-project-configurations.md)
