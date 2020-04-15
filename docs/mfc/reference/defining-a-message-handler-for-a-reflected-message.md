---
title: Yansımış Bir İleti İçin İleti İşleyicisi Tanımlama
ms.date: 09/07/2019
f1_keywords:
- vc.codewiz.defining.msg.msghandler
helpviewer_keywords:
- messages [MFC], reflected
- message handling [MFC], reflected messages
ms.assetid: 5a403528-58c5-46e7-90d5-4a77f0ab9b9c
ms.openlocfilehash: f7f90d3347ac61abcfcb48e77ef39aa2626ae5c8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365852"
---
# <a name="defining-a-message-handler-for-a-reflected-message"></a>Yansımış Bir İleti İçin İleti İşleyicisi Tanımlama

Yeni bir MFC denetim sınıfı oluşturduktan sonra, bunun için ileti işleyicileri tanımlayabilirsiniz. Yansıyan ileti işleyicileri, ileti üst öğetarafından alınmadan önce denetim sınıfınızın kendi iletilerini işlemesine izin verir. Denetiminizden bir üst pencereye ileti göndermek için MFC [CWnd::SendMessage](../../mfc/reference/cwnd-class.md#sendmessage) işlevini kullanabilirsiniz.

Bu işlevsellik ile, örneğin, bunu yapmak için üst pencere (sahibi çizilmiş) güvenerek yerine kendini yeniden çizecek bir liste kutusu oluşturabilirsiniz. Yansıyan iletiler hakkında daha fazla bilgi için [bkz.](../../mfc/handling-reflected-messages.md)

Aynı işlevsellik ile [bir ActiveX denetimi](../../mfc/activex-controls-on-the-internet.md) oluşturmak için ActiveX denetimi için bir proje oluşturmanız gerekir.

> [!NOTE]
> Aşağıda açıklandığı gibi Sınıf Sihirbazı'nı kullanarak ActiveX denetimi için yansıtılmış ileti (OCM_*İleti)* ekleyemezsiniz. Bu iletileri el ile eklemeniz gerekir.

### <a name="to-define-a-message-handler-for-a-reflected-message-from-the-class-wizard"></a>Sınıf Sihirbazı'ndan yansıyan bir ileti için ileti işleyicisi tanımlamak için

1. MFC projenize liste, demir çubuğu denetimi, araç çubuğu veya ağaç denetimi gibi bir denetim ekleyin.

1. Sınıf Görünümü'nde, denetim sınıfınızın adını tıklatın.

1. Sınıf [Sihirbazı'nda](mfc-class-wizard.md)denetim sınıfı adı **Sınıf Adı** listesinde görünür.

1. Denetime eklemek için kullanılabilir Windows iletilerini görüntülemek için **Mesajlar** sekmesini tıklatın.

1. Bir işleyici tanımlamak istediğiniz yansıyan iletiyi seçin. Yansıtılan iletiler eşit işaretle işaretlenir (=).

1. Işleyicinin önerilen adını işleyicinin>\< *Işleyici Adı*olarak görüntülemek için Sınıf Sihirbazı'ndaki sağ sütundaki hücreyi tıklatın. (Örneğin, **=WM_CTLCOLOR** ileti işleyicisi \< **ctlColor**>eklemeyi önerir).

1. Kabul etmek için önerilen adı tıklatın. İşleyici projenize eklenir.

1. İleti işleyicisini düzenlemek veya silmek için 4 ile 7 arası adımları yineleyin. Düzenlemek veya silmek için işleyici adını içeren hücreyi tıklatın ve uygun görevi tıklatın.

## <a name="see-also"></a>Ayrıca bkz.

[İletileri İşlevlere Eşleme](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[Kod Sihirbazlarıyla İşlevsellik Ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Sınıf Ekleme](../../ide/adding-a-class-visual-cpp.md)<br/>
[Üye İşlev Ekleme](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Üye Değişkeni Ekleme](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Sanal İşlev Geçersiz Kılma](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC İleti Işleyicisi](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Sınıf Yapısında Gezinme](../../ide/navigate-code-cpp.md)
