---
title: 'MFC ActiveX Denetimleri: Stok Yöntemler Ekleme'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], stock methods
- MFC ActiveX controls [MFC], methods
- DoClick method [MFC]
ms.assetid: bc4fad78-cabd-4cc0-a798-464b1a682f0b
ms.openlocfilehash: ec59ccc0cbd48fc3114eb2dc0833dd3dd65691de
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364677"
---
# <a name="mfc-activex-controls-adding-stock-methods"></a>MFC ActiveX Denetimleri: Stok Yöntemler Ekleme

Stok yöntemi, [coleControl](../mfc/reference/colecontrol-class.md)sınıfı tarafından zaten uygulandığı için özel bir yöntemden farklıdır. Örneğin, `COleControl` denetiminiz için Yenileme yöntemini destekleyen önceden tanımlanmış bir üye işlev içerir. Bu stok yöntemi için sevk haritası girişi DISP_STOCKFUNC_REFRESH.

>[!IMPORTANT]
> ActiveX, yeni geliştirme için kullanılmaması gereken eski bir teknolojidir. ActiveX'in yerini alabilecek modern teknolojiler hakkında daha fazla bilgi için [ActiveX Denetimleri'ne](activex-controls.md)bakın.

`COleControl`iki stok yöntemini destekler: DoClick ve Refresh. Yenileme, denetimin görünümünü hemen güncelleştirmek için denetimin kullanıcısı tarafından çağrılır; DoClick, denetimin Click etkinliğini ateşlemek için çağrılır.

|Yöntem|Sevkiyat haritası girişi|Açıklama|
|------------|------------------------|-------------|
|`DoClick`|**DISP_STOCKPROP_DOCLICK ( )**|Bir Tıklama olayını ateşler.|
|`Refresh`|**DISP_STOCKPROP_REFRESH ( )**|Denetimin görünümünü hemen güncelleştirir.|

## <a name="adding-a-stock-method-using-the-add-method-wizard"></a><a name="_core_adding_a_stock_method_using_classwizard"></a>Ekle Yöntemi Sihirbazı'nı Kullanarak Stok Yöntemi Ekleme

Stok yöntemi ekleme yöntemi [sihirbazı](../ide/add-method-wizard.md)kullanılarak basittir. Aşağıdaki yordam, MFC ActiveX Denetim Sihirbazı kullanılarak oluşturulan denetime Yenileme yönteminin eklenmesini gösterir.

#### <a name="to-add-the-stock-refresh-method-using-the-add-method-wizard"></a>Ekle Yöntemi Sihirbazı'nı kullanarak stok Yenileme yöntemini eklemek için

1. Denetiminizin projesini yükleyin.

1. Sınıf Görünümü'nde, denetiminizin kitaplık düğümunu genişletin.

1. Kısayol menüsünü açmak için denetiminiz için arabirim düğümüne (kitaplık düğümünün ikinci düğümü) sağ tıklayın.

1. Kısayol menüsünden **Ekle'yi** tıklatın ve ardından **Yöntem Ekle'yi**tıklatın.

   Bu, Yöntem Ekle Sihirbazı'nı açar.

1. Yöntem **Adı** **kutusunda, Yenile'yi**tıklatın.

1. **Son**'a tıklayın.

## <a name="add-method-wizard-changes-for-stock-methods"></a><a name="_core_classwizard_changes_for_stock_methods"></a>Stok Yöntemleri için Yöntem Sihirbazı Değişiklikleri Ekle

Stok Yenileme yöntemi denetimin taban sınıfı tarafından desteklendirilmesin, **Yöntem Ekle Sihirbazı** denetimin sınıf bildirimini hiçbir şekilde değiştirmez. Yöntem için bir giriş ekler denetimin sevkiyat haritasına ve onun . IDL dosyası. Aşağıdaki satır, denetimin uygulanmasında bulunan sevk haritasına eklenir (. CPP) dosyası:

[!code-cpp[NVC_MFC_AxUI#16](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-methods_1.cpp)]

Bu, Yenileme yöntemini denetimkullanıcılarının kullanımına sunar.

Aşağıdaki satır denetimin. IDL dosyası:

[!code-cpp[NVC_MFC_AxUI#17](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-methods_2.idl)]

Bu satır, Yenileme yöntemine belirli bir kimlik numarası atar.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Kontrolleri](../mfc/mfc-activex-controls.md)
