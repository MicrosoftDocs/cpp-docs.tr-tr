---
description: 'Hakkında daha fazla bilgi edinin: Iletişim kutusu başlatılıyor'
title: İletişim Kutusunu Başlatma
ms.date: 11/04/2016
helpviewer_keywords:
- initializing dialog boxes [MFC]
- OnInitDialog method [MFC]
- modal dialog boxes [MFC], initializing
- modeless dialog boxes [MFC], initializing
- MFC dialog boxes [MFC], initializing
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
ms.openlocfilehash: 317098a8c0cc745bbd4c94b9ed02401774cb0df9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197627"
---
# <a name="initializing-the-dialog-box"></a>İletişim Kutusunu Başlatma

İletişim kutusu ve tüm denetimleri oluşturulduktan sonra, ancak ekranda iletişim kutusu (herhangi bir türden) görüntülenmeden önce, iletişim kutusu nesnesinin [OnInitDialog](reference/cdialog-class.md#oninitdialog) üye işlevi çağırılır. Kalıcı iletişim kutusu için bu çağrı sırasında oluşur `DoModal` . Kalıcı olmayan bir iletişim kutusu için `OnInitDialog` `Create` çağrıldığında çağrılır. Genellikle `OnInitDialog` , bir düzenleme kutusunun ilk metnini ayarlama gibi iletişim kutusunun denetimlerini başlatmak için geçersiz kılmalısınız. `OnInitDialog` `CDialog` Geçersiz kılmanızda, taban sınıfının üye işlevini çağırmanız gerekir `OnInitDialog` .

İletişim kutusunun arka plan rengini (ve uygulamanızdaki diğer tüm iletişim kutularından) ayarlamak istiyorsanız, bkz. [Iletişim kutusunun arka plan rengini ayarlama](setting-the-dialog-boxs-background-color.md).

## <a name="see-also"></a>Ayrıca bkz.

[MFC’de İletişim Kutularıyla çalışma](life-cycle-of-a-dialog-box.md)
