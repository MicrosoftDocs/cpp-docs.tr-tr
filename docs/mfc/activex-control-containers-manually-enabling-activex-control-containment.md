---
title: 'ActiveX denetim kapsayıcıları: ActiveX denetimi kapsamasını el ile etkinleştirme | Microsoft Docs'
ms.custom: ''
ms.date: 09/12/2018
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
ms.openlocfilehash: f684bbb287213ad0cbe6d490c1bef869f5ffc9db
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50077783"
---
# <a name="activex-control-containers-manually-enabling-activex-control-containment"></a>ActiveX Denetimi Kapsayıcıları: ActiveX Denetimi Kapsamasını El İle Etkinleştirme

Uygulamanızı oluşturmak için MFC Uygulama Sihirbazı kullanıldığında ActiveX denetimi desteği etkinleştirmediyseniz Bu destek el ile eklemeniz gerekir. Bu makalede el ile varolan bir OLE kapsayıcı uygulamaya ActiveX denetimi kapsamasını ekleme işlemi açıklanır. OLE kapsayıcınızı ActiveX denetimi desteği istediğinizi önceden bilmeniz, makalesine bakın. [MFC ActiveX denetimi kapsayıcısı oluşturma](../mfc/reference/creating-an-mfc-activex-control-container.md).

>[!IMPORTANT]
> ActiveX yeni geliştirme projeleri için kullanılmaması gereken eski bir teknolojidir. ActiveX yerini modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimlerini](activex-controls.md).

> [!NOTE]
>  Bu makalede, kapsayıcı ve yordamları ve kod örnekleri olarak Dai adlı bir katıştırılmış denetime adlı bir iletişim kutusu tabanlı ActiveX denetimi kapsayıcısı proje kullanır.

ActiveX denetimlerini desteklemek için iki proje dosyaları için bir kod satırı eklemelisiniz.

- Değişiklik, ana iletişim kutusunun `InitInstance` işlevi (KAPSAYICISINDA bulunamadı. CPP) çağrısını yapmadan MFC Uygulama Sihirbazı tarafından [AfxEnableControlContainer](reference/ole-initialization.md#afxenablecontrolcontainer), aşağıdaki örnekte olduğu gibi:

   [!code-cpp[NVC_MFCOleContainer#34](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_1.cpp)]
    [!code-cpp[NVC_MFCOleContainer#35](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_2.cpp)]

- Projenizin STDAFX için aşağıdakileri ekleyin. H üst bilgi dosyası:

   [!code-cpp[NVC_MFCOleContainer#36](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_3.h)]

Bu adımları tamamladıktan sonra tıklayarak projenizi yeniden derleyin **derleme** üzerinde **derleme** menüsü.

## <a name="see-also"></a>Ayrıca Bkz.

[ActiveX Denetim Kapsayıcıları](../mfc/activex-control-containers.md)

