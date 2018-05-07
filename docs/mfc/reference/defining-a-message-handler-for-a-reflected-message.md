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
ms.openlocfilehash: 3ed941816824c77f14a3364b06af0b3da171ee8f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="defining-a-message-handler-for-a-reflected-message"></a>Yansımış Bir İleti İçin İleti İşleyicisi Tanımlama
Yeni bir MFC denetim sınıf oluşturduktan sonra ileti işleyicileri için tanımlayabilirsiniz. Yansıtılan ileti işleyicileri ileti üst tarafından alınmadan önce kendi iletileri işlemek denetim sınıfınıza izin verir. MFC kullanabilirsiniz [CWnd::SendMessage](../../mfc/reference/cwnd-class.md#sendmessage) üst penceresine, denetimden iletileri göndermeye işlevi.  
  
 (Bunu sahip çizilmiş) yapmak için üst pencere güvenmek yerine kendisini yeniden çizer bir liste kutusu gibi olabilir, bu işlev ile oluşturun. Yansımış iletiler hakkında daha fazla bilgi için bkz: [yansımış iletileri işleme](../../mfc/handling-reflected-messages.md).  
  
 Oluşturmak için bir [ActiveX denetimi](../../mfc/activex-controls-on-the-internet.md) aynı işlevselliğe sahip bir proje ActiveX denetimi için oluşturmanız gerekir.  
  
> [!NOTE]
>  Yansımış bir ileti eklenemiyor (OCM_*ileti*) için bir ActiveX denetimi Özellikler penceresini kullanarak aşağıda açıklandığı gibi. Bu iletiler el ile eklemeniz gerekir.  
  
### <a name="to-define-a-message-handler-for-a-reflected-message-from-the-properties-window"></a>Özellikler penceresinde yansımış bir ileti için ileti işleyicisi tanımlamak için  
  
1.  Bir liste gibi bir denetim, rebar denetimi, bir araç veya bir ağaç denetimi MFC projenize ekleyin.  
  
2.  Sınıf Görünümü'nde denetim sınıfınıza adına tıklayın.  
  
3.  İçinde [Özellikler penceresini](/visualstudio/ide/reference/properties-window), denetim sınıf adı görünür **sınıf adı** listesi.  
  
4.  Tıklatın **iletileri** denetimine eklemek kullanılabilir Windows iletilerini görüntülemek için düğmeyi.  
  
5.  Başlık görene kadar Özellikleri penceresinde iletilerin listesini aşağı kaydırın **Reflected**. Alternatif olarak, **kategorileri** düğmesini ve görmek için görünümü daraltma **Reflected** başlığı.  
  
6.  Bir işleyici tanımlamak istediğiniz yansıtılan iletiyi seçin. Yansımış iletiler eşittir işareti (=) ile işaretlenir.  
  
7.  İşleyici olarak önerilen adını görüntülemek için özellikleri penceresinde sağ sütunda bir hücreyi tıklatın \<Ekle >*HandlerName*. (Örneğin, **WM_CTLCOLOR =** ileti işleyicisi öneren \<Ekle >**CtlColor**).  
  
8.  Kabul etmek için önerilen adına tıklayın. İşleyici projenize eklenir.  
  
     Eklediğiniz ileti işleyicisi adları yansımış iletiler penceresinin sağ sütunda görüntülenir.  
  
9. Düzenleme veya silme bir ileti işleyicisini için 4 ile 7 arasındaki adımları yineleyin. Düzenlemek veya silmek ve uygun göreve tıklayın işleyici adını içeren bir hücreyi tıklatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletileri işlevlere eşleme](../../mfc/reference/mapping-messages-to-functions.md)   
 [Kod sihirbazlarıyla işlevsellik ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)   
 [Üye işlevi ekleme](../../ide/adding-a-member-function-visual-cpp.md)   
 [Üye değişkeni ekleme](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Sanal işlevi geçersiz kılma](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC ileti işleyicisi](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Sınıf yapısında gezinme](../../ide/navigating-the-class-structure-visual-cpp.md)
