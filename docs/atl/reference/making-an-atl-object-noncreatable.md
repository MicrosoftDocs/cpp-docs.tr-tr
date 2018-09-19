---
title: ATL nesnesini oluşturulamaz yapma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.objects
dev_langs:
- C++
helpviewer_keywords:
- noncreatable ATL objects
- ATL projects, noncreatable objects
ms.assetid: 80d0bca2-dea0-4801-9a85-6243124437f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cf2b3d047a6618326e69dcb51f143f77fc10c8a6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099544"
---
# <a name="making-an-atl-object-noncreatable"></a>ATL nesnesini oluşturulamaz yapma

Bir istemci doğrudan nesne oluşturulamıyor bir ATL tabanlı COM nesnesi özniteliklerini değiştirebilirsiniz. Bu durumda, nesne başka bir nesne üzerinde bir yöntem çağrısının döndürülen yerine doğrudan oluşturulur.

### <a name="to-make-an-object-noncreatable"></a>Nesnesini oluşturulamaz yapma

1. Kaldırma [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) nesne. Noncreatable ancak kaydedilecek denetim nesnesi istiyorsanız, OBJECT_ENTRY_AUTO ile değiştirin [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](object-map-macros.md#object_entry_non_createable_ex_auto).

2. Ekleme [noncreatable](../../windows/noncreatable.md) .IDL dosyasındaki coclass özniteliği. Örneğin:

    ```  
    [uuid(A1992E3D-3CF0-11D0-826F-00A0C90F2851), 
    helpstring("MyObject"), 
    noncreatable]  
    coclass MyObject  
    {  
        [default] interface IMyInterface;  
    }  
    ```

## <a name="see-also"></a>Ayrıca Bkz.

[ATL Projesi Sihirbazı](../../atl/reference/atl-project-wizard.md)<br/>
[Visual C++ Proje Türleri](../../ide/visual-cpp-project-types.md)<br/>
[Uygulama Sihirbazları Kullanarak Masaüstü Projeleri Oluşturma](../../ide/creating-desktop-projects-by-using-application-wizards.md)<br/>
[ATL ve C Çalışma Zamanı Koduyla Programlama](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[ATL COM Nesnelerinin Temelleri](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[Varsayılan ATL Projesi Yapılandırmaları](../../atl/reference/default-atl-project-configurations.md)

