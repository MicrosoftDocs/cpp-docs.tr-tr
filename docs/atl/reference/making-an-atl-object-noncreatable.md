---
description: 'Daha fazla bilgi edinin: ATL nesnesi oluşturma'
title: ATL Nesnesini Oluşturulamaz Yapma
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.ATL.objects
helpviewer_keywords:
- noncreatable ATL objects
- ATL projects, noncreatable objects
ms.assetid: 80d0bca2-dea0-4801-9a85-6243124437f6
ms.openlocfilehash: 0a7a07081546722e5a960cb8bf0384a1d7e47f9b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139184"
---
# <a name="making-an-atl-object-noncreatable"></a>ATL Nesnesini Oluşturulamaz Yapma

Bir istemcinin nesneyi doğrudan oluşturabilmesi için ATL tabanlı bir COM nesnesinin özniteliklerini değiştirebilirsiniz. Bu durumda, nesnesi doğrudan oluşturulması yerine başka bir nesne üzerindeki bir yöntem çağrısıyla döndürülür.

## <a name="to-make-an-object-noncreatable"></a>Nesne dışı tablo oluşturmak için

1. Nesnenin [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) kaldırın. Nesnenin oluşturulamasa da, denetimin kaydedilmesini istiyorsanız, OBJECT_ENTRY_AUTO [object_entry_non_createable_ex_auto](object-map-macros.md#object_entry_non_createable_ex_auto)ile değiştirin.

1. . IDL dosyasındaki coclass öğesine [noncreatable](../../windows/attributes/noncreatable.md) özniteliğini ekleyin. Örneğin:

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

[ATL Proje Sihirbazı](../../atl/reference/atl-project-wizard.md)<br/>
[Visual Studio 'da C++ proje türleri](../../build/reference/visual-cpp-project-types.md)<br/>
[ATL ve C Run-Time kodla programlama](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[ATL COM nesnelerinin temelleri](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[Varsayılan ATL Proje yapılandırması](../../atl/reference/default-atl-project-configurations.md)
