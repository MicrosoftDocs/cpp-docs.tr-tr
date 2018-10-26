---
title: Yansımış bir ileti için ileti işleyicisi tanımlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.defining.msg.msghandler
dev_langs:
- C++
helpviewer_keywords:
- messages [MFC], reflected
- message handling [MFC], reflected messages
ms.assetid: 5a403528-58c5-46e7-90d5-4a77f0ab9b9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 104f9e0be67a350a1725dfbcd2bf234a8bc79553
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50052570"
---
# <a name="defining-a-message-handler-for-a-reflected-message"></a>Yansımış Bir İleti İçin İleti İşleyicisi Tanımlama

Yeni bir MFC denetim sınıf oluşturduktan sonra bunun için ileti işleyicileri tanımlayabilirsiniz. Yansımış bir ileti işleyicileri, ileti üst öğe tarafından alındığında önce kendi iletileri işlemek denetim sınıfınıza izin verir. MFC kullanabileceğiniz [CWnd::SendMessage](../../mfc/reference/cwnd-class.md#sendmessage) üst penceresine, denetiminden ileti göndermek için işlevi.

(Bunu sahip çizilmiş) yapmak için ana penceresinde güvenmek yerine yapabilirsiniz, örneğin, bu işlevin kendisi yeniden çizer bir liste kutusu oluşturun. Yansımış iletiler hakkında daha fazla bilgi için bkz. [yansımış iletileri işleme](../../mfc/handling-reflected-messages.md).

Oluşturmak için bir [ActiveX denetimi](../../mfc/activex-controls-on-the-internet.md) aynı işlevselliğe sahip ActiveX denetimi projesi oluşturmanız gerekir.

> [!NOTE]
>  Yansımış bir ileti ekleyemezsiniz (OCM_*ileti*) için bir ActiveX denetimi Özellikler penceresini kullanarak aşağıda açıklandığı gibi. Bu iletiler el ile eklemeniz gerekir.

### <a name="to-define-a-message-handler-for-a-reflected-message-from-the-properties-window"></a>Özellikler penceresinde yansımış bir ileti için ileti işleyicisi tanımlama

1. Bir liste gibi bir denetimin, bir çubuk barınağı denetimi, bir araç veya bir ağaç denetimi MFC projenize ekleyin.

1. Sınıf Görünümü'nde denetim sınıfınıza adına tıklayın.

1. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), denetim sınıf adı görünür **sınıf adı** listesi.

1. Tıklayın **iletileri** düğme denetimine eklemek kullanılabilir Windows iletileri görüntülemek için.

1. Özellikler penceresinde başlık görene kadar ileti listesini aşağı kaydırın **Reflected**. Alternatif olarak, tıklayın **kategorileri** düğmesine tıklayın ve görmek için görüntüyü Daralt **Reflected** başlığı.

1. Yansıtılan bir işleyici tanımlamak istediğiniz iletiyi seçin. Yansımış iletiler bir eşittir işareti (=) ile işaretlenir.

1. İşleyici önerilen adını görüntülemek için Özellikler penceresindeki sağ sütunda bir hücreyi tıklatın \<Ekle >*HandlerName*. (Örneğin, **WM_CTLCOLOR =** ileti işleyicisi önerir \<Ekle >**CtlColor**).

1. Kabul etmek için önerilen adına tıklayın. İşleyici, projenize eklenir.

   Eklediğiniz ileti işleyici adlarının yansımış iletiler penceresinin sağ sütunda görüntülenir.

9. Düzenleme ya da bir ileti işleyicisi silmek için 4-7 arası adımları yineleyin. Düzenleyin veya silin uygun göreve tıklayın işleyici adını içeren hücreye tıklayın.

## <a name="see-also"></a>Ayrıca Bkz.

[İletileri İşlevlere Eşleme](../../mfc/reference/mapping-messages-to-functions.md)<br/>
[Kod sihirbazlarıyla işlevsellik ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)<br/>
[Üye işlevi ekleme](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Üye değişkeni ekleme](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Bir sanal işlevi geçersiz kılma](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC ileti işleyicisi](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Sınıf yapısında gezinme](../../ide/navigating-the-class-structure-visual-cpp.md)
