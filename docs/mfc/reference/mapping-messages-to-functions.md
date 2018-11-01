---
title: İletileri İşlevlere Eşleme
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.mapping.msg.function
helpviewer_keywords:
- Windows messages [MFC], adding message handlers
- message maps [MFC], mapping messages to functions
ms.assetid: a7727a62-f638-4b20-b7f5-131f47200d6a
ms.openlocfilehash: 0393475143b9448091d4a886c43ce1206c655b25
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629196"
---
# <a name="mapping-messages-to-functions"></a>İletileri İşlevlere Eşleme

Özellikler penceresinde, ileti işleyicileri (MFC kullanıcı arabirimi sınıfının üye fonksiyonları) bağlamak, uygulamanızın kaynaklar tarafından oluşturulan iletileri sağlar. Kullandıkları [MFC ileti eşlemeleri](../../mfc/messages-and-commands-in-the-framework.md) bağlamayı oluşturmak için.

Framework sınıflarının birinden türetilmiş yeni bir sınıf oluşturmak için sınıf görünümü kullandığınızda, bu otomatik olarak tam ve işlevsel bir yerde üstbilgi (.h) ve uygulama (.cpp), belirttiğiniz sınıf dosyaları.

> [!NOTE]
>  İletileri işlemiyor yeni bir sınıf eklemek için doğrudan Metin Düzenleyicisi'nde bir sınıf oluşturun.

### <a name="to-define-or-remove-a-message-handler-using-the-properties-window"></a>Tanımlayın veya Özellikler penceresini kullanarak bir ileti işleyicisi kaldırmak için

1. Sınıf Görünümü'nde sınıfı tıklayın.

1. Özellikler penceresinde tıklayın **iletileri** düğmesi.

    > [!NOTE]
    >  **İletileri** düğmesi, sınıf görünümü veya kaynak pencereye tıkladığınızda, sınıf adı seçtiğinizde kullanılabilir.

   Projenizin bir ileti için bir işleyici varsa, işleyici adını iletinin yanındaki sağ sütunda görüntülenir.

1. İleti işleyici yok sahipse, sonra sağ sütunda işleyici önerilen adını görüntülemek için Özellikler penceresindeki hücreyi tıklatın \<Ekle >*HandlerName*. (Örneğin, WM_TIMER ileti işleyicisi önerir \<Ekle >`OnTimer`).

1. İşlev için saptama kodu eklemek için önerilen adına tıklayın.

1. Bir ileti işleyicisi düzenlemek için Sınıf Görünümü'nde iletiye çift tıklayın ve kaynak penceresinde kodu düzenleyin.

Bir ileti işleyicisi kaldırmak için sağ sütunda işleyici çift tıklatın ve seçin \<sil >*HandlerName*. İşlev kod dışı bırakılmıştır.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC ileti işleyicisi](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Kod sihirbazlarıyla işlevsellik ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)<br/>
[Üye işlevi ekleme](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Üye değişkeni ekleme](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Bir sanal işlevi geçersiz kılma](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[İletişim Kutusu Denetimleri için Olay İşleyicileri Ekleme](../../windows/adding-event-handlers-for-dialog-box-controls.md)<br/>
[Sınıf yapısında gezinme](../../ide/navigating-the-class-structure-visual-cpp.md)
