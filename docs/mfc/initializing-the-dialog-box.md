---
title: İletişim Kutusunu Başlatma
ms.date: 11/04/2016
helpviewer_keywords:
- initializing dialog boxes [MFC]
- OnInitDialog method [MFC]
- modal dialog boxes [MFC], initializing
- modeless dialog boxes [MFC], initializing
- MFC dialog boxes [MFC], initializing
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
ms.openlocfilehash: 87b3405f1441e730cf5c9ce7fc03d2c7372e55db
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62297105"
---
# <a name="initializing-the-dialog-box"></a>İletişim Kutusunu Başlatma

Sonra iletişim kutusunu ve tüm alt denetimleri oluşturulur ancak yalnızca önce iletişim kutusu (ya da türünde) iletişim nesnesi 's ekranda [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) üye işlevi çağrılır. Kalıcı bir iletişim kutusu için bu sistemdeki `DoModal` çağırın. Kalıcı olmayan iletişim kutusu, `OnInitDialog` aldığında çağrılan `Create` çağrılır. Genellikle geçersiz kılma `OnInitDialog` ilk metin düzenleme kutusu ayarlama gibi iletişim kutusunun denetimleri başlatılamadı. Çağırmalısınız `OnInitDialog` temel sınıfının üye işlevinde `CDialog`, gelen, `OnInitDialog` geçersiz kılar.

İletişim kutusunun arka plan rengini (ve, uygulamanızdaki tüm diğer iletişim kutuları) ayarlamak istiyorsanız, bkz. [iletişim kutusunun arka plan rengini ayarlama](../mfc/setting-the-dialog-boxs-background-color.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bir İletişim Kutusunun Yaşam Döngüsü](../mfc/life-cycle-of-a-dialog-box.md)
