---
title: ATL Nesnesini Oluşturulamaz Yapma
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.ATL.objects
helpviewer_keywords:
- noncreatable ATL objects
- ATL projects, noncreatable objects
ms.assetid: 80d0bca2-dea0-4801-9a85-6243124437f6
ms.openlocfilehash: b2d0a21ec9e68f76650f0f6cb78446bd93540fa2
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91506950"
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
[ATL ve C çalışma zamanı koduyla programlama](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[ATL COM nesnelerinin temelleri](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[Varsayılan ATL Proje yapılandırması](../../atl/reference/default-atl-project-configurations.md)
