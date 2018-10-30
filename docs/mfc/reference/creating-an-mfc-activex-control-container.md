---
title: MFC ActiveX denetimi kapsayıcısı oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.activex.container
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], containers
- ActiveX control containers [MFC], creating
- containers [MFC], creating
- OLE controls [MFC], containers
ms.assetid: ec70e137-7c14-4940-bd0e-fd4edcc63ea5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bc12be2b7d3e25059333d4f22bd2d8eb458b959c
ms.sourcegitcommit: a3c9e7888b8f437a170327c4c175733ad9eb0454
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2018
ms.locfileid: "50204398"
---
# <a name="creating-an-mfc-activex-control-container"></a>MFC ActiveX Denetimi Kapsayıcısı Oluşturma

Bir ActiveX denetimi kapsayıcısı bir ActiveX (eski adı OLE) denetimini çalıştırmak ortamı sağlayan bir üst programdır. Özelliğine sahip olan veya olmayan MFC ActiveX denetimleri içeren bir uygulama oluşturabilirsiniz, ancak ile MFC yapmak daha kolaydır.

>[!IMPORTANT]
> ActiveX yeni geliştirme projeleri için kullanılmaması gereken eski bir teknolojidir. ActiveX yerine geçen modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimlerini](../activex-controls.md).

Bir MFC kapsayıcı programını kullanarak oluşturma [MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md) MFC ve ActiveX sınıfları tarafından uygulanan özellikleri ActiveX denetimlerini ve Otomasyon erişmenize olanak sağlar. Bu özellikler, görsel düzenleme, otomasyon, bileşik dosyalar oluşturma içerir ve denetimler için destek. Bir kapsayıcı, bir mini sunucu, bir tam sunucu ve bir kapsayıcı hem bir sunucusu olan bir program oluşturma üst programınızı destekleyen MFC Uygulama Sihirbazı'nı visual düzenleme seçeneklerini içerir.

- **Yeni bir MFC uygulaması**. Otomasyon içeren yeni bir MFC programı oluşturmak için görsel düzenleme, dosyalar, bileşik veya destek denetlemek, MFC Uygulama Sihirbazı'nı kullanın ve uygun Otomasyon seçenekleri belirleyin.

- **Varolan bir MFC uygulamasına**. Varolan bir MFC uygulamasına denetimi kapsamasını ekliyorsanız, bkz. [OLE denetim kapsayıcıları: el ile etkinleştirme OLE denetim kapsamı](../../mfc/activex-control-containers-manually-enabling-activex-control-containment.md).

### <a name="to-create-an-activex-container-for-any-of-the-following-types-of-applications"></a>Aşağıdaki uygulama türlerini herhangi bir ActiveX kapsayıcısı oluşturmak için

1. [Kapsayıcılar](../../mfc/containers.md)

1. [Görsel düzenleme](../../mfc/ole-mfc.md)

1. [MFC ActiveX denetimleri](../../mfc/mfc-activex-controls.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Visual C++ Proje Türleri](../../ide/visual-cpp-project-types.md)

