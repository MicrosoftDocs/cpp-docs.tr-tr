---
title: İletileri işlevlere eşleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.mapping.msg.function
dev_langs:
- C++
helpviewer_keywords:
- Windows messages [MFC], adding message handlers
- message maps [MFC], mapping messages to functions
ms.assetid: a7727a62-f638-4b20-b7f5-131f47200d6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 962a86139b7fdf8afac08e04e7b42240603b4374
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37335532"
---
# <a name="mapping-messages-to-functions"></a>İletileri İşlevlere Eşleme
Özellikler penceresinde, ileti işleyicileri (MFC kullanıcı arabirimi sınıfının üye fonksiyonları) bağlamak, uygulamanızın kaynaklar tarafından oluşturulan iletileri sağlar. Kullandıkları [MFC ileti eşlemeleri](../../mfc/messages-and-commands-in-the-framework.md) bağlamayı oluşturmak için.  
  
 Framework sınıflarının birinden türetilmiş yeni bir sınıf oluşturmak için sınıf görünümü kullandığınızda, bu otomatik olarak tam ve işlevsel bir yerde üstbilgi (.h) ve uygulama (.cpp), belirttiğiniz sınıf dosyaları.  
  
> [!NOTE]
>  İletileri işlemiyor yeni bir sınıf eklemek için doğrudan Metin Düzenleyicisi'nde bir sınıf oluşturun.  
  
### <a name="to-define-or-remove-a-message-handler-using-the-properties-window"></a>Tanımlayın veya Özellikler penceresini kullanarak bir ileti işleyicisi kaldırmak için  
  
1.  Sınıf Görünümü'nde sınıfı tıklayın.  
  
2.  Özellikler penceresinde tıklayın **iletileri** düğmesi.  
  
    > [!NOTE]
    >  **İletileri** düğmesi, sınıf görünümü veya kaynak pencereye tıkladığınızda, sınıf adı seçtiğinizde kullanılabilir.  
  
     Projenizin bir ileti için bir işleyici varsa, işleyici adını iletinin yanındaki sağ sütunda görüntülenir.  
  
3.  İleti işleyici yok sahipse, sonra sağ sütunda işleyici önerilen adını görüntülemek için Özellikler penceresindeki hücreyi tıklatın \<Ekle >*HandlerName*. (Örneğin, WM_TIMER ileti işleyicisi önerir \<Ekle >`OnTimer`).  
  
4.  İşlev için saptama kodu eklemek için önerilen adına tıklayın.  
  
5.  Bir ileti işleyicisi düzenlemek için Sınıf Görünümü'nde iletiye çift tıklayın ve kaynak penceresinde kodu düzenleyin.  
  
 Bir ileti işleyicisi kaldırmak için sağ sütunda işleyici çift tıklatın ve seçin \<sil >*HandlerName*. İşlev kod dışı bırakılmıştır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ileti işleyicisi](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Kod sihirbazlarıyla işlevsellik ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)   
 [Üye işlevi ekleme](../../ide/adding-a-member-function-visual-cpp.md)   
 [Üye değişkeni ekleme](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Bir sanal işlevi geçersiz kılma](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [İletişim kutusu denetimleri için olay işleyicileri ekleme](../../windows/adding-event-handlers-for-dialog-box-controls.md)   
 [Sınıf yapısında gezinme](../../ide/navigating-the-class-structure-visual-cpp.md)
