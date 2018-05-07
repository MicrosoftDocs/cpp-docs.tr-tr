---
title: İletişim kutusunu başlatma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- initializing dialog boxes [MFC]
- OnInitDialog method [MFC]
- modal dialog boxes [MFC], initializing
- modeless dialog boxes [MFC], initializing
- MFC dialog boxes [MFC], initializing
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7918180a437687eded090b3d014e4affe38fe8f9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="initializing-the-dialog-box"></a>İletişim Kutusunu Başlatma
Sonra iletişim kutusunu ve tüm alt denetimleri oluşturulur ancak hemen önce iletişim kutusu (her iki türdeki) iletişim nesnesi 's ekranda [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) üye işlevi çağrılır. Modal bir iletişim kutusu için bu sistemdeki `DoModal` çağırın. Kalıcı olmayan iletişim kutusu için `OnInitDialog` aldığında çağrılan **oluşturma** olarak adlandırılır. Genellikle geçersiz kılma `OnInitDialog` düzenleme kutusu ilk metnin ayarlama gibi iletişim kutusunun denetimleri başlatılamadı. Çağırmalısınız `OnInitDialog` üye işlevi temel sınıfın `CDialog`, gelen, `OnInitDialog` geçersiz kılar.  
  
 İletişim kutusunun arka plan rengini (ve uygulamanızdaki diğer tüm iletişim kutularını,) ayarlamak istiyorsanız, bkz: [iletişim kutusunun arka plan rengini ayarlama](../mfc/setting-the-dialog-boxs-background-color.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

