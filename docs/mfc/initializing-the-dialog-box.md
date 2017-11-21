---
title: "İletişim kutusunu başlatma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- initializing dialog boxes [MFC]
- OnInitDialog method [MFC]
- modal dialog boxes [MFC], initializing
- modeless dialog boxes [MFC], initializing
- MFC dialog boxes [MFC], initializing
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6568c9bd9002df880a5501dd68e7050a4dc14706
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="initializing-the-dialog-box"></a>İletişim Kutusunu Başlatma
Sonra iletişim kutusunu ve tüm alt denetimleri oluşturulur ancak hemen önce iletişim kutusu (her iki türdeki) iletişim nesnesi 's ekranda [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) üye işlevi çağrılır. Modal bir iletişim kutusu için bu sistemdeki `DoModal` çağırın. Kalıcı olmayan iletişim kutusu için `OnInitDialog` aldığında çağrılan **oluşturma** olarak adlandırılır. Genellikle geçersiz kılma `OnInitDialog` düzenleme kutusu ilk metnin ayarlama gibi iletişim kutusunun denetimleri başlatılamadı. Çağırmalısınız `OnInitDialog` üye işlevi temel sınıfın `CDialog`, gelen, `OnInitDialog` geçersiz kılar.  
  
 İletişim kutusunun arka plan rengini (ve uygulamanızdaki diğer tüm iletişim kutularını,) ayarlamak istiyorsanız, bkz: [iletişim kutusunun arka plan rengini ayarlama](../mfc/setting-the-dialog-boxs-background-color.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutusunun yaşam döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

