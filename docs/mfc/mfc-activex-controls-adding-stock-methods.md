---
description: 'Daha fazla bilgi edinin: MFC ActiveX denetimleri: stok yöntemleri ekleme'
title: 'MFC ActiveX Denetimleri: Stok Yöntemler Ekleme'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], stock methods
- MFC ActiveX controls [MFC], methods
- DoClick method [MFC]
ms.assetid: bc4fad78-cabd-4cc0-a798-464b1a682f0b
ms.openlocfilehash: 1bd176c81a3c97ad5530a9b1971656e5204fe407
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202879"
---
# <a name="mfc-activex-controls-adding-stock-methods"></a>MFC ActiveX Denetimleri: Stok Yöntemler Ekleme

Bir stok yöntemi, sınıf [Colet denetimi](reference/colecontrol-class.md)tarafından zaten uygulanmış olan özel bir yöntemden farklıdır. Örneğin, `COleControl` denetiminiz Için Refresh metodunu destekleyen önceden tanımlanmış bir üye işlevi içerir. Bu stok yöntemi için dağıtım Haritası girişi DISP_STOCKFUNC_REFRESH.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılması gereken eski bir teknolojidir. ActiveX 'in yerini alan modern teknolojiler hakkında daha fazla bilgi için bkz. [ActiveX denetimleri](activex-controls.md).

`COleControl` iki stok yöntemini destekler: Dotıkla ve Yenile. Yenileme denetimin kullanıcı tarafından denetimin görünümünü hemen güncelleştirmek için çağrılır; Denetimin Click olayını harekete geçmek için DoClick çağrılır.

|Yöntem|Dağıtım eşleme girişi|Yorum|
|------------|------------------------|-------------|
|`DoClick`|**DISP_STOCKPROP_DOCLICK ()**|Bir tıklama olayı tetikler.|
|`Refresh`|**DISP_STOCKPROP_REFRESH ()**|Denetimin görünümünü hemen güncelleştirir.|

## <a name="adding-a-stock-method-using-the-add-method-wizard"></a><a name="_core_adding_a_stock_method_using_classwizard"></a> Yöntem Ekleme Sihirbazı 'Nı kullanarak stok yöntemi ekleme

Bir stok yöntemi ekleme [yöntemi ekleme Sihirbazı](../ide/adding-a-method-visual-cpp.md#add-method-wizard)kullanılarak basittir. Aşağıdaki yordamda, MFC ActiveX Denetim Sihirbazı kullanılarak oluşturulan bir denetime yenileme yönteminin eklenmesi gösterilmektedir.

#### <a name="to-add-the-stock-refresh-method-using-the-add-method-wizard"></a>Yöntem Ekleme Sihirbazı 'Nı kullanarak hisse senedi yenileme yöntemi eklemek için

1. Denetiminizin projesini yükleyin.

1. Sınıf Görünümü, denetiminizin kitaplık düğümünü genişletin.

1. Kısayol menüsünü açmak için denetiminizin arabirim düğümüne (kitaplık düğümünün ikinci düğümü) sağ tıklayın.

1. Kısayol menüsünde, **Ekle** ' ye ve ardından **Yöntem Ekle**' ye tıklayın.

   Bu, yöntem ekleme Sihirbazı ' nı açar.

1. **Yöntem adı** kutusunda **Yenile**' ye tıklayın.

1. **Finish (Son)** düğmesine tıklayın.

## <a name="add-method-wizard-changes-for-stock-methods"></a><a name="_core_classwizard_changes_for_stock_methods"></a> Stok yöntemleri için yöntem ekleme Sihirbazı değişiklikleri

Stok yenileme yöntemi denetimin temel sınıfı tarafından desteklendiğinden, **Yöntem Ekleme Sihirbazı** denetimin sınıf bildirimini hiçbir şekilde değiştirmez. Bir yöntemi, denetimin dağıtım eşlemesine ve öğesine bir giriş ekler. IDL dosyası. Aşağıdaki satır, denetimin dağıtım eşlemesine, uygulamasında bulunur (. CPP) dosyası:

[!code-cpp[NVC_MFC_AxUI#16](codesnippet/cpp/mfc-activex-controls-adding-stock-methods_1.cpp)]

Bu, yenileme yöntemini denetimin kullanıcıları için kullanılabilir hale getirir.

Aşağıdaki satır denetimin öğesine eklenir. IDL dosyası:

[!code-cpp[NVC_MFC_AxUI#17](codesnippet/cpp/mfc-activex-controls-adding-stock-methods_2.idl)]

Bu satır, yenileme yöntemine belirli bir KIMLIK numarası atar.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)
