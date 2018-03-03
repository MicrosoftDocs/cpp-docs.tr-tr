---
title: "İletişim kutusunu başlatma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- initializing dialog boxes [MFC]
- OnInitDialog method [MFC]
- modal dialog boxes [MFC], initializing
- modeless dialog boxes [MFC], initializing
- MFC dialog boxes [MFC], initializing
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2af05011e8f2af2993edf3ea2f82716137b17857
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="initializing-the-dialog-box"></a>İletişim Kutusunu Başlatma
Sonra iletişim kutusunu ve tüm alt denetimleri oluşturulur ancak hemen önce iletişim kutusu (her iki türdeki) iletişim nesnesi 's ekranda [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) üye işlevi çağrılır. Modal bir iletişim kutusu için bu sistemdeki `DoModal` çağırın. Kalıcı olmayan iletişim kutusu için `OnInitDialog` aldığında çağrılan **oluşturma** olarak adlandırılır. Genellikle geçersiz kılma `OnInitDialog` düzenleme kutusu ilk metnin ayarlama gibi iletişim kutusunun denetimleri başlatılamadı. Çağırmalısınız `OnInitDialog` üye işlevi temel sınıfın `CDialog`, gelen, `OnInitDialog` geçersiz kılar.  
  
 İletişim kutusunun arka plan rengini (ve uygulamanızdaki diğer tüm iletişim kutularını,) ayarlamak istiyorsanız, bkz: [iletişim kutusunun arka plan rengini ayarlama](../mfc/setting-the-dialog-boxs-background-color.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

