---
title: Bir iletişim kutusunda ortak denetimleri kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- common controls [MFC], in dialog boxes
- dialog box controls [MFC], common controls
- Windows common controls [MFC], in dialog boxes
ms.assetid: 17713caf-09f8-484a-bf54-5f48bf09cce9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c848cfa74363d871720f9ca269b114687aad9ecf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382697"
---
# <a name="using-common-controls-in-a-dialog-box"></a>İletişim Kutusunda Ortak Denetimleri Kullanma
Windows ortak denetimleri kullanılabilir [iletişim kutuları](../mfc/dialog-boxes.md), form görünümleri, kayıt görünümleri ve bir iletişim şablonunu temel alan başka bir pencere. Aşağıdaki yordam, bazı küçük değişikliklerle de formlar için çalışır.  
  
## <a name="procedures"></a>Yordamlar  
  
#### <a name="to-use-a-common-control-in-a-dialog-box"></a>Bir iletişim kutusunda bir ortak denetimi kullanmak için  
  
1.  İletişim şablonu denetimi yerleştirin [iletişim kutusu Düzenleyicisi'ni kullanarak](../mfc/using-the-dialog-editor-to-add-controls.md).  
  
2.  İletişim kutusu sınıfı denetimini temsil eden bir üye değişkeni ekleyin. İçinde **üye değişkeni ekleme** iletişim kutusu, onay **denetim değişkeni** ve emin **denetim** için seçilen **kategori**.  
  
3.  Bu yaygın bir denetim programı için giriş sağlama, ek üyesi bildirin olanlar işlemek için iletişim kutusu sınıfında variable(s) giriş değerleri.  
  
    > [!NOTE]
    >  Sınıf Görünümü'nde bağlam menüsünü kullanarak bu üye değişkenleri ekleyebilirsiniz (bkz [üye değişkeni ekleme](../ide/adding-a-member-variable-visual-cpp.md)).  
  
4.  İçinde [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) iletişim sınıfınızı için yaygın bir denetim için ilk koşulları ayarlayın. Üye işlevleri, önceki adımda oluşturduğunuz üye değişkeni kullanarak, ilk değer ve diğer ayarları ayarlamak için kullanın. Ayrıntılar için denetimleri aşağıdaki açıklamalarını ayarlarını bakın.  
  
     Aynı zamanda [iletişim kutusu veri değişimi](../mfc/dialog-data-exchange-and-validation.md) bir iletişim kutusu denetimleri başlatılamadı (DDX).  
  
5.  İletişim kutusu denetimleri için işleyiciler üye değişkeni denetimi yönetmek için kullanın. Ayrıntılar için denetimleri aşağıdaki açıklamalarını yöntemlere bakın.  
  
    > [!NOTE]
    >  İletişim kutusu yalnızca mevcut olduğu sürece üye değişkeni yer alır. İletişim kutusu kapatıldıktan sonra denetim için giriş değerleri sorgu mümkün olmaz. Bir ortak denetimi giriş değerleri çalışmak için geçersiz kılma `OnOK` iletişim sınıfınızda. Geçersiz kılma, denetim giriş değerleri için sorgu ve bu değerler iletişim sınıfının üye değişkenlerine depolayın.  
  
    > [!NOTE]
    >  İletişim kutusu veri değişimi, ayarlama veya bir iletişim kutusu denetimleri değerleri almak için de kullanabilirsiniz.  
  
## <a name="remarks"></a>Açıklamalar  
 Bazı ortak bir iletişim kutusu denetimlerine ekleme iletişim kutusu artık işlevi neden olur. Başvurmak [bir iletişim kutusu denetimlerine ekleme neden olan iletişim kutusu artık işleve](../windows/adding-controls-to-a-dialog-causes-the-dialog-to-no-longer-function.md) bu durum işleme hakkında daha fazla bilgi.  
  
## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz  
  
-   [Denetimleri bir Ekle iletişim kutusu için el ile yerine ile iletişim kutusu Düzenleyicisi](../mfc/adding-controls-by-hand.md)  
  
-   [My denetim standart Windows ortak denetimleri birinden türetilen](../mfc/deriving-controls-from-a-standard-control.md)  
  
-   [Bir ortak denetimi alt pencere olarak kullanma](../mfc/using-a-common-control-as-a-child-window.md)  
  
-   [Bir denetiminden bildirim iletilerini alma](../mfc/receiving-notification-from-common-controls.md)  
  
-   [İletişim kutusu veri değişimi (DDX) kullanın](../mfc/dialog-data-exchange-and-validation.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetimleri yapma ve kullanma](../mfc/making-and-using-controls.md)   
 [Denetimler](../mfc/controls-mfc.md)

