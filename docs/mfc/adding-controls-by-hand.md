---
title: El ile denetim ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows common controls [MFC], adding
- dialog box controls [MFC], adding to dialog boxes
- controlling input focus
- input focus control
- focus, controlling input [MFC]
- controls [MFC], adding to dialog boxes
- common controls [MFC], adding
ms.assetid: bc843e59-0c51-4b5b-8bf2-343f716469d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c39f2d7803630aaaef6e803e90bf332c74937a71
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930621"
---
# <a name="adding-controls-by-hand"></a>El İle Denetim Ekleme
Seçebilir ya da [ile iletişim kutusu Düzenleyicisi için bir iletişim kutusu denetimleri ekleme](../mfc/using-the-dialog-editor-to-add-controls.md) veya bunları kendiniz koduyla ekleyin.  
  
 Bir denetim nesnesi kendiniz oluşturmak için genellikle bir C++ iletişim C++ denetim nesnesi veya çerçeve pencere nesnesi katıştırır. Diğer birçok nesne gibi Framework'te, iki aşamalı yapımı denetimleri gerektirir. Denetimin çağırmalıdır **oluşturma** üst iletişim kutusu veya çerçeve penceresi oluşturma bir parçası olarak üye işlevi. İletişim kutuları için bu genellikle içinde yapılır [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)ve çerçeve pencereleri içinde [OnCreate](../mfc/reference/cwnd-class.md#oncreate).  
  
 Aşağıdaki örnek, nasıl bildirdiğiniz gösterir bir `CEdit` nesne türetilmiş iletişim kutusu sınıfı sınıfı bildiriminde ve ardından arama `Create` üye işlevinde `OnInitDialog`. Çünkü `CEdit` nesne katıştırılmış nesne olarak bildirilen, iletişim nesnesi oluşturulur, ancak bunu hala kendi ile başlatılmalıdır otomatik olarak oluşturulur `Create` üye işlevi.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#1](../mfc/codesnippet/cpp/adding-controls-by-hand_1.h)]  
  
 Aşağıdaki `OnInitDialog` işlevi bir dikdörtgen ayarlar daha sonra çağırır `Create` Windows düzenleme denetimi oluşturmak ve başlatılmamış eklemek için `CEdit` nesnesi.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#2](../mfc/codesnippet/cpp/adding-controls-by-hand_2.cpp)]  
  
 Nesne Düzenle oluşturduktan sonra ayrıca giriş odağı denetimi çağırarak ayarlayabilirsiniz `SetFocus` üye işlevi. Son olarak, 0'dan iade `OnInitDialog` odağı ayarladığınız göstermek için. Sıfır olmayan bir değer döndürürse, iletişim Yöneticisi odağı iletişim öğesi listesindeki ilk denetim öğesini ayarlar. Çoğu durumda, denetimleri ile iletişim kutusu Düzenleyicisi iletişim kutularına ekleme istersiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Denetimleri yapma ve kullanma](../mfc/making-and-using-controls.md)   
 [Denetimleri](../mfc/controls-mfc.md)   
 [CDialog::OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)

