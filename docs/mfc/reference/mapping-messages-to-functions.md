---
title: "İletileri işlevlere eşleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.mapping.msg.function
dev_langs:
- C++
helpviewer_keywords:
- Windows messages [MFC], adding message handlers
- message maps [MFC], mapping messages to functions
ms.assetid: a7727a62-f638-4b20-b7f5-131f47200d6a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ad36b249e601e15e25f32ef1ef7e6d5a28874cf1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mapping-messages-to-functions"></a>İletileri İşlevlere Eşleme
Özellikler penceresini, ileti işleyicileri (MFC kullanıcı arabirimi sınıfları üye işlevlerini) bağlamak, uygulamanızın kaynaklar tarafından üretilen iletileri sağlar. Kullandıkları [MFC ileti eşlemeleri](../../mfc/messages-and-commands-in-the-framework.md) bağlama oluşturmak için.  
  
 Framework sınıflarının birinden türetilen yeni bir sınıf oluşturmak için sınıf görünümü kullandığınızda, bunu otomatik olarak tam ve işlevsel bir yerde üstbilgi (.h) ve uygulama (.cpp) belirttiğiniz sınıf dosyaları.  
  
> [!NOTE]
>  İletileri işlemez yeni bir sınıf eklemek için doğrudan Metin Düzenleyicisi'nde sınıf oluşturun.  
  
### <a name="to-define-or-remove-a-message-handler-using-the-properties-window"></a>Tanımlayın veya Özellikler penceresini kullanarak bir ileti işleyicisini kaldırmak için  
  
1.  Sınıf Görünümü'nde sınıfı'ı tıklatın.  
  
2.  Özellikler penceresinde **iletileri** düğmesi.  
  
    > [!NOTE]
    >  **İletileri** düğmesi, sınıf görünümünde veya kaynak pencereye tıkladığınızda, sınıf adını seçtiğinizde kullanılabilir.  
  
     Projenizin bir ileti için bir işleyici varsa, işleyici adını iletinin yanındaki sağ sütunda görüntülenir.  
  
3.  İleti işleyici yok sahipse, işleyici olarak önerilen adını görüntülemek için Özellikler penceresini sağ sütunda hücreyi tıklatın \<Ekle >*HandlerName*. (Örneğin, `WM_TIMER` ileti işleyicisi öneren \<Ekle >`OnTimer`).  
  
4.  İşlev için saplama kodu eklemek için önerilen adına tıklayın.  
  
5.  Bir ileti işleyicisini düzenlemek için Sınıf Görünümü'nde iletiyi çift tıklatın ve kaynak penceresini kodda düzenleyin.  
  
 Bir ileti işleyicisini kaldırmak için işleyici sağ sütundaki çift tıklatın ve seçin \<sil >*HandlerName*. İşlevin kodunu dışı bırakılmıştır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ileti işleyicisi](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Kod sihirbazlarıyla işlevsellik ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)   
 [Üye işlevi ekleme](../../ide/adding-a-member-function-visual-cpp.md)   
 [Üye değişkeni ekleme](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Sanal işlevi geçersiz kılma](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [İletişim kutusu denetimleri için olay işleyicileri ekleme](../../windows/adding-event-handlers-for-dialog-box-controls.md)   
 [Sınıf yapısında gezinme](../../ide/navigating-the-class-structure-visual-cpp.md)
