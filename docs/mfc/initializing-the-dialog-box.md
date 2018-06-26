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
ms.openlocfilehash: 1c4bc280c57998b23082f11f4ebe42b660177d3c
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929627"
---
# <a name="initializing-the-dialog-box"></a>İletişim Kutusunu Başlatma
Sonra iletişim kutusunu ve tüm alt denetimleri oluşturulur ancak hemen önce iletişim kutusu (her iki türdeki) iletişim nesnesi 's ekranda [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) üye işlevi çağrılır. Modal bir iletişim kutusu için bu sistemdeki `DoModal` çağırın. Kalıcı olmayan iletişim kutusu için `OnInitDialog` aldığında çağrılan `Create` olarak adlandırılır. Genellikle geçersiz kılma `OnInitDialog` düzenleme kutusu ilk metnin ayarlama gibi iletişim kutusunun denetimleri başlatılamadı. Çağırmalısınız `OnInitDialog` üye işlevi temel sınıfın `CDialog`, gelen, `OnInitDialog` geçersiz kılar.  
  
 İletişim kutusunun arka plan rengini (ve uygulamanızdaki diğer tüm iletişim kutularını,) ayarlamak istiyorsanız, bkz: [iletişim kutusunun arka plan rengini ayarlama](../mfc/setting-the-dialog-boxs-background-color.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)

