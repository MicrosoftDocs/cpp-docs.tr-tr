---
title: 'MFC ActiveX Denetimleri: Olaylar'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], events
- notifications [MFC], notifying containers of events
- custom events [MFC], adding to ActiveX controls
- events [MFC], mapping
- COleControl class [MFC], handling of events
- mappings [MFC], events
- stock events [MFC]
- container events [MFC]
- events [MFC], ActiveX controls
- OLE events [MFC]
ms.assetid: e1e57e0c-206b-4923-a0b5-682c26564f74
ms.openlocfilehash: 76557e64b5b53c32a7d7f63134085e86bf0138df
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50540679"
---
# <a name="mfc-activex-controls-events"></a>MFC ActiveX Denetimleri: Olaylar

ActiveX denetimleri, olayları bir denetime gerçekleşen bir kapsayıcı bildirmek için kullanın. Genel olaylar denetim, klavye ve değişiklikleri denetimin durumda kullanarak girilen veriler tıklar örneklerindendir. Bu eylemler olduğunda denetim kapsayıcı uyaran bir olay tetikler.

Olaylar, iletiler olarak da adlandırılır.

MFC, iki tür olay destekler: stok ve özel. Stok olaylardır sınıfı bu olayları [COleControl](../mfc/reference/colecontrol-class.md) otomatik olarak işler. Stok olayları tam listesi için bkz [MFC ActiveX denetimleri: stok olaylar ekleme](../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md). Özel olaylar bir denetim kapsayıcı ilgili denetimin belirli bir eylem meydana geldiğinde bildirim olanağı sağlar. Bazı örnekler bir denetimin iç durumunu veya belirli bir pencere ileti bir değişiklik olur.

Denetiminiz olaylarını düzgün bir şekilde başlatmak, ilişkili olay gerçekleştiğinde çağrılması gereken bir üye işlev için her bir olay denetimi denetim sınıfınıza eşlemeniz gerekir. Bu eşleme mekanizması (bir olay eşlemesi olarak bilinir), olay hakkında bilgiler merkezileştirir ve kolay erişim ve denetim olaylarını işlemek Visual Studio sağlar. Bu olay eşlemesi üstbilgisinde bulunan aşağıdaki makro tarafından bildirilen (. H) denetim sınıf bildiriminin dosya:

[!code-cpp[NVC_MFC_AxUI#2](../mfc/codesnippet/cpp/mfc-activex-controls-events_1.h)]

Olay eşlemesi bildirildikten sonra bu denetimin uygulamasında tanımlanmış olmalıdır (. CPP) dosyası. Belirli olayları tetiklemesine denetim sağlayan olay eşlemesi, aşağıdaki kod satırlarını tanımlayın:

[!code-cpp[NVC_MFC_AxUI#3](../mfc/codesnippet/cpp/mfc-activex-controls-events_2.cpp)]
[!code-cpp[NVC_MFC_AxUI#4](../mfc/codesnippet/cpp/mfc-activex-controls-events_3.cpp)]

Projeyi oluşturmak için MFC ActiveX Denetim Sihirbazı'nı kullanırsanız, bu satırlar otomatik olarak ekler. MFC ActiveX Denetim Sihirbazı'nı kullanmıyorsanız, bu satırlar el ile eklemeniz gerekir.

Sınıf Görünümü ile sınıfı tarafından desteklenen stok olaylar ekleme `COleControl` veya tanımladığınız özel olaylar. Her yeni olay için sınıf görünümü otomatik olarak denetimin denetimin olay eşlemesi ile düzgün bir giriş ekler. IDL dosyası.

İki diğer makaleler olayları ayrıntılı açıklanmaktadır:

- [MFC ActiveX denetimleri: Stok olaylar ekleme](../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)

- [MFC ActiveX Denetimleri: Özel Olaylar Ekleme](../mfc/mfc-activex-controls-adding-custom-events.md)

## <a name="see-also"></a>Ayrıca Bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX Denetimleri: Yöntemler](../mfc/mfc-activex-controls-methods.md)<br/>
[COleControl Sınıfı](../mfc/reference/colecontrol-class.md)
