---
title: ATL nesne Noncreatable yapma | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vc.appwiz.ATL.objects
dev_langs: C++
helpviewer_keywords:
- noncreatable ATL objects
- ATL projects, noncreatable objects
ms.assetid: 80d0bca2-dea0-4801-9a85-6243124437f6
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 38aa9f5fae45c9d5fa1e413763bd5fa2e65ab795
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="making-an-atl-object-noncreatable"></a>ATL nesne Noncreatable yapma
Bir istemci doğrudan nesneyi oluşturamıyor ATL tabanlı COM nesnesinin özniteliklerini değiştirebilirsiniz. Bu durumda, nesne başka bir nesne üzerinde bir yöntem çağrısı ile döndürülen yerine doğrudan oluşturulur.  
  
### <a name="to-make-an-object-noncreatable"></a>Bir nesne noncreatable yapma  
  
1.  Kaldırma [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) nesne. Noncreatable ancak kaydedilecek denetim nesnesi istiyorsanız, OBJECT_ENTRY_AUTO ile Değiştir [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](object-map-macros.md#object_entry_non_createable_ex_auto).  
  
2.  Ekleme [noncreatable](../../windows/noncreatable.md) .idl dosyasındaki coclass özniteliği. Örneğin:  
  
 ```  
 [  
    uuid(A1992E3D-3CF0-11D0-826F-00A0C90F2851), 
    helpstring("MyObject"), 
    noncreatable]  
    coclass MyObject  
 {  
 [default] interface IMyInterface;  
 }  
 ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL Proje Sihirbazı](../../atl/reference/atl-project-wizard.md)   
 [Visual C++ proje türleri](../../ide/visual-cpp-project-types.md)   
 [Uygulama sihirbazları kullanarak masaüstü projeleri oluşturma](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [ATL ve C çalışma zamanı koduyla programlama](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [ATL COM nesneleri temelleri](../../atl/fundamentals-of-atl-com-objects.md)   
 [Varsayılan ATL Proje yapılandırmaları](../../atl/reference/default-atl-project-configurations.md)

