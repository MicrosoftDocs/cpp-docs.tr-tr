---
title: 'MFC ActiveX denetimleri: Otomasyon sunucusu oluşturma'
ms.date: 11/04/2016
helpviewer_keywords:
- Automation servers [MFC], MFC ActiveX controls
- ActiveX controls [MFC], Automation server
- MFC ActiveX controls [MFC], Automation server
ms.assetid: e0c24ed2-d61c-49ad-a4fa-4e1098d1d39b
ms.openlocfilehash: 01f0162e124c5c49d45ce4a90f5243c88b09b5a0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62225261"
---
# <a name="mfc-activex-controls-creating-an-automation-server"></a>MFC ActiveX denetimleri: Otomasyon sunucusu oluşturma

MFC ActiveX denetimi programlı olarak başka bir uygulamada söz konusu denetim ekleme ve uygulamadan denetimi metotları çağırma amacıyla Otomasyon sunucusu olarak geliştirebilirsiniz. Bu tür bir denetim bir ActiveX denetimi kapsayıcısı içinde barındırılması kullanılabilir olacaktır.

### <a name="to-create-a-control-as-an-automation-server"></a>Otomasyon sunucusu bir denetim oluşturmak için

1. [Oluşturma](../mfc/reference/mfc-activex-control-wizard.md) denetimi.

1. [Yöntemler](../mfc/mfc-activex-controls-methods.md).

1. Geçersiz kılma [IsInvokeAllowed](../mfc/reference/colecontrol-class.md#isinvokeallowed).

1. Denetimi oluşturun.

### <a name="to-programmatically-access-the-methods-in-an-automation-server"></a>Otomasyon sunucusu yöntemlere programlı olarak erişmek için

1. Örneğin bir uygulama oluşturun, bir [MFC exe](../mfc/reference/mfc-application-wizard.md).

1. Başında `InitInstance` işlev, aşağıdaki satırı ekleyin:

   [!code-cpp[NVC_MFC_AxCont#17](../mfc/codesnippet/cpp/mfc-activex-controls-creating-an-automation-server_1.cpp)]

1. Sınıf Görünümü'nde proje düğümüne sağ tıklayıp **typelib'den sınıf ekleme** tür kitaplığını içeri aktarmak için.

   Bu dosya adı uzantıları .h ve .cpp dosyaları projeye ekler.

1. Burada, çağrılacak bir veya daha fazla yöntemi ActiveX denetimi üstbilgi dosyasında sınıfın, aşağıdaki satırı ekleyin: `#include filename.h`burada dosya adı tür kitaplığını içeri aktardığınızda oluşturduğunuz üstbilgi dosyasının adıdır.

1. İşlevi burada bir çağrı bir yöntemde bir ActiveX denetimi yapılmaz, denetimin sarmalayıcı sınıfın bir nesnesi oluşturan kodu ekleyin ve ActiveX nesnesi oluşturun. Örneğin, aşağıdaki MFC kodu örnekleyen bir `CCirc` denetimi, resim yazısı özelliğini alır ve bir iletişim kutusunda Tamam düğmesine tıklandığında edilen sonucu gösterir:

   [!code-cpp[NVC_MFC_AxCont#18](../mfc/codesnippet/cpp/mfc-activex-controls-creating-an-automation-server_2.cpp)]

Bir uygulamada kullandıktan sonra ActiveX denetimine yöntemleri eklerseniz, tür kitaplığı içeri aktarıldığında, oluşturulan dosyaları silerek uygulama denetimi en son sürümünü kullanarak başlayabilirsiniz. Ardından tür kitaplığı yeniden içeri aktarın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)
