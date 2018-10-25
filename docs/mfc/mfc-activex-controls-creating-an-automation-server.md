---
title: 'MFC ActiveX denetimleri: Otomasyon sunucusu oluşturma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Automation servers [MFC], MFC ActiveX controls
- ActiveX controls [MFC], Automation server
- MFC ActiveX controls [MFC], Automation server
ms.assetid: e0c24ed2-d61c-49ad-a4fa-4e1098d1d39b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e37e6183ca840067ceca47dd48f3b24d7b3b98c7
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50074546"
---
# <a name="mfc-activex-controls-creating-an-automation-server"></a>MFC ActiveX Denetimleri: Otomasyon Sunucusu Oluşturma

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

## <a name="see-also"></a>Ayrıca Bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)

