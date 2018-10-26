---
title: 'MFC ActiveX denetimleri: Stok yöntemler ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], stock methods
- MFC ActiveX controls [MFC], methods
- DoClick method [MFC]
ms.assetid: bc4fad78-cabd-4cc0-a798-464b1a682f0b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e103e43f23746f8274ad00da4d043e3446dfc706
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50053034"
---
# <a name="mfc-activex-controls-adding-stock-methods"></a>MFC ActiveX Denetimleri: Stok Yöntemler Ekleme

Sınıfı tarafından zaten uygulandı, stok metodu bir özel yönteminden farklıdır [COleControl](../mfc/reference/colecontrol-class.md). Örneğin, `COleControl` denetim için yenileme yöntemi destekleyen önceden tanımlı üye işlevi içeriyor. Bu hisse senedi yöntemi için gönderme eşleme girişi DISP_STOCKFUNC_REFRESH ' dir.

>[!IMPORTANT]
> ActiveX yeni geliştirme projeleri için kullanılmaması gereken eski bir teknolojidir. ActiveX yerini modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimlerini](activex-controls.md).

`COleControl` Stok iki yöntemi destekler: DoClick ve yenileme. Yenileme denetiminin görünüşünü hemen güncelleştirmek için denetimin kullanıcı tarafından çağrılır; DoClick denetimin tıklatın ateşlenmesine çağrıldığında olay.

|Yöntem|Gönderme eşleme girişi|Yorum|
|------------|------------------------|-------------|
|`DoClick`|**DISP_STOCKPROP_DOCLICK)**|Bir tıklama olayı tetikler.|
|`Refresh`|**DISP_STOCKPROP_REFRESH)**|Hemen bir denetimin görünümünü güncelleştirir.|

##  <a name="_core_adding_a_stock_method_using_classwizard"></a> Stok yöntemi kullanarak bir ekleme yöntem Ekleme Sihirbazı

Stok yöntem ekleme basit kullanarak [yöntem Ekleme Sihirbazı'nı](../ide/add-method-wizard.md). Aşağıdaki yordam, MFC ActiveX Denetim Sihirbazı kullanılarak oluşturulan bir denetime Refresh yöntemi ekleme göstermektedir.

#### <a name="to-add-the-stock-refresh-method-using-the-add-method-wizard"></a>Yöntem Ekleme Sihirbazı'nı kullanarak stok Refresh yöntemi eklemek için

1. Denetiminizin proje yükleyin.

1. Sınıf Görünümü'nde denetim kitaplığı düğümünü genişletin.

1. Arabirim (ikinci düğüm kitaplığı düğümünün) denetlemek için kısayol menüsünü açmak için düğümü.

1. Kısayol menüsünden tıklayın **Ekle** ve ardından **Ekle yöntemi**.

   Bu yöntem Ekleme Sihirbazı'nı açar.

1. İçinde **yöntem adı** kutusunun **Yenile**.

1. **Son**'a tıklayın.

##  <a name="_core_classwizard_changes_for_stock_methods"></a> Yöntemi Sihirbazı değişiklikler için stok yöntemler ekleme

Stok Refresh yöntemi denetimin taban sınıfı tarafından desteklenmediği için **yöntem Ekleme Sihirbazı'nı** denetimin sınıf bildirimi hiçbir şekilde değiştirmez. Denetimin dağıtım eşlemesi ve çok yöntemi için bir giriş ekler. IDL dosyası. Denetimin dağıtım eşlemesi uygulaması içinde bulunan, aşağıdaki satırı eklenir (. CPP) dosyası:

[!code-cpp[NVC_MFC_AxUI#16](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-methods_1.cpp)]

Bu yenileme yöntemi denetimin kullanıcılara kullanılabilmesini sağlar.

Aşağıdaki satırı denetimin eklenir. IDL dosyası:

[!code-cpp[NVC_MFC_AxUI#17](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-methods_2.idl)]

Bu satırı Refresh yöntemi belirli bir kimlik numarası atar.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)

