---
description: 'Hakkında daha fazla bilgi edinin: yansıtılan bir Ileti için Ileti Işleyicisi tanımlama'
title: Yansımış Bir İleti İçin İleti İşleyicisi Tanımlama
ms.date: 09/07/2019
f1_keywords:
- vc.codewiz.defining.msg.msghandler
helpviewer_keywords:
- messages [MFC], reflected
- message handling [MFC], reflected messages
ms.assetid: 5a403528-58c5-46e7-90d5-4a77f0ab9b9c
ms.openlocfilehash: 5d742c589401f3537b34546dfa89bc50ca060d18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220194"
---
# <a name="defining-a-message-handler-for-a-reflected-message"></a>Yansımış Bir İleti İçin İleti İşleyicisi Tanımlama

Yeni bir MFC denetim sınıfı oluşturduktan sonra, bunun için ileti işleyicileri tanımlayabilirsiniz. Yansıtılan ileti işleyicileri, ileti üst öğe tarafından alınmadan önce denetim sınıfınızın kendi iletilerini işlemesini sağlar. Denetiminden bir ana pencereye ileti göndermek için MFC [CWnd:: SendMessage](../../mfc/reference/cwnd-class.md#sendmessage) işlevini kullanabilirsiniz.

Bu işlevle, örneğin, ana pencereye güvenmek yerine kendisini yeniden çizen bir liste kutusu oluşturabilirsiniz (sahip çizildi). Yansıtılan iletiler hakkında daha fazla bilgi için bkz. [yansıtılan Iletileri işleme](../../mfc/handling-reflected-messages.md).

Aynı işlevselliğe sahip bir [ActiveX denetimi](../../mfc/activex-controls-on-the-internet.md) oluşturmak Için, ActiveX denetimi için bir proje oluşturmanız gerekir.

> [!NOTE]
> Aşağıda açıklandığı gibi, sınıf Sihirbazı 'nı kullanarak bir ActiveX denetimi için yansıtılan bir ileti (OCM_ *iletisi*) ekleyemezsiniz. Bu iletileri el ile eklemeniz gerekir.

### <a name="to-define-a-message-handler-for-a-reflected-message-from-the-class-wizard"></a>Sınıf sihirbazından yansıtılan bir ileti için ileti işleyicisi tanımlama

1. MFC projenize liste, Rebar denetim, araç çubuğu veya ağaç denetimi gibi bir denetim ekleyin.

1. Sınıf Görünümü, denetim sınıfınızın adına tıklayın.

1. [Sınıf sihirbazında](mfc-class-wizard.md), denetim sınıfı adı **sınıf adı** listesinde görünür.

1. Denetime eklenecek Windows iletilerini göstermek için **iletiler** sekmesine tıklayın.

1. İşleyicisini tanımlamak istediğiniz yansıtılan iletiyi seçin. Yansıtılan iletiler eşittir işareti (=) ile işaretlenir.

1. İşleyicinin önerilen adını \<add> *HandlerName* olarak göstermek için sınıf sihirbazındaki sağ sütunundaki hücreye tıklayın. (Örneğin, **= WM_CTLCOLOR** ileti işleyicisi şunu önerir \<add> **CtlColor**).

1. Kabul etmek için önerilen ada tıklayın. İşleyici projenize eklenir.

1. Bir ileti işleyicisini düzenlemek veya silmek için 4 ile 7 arasındaki adımları yineleyin. Düzenlemek veya silmek için işleyici adını içeren hücreye tıklayın ve uygun görevi tıklatın.

## <a name="see-also"></a>Ayrıca bkz.

[Iletileri IŞLEVLERE eşleme](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[Kod Sihirbazlarıyla İşlevsellik Ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)<br/>
[Üye Işlevi ekleme](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Üye değişkeni ekleme](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Sanal Işlevi geçersiz kılma](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC Ileti Işleyicisi](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Sınıf yapısında gezinme](../../ide/navigate-code-cpp.md)
