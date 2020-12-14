---
description: 'Daha fazla bilgi edinin: MFC ActiveX denetimleri: Otomasyon sunucusu oluşturma'
title: 'MFC ActiveX Denetimleri: Otomasyon Sunucusu Oluşturma'
ms.date: 11/04/2016
helpviewer_keywords:
- Automation servers [MFC], MFC ActiveX controls
- ActiveX controls [MFC], Automation server
- MFC ActiveX controls [MFC], Automation server
ms.assetid: e0c24ed2-d61c-49ad-a4fa-4e1098d1d39b
ms.openlocfilehash: ffac05d48a17e0f8b40f268709393fff392a3b95
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280735"
---
# <a name="mfc-activex-controls-creating-an-automation-server"></a>MFC ActiveX Denetimleri: Otomasyon Sunucusu Oluşturma

Bu denetimi başka bir uygulamada programlı bir şekilde katıştırma ve denetimdeki yöntemleri uygulamadan çağırmak amacıyla bir Otomasyon sunucusu olarak MFC ActiveX denetimi geliştirebilirsiniz. Bu tür bir denetim, ActiveX denetim kapsayıcısında barındırılmak için kullanılabilir olmaya devam eder.

### <a name="to-create-a-control-as-an-automation-server"></a>Otomasyon sunucusu olarak bir denetim oluşturmak için

1. Denetimi [oluşturun](reference/mfc-activex-control-wizard.md) .

1. [Yöntem ekleyin](mfc-activex-controls-methods.md).

1. Geçersiz kılma [IsInvokeAllowed](reference/colecontrol-class.md#isinvokeallowed).

1. Denetimi oluşturun.

### <a name="to-programmatically-access-the-methods-in-an-automation-server"></a>Otomasyon sunucusundaki yöntemlere programlı olarak erişmek için

1. Bir uygulama oluşturun (örneğin, [MFC exe](reference/mfc-application-wizard.md)).

1. `InitInstance`İşlevin başlangıcında aşağıdaki satırı ekleyin:

   [!code-cpp[NVC_MFC_AxCont#17](codesnippet/cpp/mfc-activex-controls-creating-an-automation-server_1.cpp)]

1. Sınıf Görünümü, proje düğümüne sağ tıklayın ve tür kitaplığını içeri aktarmak için **TypeLib 'ten Sınıf Ekle** ' yi seçin.

   Bu, dosya adı uzantıları. h ve. cpp olan dosyaları projeye ekler.

1. ActiveX denetimindeki bir veya daha fazla yöntemi çağırabileceğiniz sınıfın üstbilgi dosyasında şu satırı ekleyin: `#include filename.h` , burada dosya adı, tür kitaplığını içeri aktardığınızda oluşturulan üst bilgi dosyasının adıdır.

1. ActiveX denetimindeki bir yönteme çağrı yapılacak işlevde, denetimin sarmalayıcı sınıfının bir nesnesini oluşturan ve ActiveX nesnesini oluşturan bir kod ekleyin. Örneğin, aşağıdaki MFC kodu bir `CCirc` denetim oluşturur, Caption özelliğini alır ve bir iletişim kutusunda Tamam düğmesine tıklandığında sonucu görüntüler:

   [!code-cpp[NVC_MFC_AxCont#18](codesnippet/cpp/mfc-activex-controls-creating-an-automation-server_2.cpp)]

Bir uygulamada kullandıktan sonra ActiveX denetimine Yöntemler eklerseniz, tür kitaplığını içeri aktardığınızda oluşturulan dosyaları silerek, uygulamada denetimin en son sürümünü kullanmaya başlayabilirsiniz. Sonra tür kitaplığını yeniden içeri aktarın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)
