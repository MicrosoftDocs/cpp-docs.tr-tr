---
title: 'ActiveX denetim kapsayıcıları: ActiveX denetimi kapsamasını el ile etkinleştirme'
ms.date: 09/12/2018
helpviewer_keywords:
- AfxEnableControlContainer method [MFC]
- ActiveX control containers [MFC], enabling
- ActiveX controls [MFC], enabling containers
ms.assetid: 833bcde9-c9ad-4709-ad12-2fc2150fb6a5
ms.openlocfilehash: 80ca25192f3dbda711b0398917cfa68571cd2c55
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394942"
---
# <a name="activex-control-containers-manually-enabling-activex-control-containment"></a>ActiveX denetim kapsayıcıları: ActiveX denetimi kapsamasını el ile etkinleştirme

Uygulamanızı oluşturmak için MFC Uygulama Sihirbazı kullanıldığında ActiveX denetimi desteği etkinleştirmediyseniz Bu destek el ile eklemeniz gerekir. Bu makalede el ile varolan bir OLE kapsayıcı uygulamaya ActiveX denetimi kapsamasını ekleme işlemi açıklanır. OLE kapsayıcınızı ActiveX denetimi desteği istediğinizi önceden bilmeniz, makalesine bakın. [MFC ActiveX denetimi kapsayıcısı oluşturma](../mfc/reference/creating-an-mfc-activex-control-container.md).

>[!IMPORTANT]
> ActiveX yeni geliştirme projeleri için kullanılmaması gereken eski bir teknolojidir. ActiveX yerine geçen modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimlerini](activex-controls.md).

> [!NOTE]
>  Bu makalede, kapsayıcı ve yordamları ve kod örnekleri olarak Dai adlı bir katıştırılmış denetime adlı bir iletişim kutusu tabanlı ActiveX denetimi kapsayıcısı proje kullanır.

ActiveX denetimlerini desteklemek için iki proje dosyaları için bir kod satırı eklemelisiniz.

- Değişiklik, ana iletişim kutusunun `InitInstance` işlevi (KAPSAYICISINDA bulunamadı. CPP) çağrısını yapmadan MFC Uygulama Sihirbazı tarafından [AfxEnableControlContainer](reference/ole-initialization.md#afxenablecontrolcontainer), aşağıdaki örnekte olduğu gibi:

   [!code-cpp[NVC_MFCOleContainer#34](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_1.cpp)]
    [!code-cpp[NVC_MFCOleContainer#35](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_2.cpp)]

- Projenizin STDAFX için aşağıdakileri ekleyin. H üst bilgi dosyası:

   [!code-cpp[NVC_MFCOleContainer#36](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_3.h)]

Bu adımları tamamladıktan sonra tıklayarak projenizi yeniden derleyin **derleme** üzerinde **derleme** menüsü.

## <a name="see-also"></a>Ayrıca bkz.

[ActiveX Denetim Kapsayıcıları](../mfc/activex-control-containers.md)
