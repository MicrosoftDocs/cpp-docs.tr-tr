---
title: 'ActiveX Denetimi Kapsayıcıları: ActiveX Denetimi Kapsamasını El İle Etkinleştirme'
ms.date: 09/12/2018
helpviewer_keywords:
- AfxEnableControlContainer method [MFC]
- ActiveX control containers [MFC], enabling
- ActiveX controls [MFC], enabling containers
ms.assetid: 833bcde9-c9ad-4709-ad12-2fc2150fb6a5
ms.openlocfilehash: 94ad6e8356b5dab54ae97dbdd90812039d1425c9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322062"
---
# <a name="activex-control-containers-manually-enabling-activex-control-containment"></a>ActiveX Denetimi Kapsayıcıları: ActiveX Denetimi Kapsamasını El İle Etkinleştirme

Uygulamanızı oluşturmak için MFC Uygulama Sihirbazı'nı kullandığınızda ActiveX denetim desteğini etkinleştirmediyseniz, bu desteği el ile eklemeniz gerekir. Bu makalede, varolan bir OLE kapsayıcı uygulamasına activex denetim içeren el ile ekleme işlemi açıklanmaktadır. OLE kapsayıcınızda ActiveX denetim desteği istediğinizi önceden biliyorsanız, [MFC ActiveX Denetim Kapsayıcısı Oluşturma](../mfc/reference/creating-an-mfc-activex-control-container.md)makalesine bakın.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılmaması gereken eski bir teknolojidir. ActiveX'in yerini alabilecek modern teknolojiler hakkında daha fazla bilgi için [ActiveX Denetimleri'ne](activex-controls.md)bakın.

> [!NOTE]
> Bu makalede, kapsayıcı adlı iletişim kutusu tabanlı activex denetim kapsayıcı sı ve yordamlar ve kodörnekleri olarak Circ adlı katıştırılmış denetim kullanır.

ActiveX denetimlerini desteklemek için projenizin iki dosyasına bir kod satırı eklemeniz gerekir.

- Ana iletişim kutunuzun `InitInstance` işlevini değiştirin (CONTAINER'da bulunur. CPP) MFC Uygulama Sihirbazı tarafından [AfxEnableControlContainer](reference/ole-initialization.md#afxenablecontrolcontainer)bir çağrı yapma , aşağıdaki örnekte olduğu gibi:

   [!code-cpp[NVC_MFCOleContainer#34](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_1.cpp)]
    [!code-cpp[NVC_MFCOleContainer#35](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_2.cpp)]

- Projenizin STDAFX'ine aşağıdakileri ekleyin. H üstbilgi dosyası:

   [!code-cpp[NVC_MFCOleContainer#36](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_3.h)]

Bu adımları tamamladıktan **sonra, Yapı** menüsünde **Oluştur'u** tıklatarak projenizi yeniden oluşturun.

## <a name="see-also"></a>Ayrıca bkz.

[ActiveX Kontrol Kapları](../mfc/activex-control-containers.md)
