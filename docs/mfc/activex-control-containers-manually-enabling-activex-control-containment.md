---
description: 'Daha fazla bilgi edinin: ActiveX denetim kapsayıcıları: ActiveX denetim kapsamayı El Ile etkinleştirme'
title: 'ActiveX Denetimi Kapsayıcıları: ActiveX Denetimi Kapsamasını El İle Etkinleştirme'
ms.date: 09/12/2018
helpviewer_keywords:
- AfxEnableControlContainer method [MFC]
- ActiveX control containers [MFC], enabling
- ActiveX controls [MFC], enabling containers
ms.assetid: 833bcde9-c9ad-4709-ad12-2fc2150fb6a5
ms.openlocfilehash: 44ca8961b064aee1efd4a24dd5bf6841399131e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277966"
---
# <a name="activex-control-containers-manually-enabling-activex-control-containment"></a>ActiveX Denetimi Kapsayıcıları: ActiveX Denetimi Kapsamasını El İle Etkinleştirme

Uygulamanızı oluşturmak için MFC Uygulama Sihirbazı 'Nı kullandığınızda ActiveX denetim desteğini etkinleştirmezseniz, bu desteği el ile eklemeniz gerekir. Bu makalede, var olan bir OLE kapsayıcı uygulamasına ActiveX denetim kapsamayı el ile ekleme işlemi açıklanır. OLE kapsayıcınızda ActiveX denetimi desteğinin olmasını istediğinizi biliyorsanız, [MFC ActiveX Denetim kapsayıcısı oluşturma](reference/creating-an-mfc-activex-control-container.md)makalesine bakın.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılması gereken eski bir teknolojidir. ActiveX 'in yerini alan modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimleri](activex-controls.md).

> [!NOTE]
> Bu makalede, kapsayıcı adlı bir iletişim kutusu tabanlı ActiveX Denetim kapsayıcısı projesi ve farklı Circ adlı bir katıştırılmış denetim, yordamlar ve kodda örnek olarak kullanılır.

ActiveX denetimlerini desteklemek için projenizin dosyalarından birine bir kod satırı eklemeniz gerekir.

- Ana iletişim kutusunun `InitInstance` işlevini (kapsayıcıda bulunan) değiştirin. CPP) MFC Uygulama Sihirbazı tarafından, aşağıdaki örnekte olduğu gibi [AfxEnableControlContainer](reference/ole-initialization.md#afxenablecontrolcontainer)öğesine çağrı yapar:

   [!code-cpp[NVC_MFCOleContainer#34](codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_1.cpp)]
    [!code-cpp[NVC_MFCOleContainer#35](codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_2.cpp)]

- Aşağıdakileri projenizin STDADFX öğesine ekleyin. H üst bilgi dosyası:

   [!code-cpp[NVC_MFCOleContainer#36](codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_3.h)]

Bu adımları tamamladıktan sonra, **derleme** menüsünde **Oluştur** ' a tıklayarak projenizi yeniden derleyin.

## <a name="see-also"></a>Ayrıca bkz.

[ActiveX denetim kapsayıcıları](activex-control-containers.md)
