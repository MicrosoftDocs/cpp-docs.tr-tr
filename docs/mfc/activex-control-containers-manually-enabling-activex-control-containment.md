---
title: "ActiveX denetim kapsayıcıları: ActiveX denetimi kapsamasını el ile etkinleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- AfxEnableControlContainer method [MFC]
- ActiveX control containers [MFC], enabling
- ActiveX controls [MFC], enabling containers
ms.assetid: 833bcde9-c9ad-4709-ad12-2fc2150fb6a5
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bf1ba1273a349f685b70fec6706b566c2b618f23
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="activex-control-containers-manually-enabling-activex-control-containment"></a>ActiveX Denetimi Kapsayıcıları: ActiveX Denetimi Kapsamasını El İle Etkinleştirme
Uygulamanızı oluşturmak için MFC Uygulama Sihirbazı kullanıldığında ActiveX denetimi desteği etkinleştirmediyseniz Bu destek el ile eklemeniz gerekir. Bu makalede, varolan bir OLE kapsayıcı uygulamaya ActiveX denetimi kapsamasını el ile ekleme işlemi açıklanmaktadır. OLE kapsayıcı içinde ActiveX denetimi desteği istediğinizi önceden biliyorsanız makalesine bakın [bir MFC ActiveX denetimi kapsayıcısı oluşturma](../mfc/reference/creating-an-mfc-activex-control-container.md).  
  
> [!NOTE]
>  Bu makalede, kapsayıcı ve yordamları ve kod örnekleri olarak Dai adlı bir katıştırılmış denetimi adlı iletişim tabanlı ActiveX denetimi kapsayıcısı projesi kullanır.  
  
 ActiveX denetimlerini destekleyecek şekilde bir kod satırı iki projenizin dosyaları eklemeniz gerekir.  
  
-   Ana iletişim değiştirme `InitInstance` işlevi (KAPSAYICISINDA bulunur. CPP) için arama yapmak MFC Uygulama Sihirbazı tarafından [AfxEnableControlContainer](reference/ole-initialization.md#afxenablecontrolcontainer), aşağıdaki örnekte olduğu gibi:  
  
     [!code-cpp[NVC_MFCOleContainer#34](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_1.cpp)]  
    [!code-cpp[NVC_MFCOleContainer#35](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_2.cpp)]  
  
-   Aşağıdaki projenizin STDAFX ekleyin. H üstbilgi dosyası:  
  
     [!code-cpp[NVC_MFCOleContainer#36](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_3.h)]  
  
 Bu adımları tamamladıktan sonra tıklayarak projenizi yeniden derleyin **yapı** üzerinde **yapı** menüsü.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ActiveX Denetim Kapsayıcıları](../mfc/activex-control-containers.md)

