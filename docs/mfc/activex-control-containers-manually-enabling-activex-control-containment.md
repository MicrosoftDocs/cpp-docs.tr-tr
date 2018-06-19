---
title: 'ActiveX denetim kapsayıcıları: ActiveX denetimi kapsamasını el ile etkinleştirme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- AfxEnableControlContainer method [MFC]
- ActiveX control containers [MFC], enabling
- ActiveX controls [MFC], enabling containers
ms.assetid: 833bcde9-c9ad-4709-ad12-2fc2150fb6a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fde0ee4dc740826c9efdf7b86cd2f021699f8820
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33339897"
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

