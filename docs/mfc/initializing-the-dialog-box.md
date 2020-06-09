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
ms.openlocfilehash: 1f8f8f7e40b1c873c4428542c628d02e250f14b4
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626333"
---
# <a name="initializing-the-dialog-box"></a>İletişim Kutusunu Başlatma

İletişim kutusu ve tüm denetimleri oluşturulduktan sonra, ancak ekranda iletişim kutusu (herhangi bir türden) görüntülenmeden önce, iletişim kutusu nesnesinin [OnInitDialog](reference/cdialog-class.md#oninitdialog) üye işlevi çağırılır. Kalıcı iletişim kutusu için bu çağrı sırasında oluşur `DoModal` . Kalıcı olmayan bir iletişim kutusu için `OnInitDialog` `Create` çağrıldığında çağrılır. Genellikle `OnInitDialog` , bir düzenleme kutusunun ilk metnini ayarlama gibi iletişim kutusunun denetimlerini başlatmak için geçersiz kılmalısınız. `OnInitDialog` `CDialog` Geçersiz kılmanızda, taban sınıfının üye işlevini çağırmanız gerekir `OnInitDialog` .

İletişim kutusunun arka plan rengini (ve uygulamanızdaki diğer tüm iletişim kutularından) ayarlamak istiyorsanız, bkz. [Iletişim kutusunun arka plan rengini ayarlama](setting-the-dialog-boxs-background-color.md).

## <a name="see-also"></a>Ayrıca bkz.

[MFC’de İletişim Kutularıyla çalışma](life-cycle-of-a-dialog-box.md)
