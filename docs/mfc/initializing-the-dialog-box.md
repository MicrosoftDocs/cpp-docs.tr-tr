---
title: Iletişim kutusu başlatılıyor
ms.date: 11/04/2016
helpviewer_keywords:
- initializing dialog boxes [MFC]
- OnInitDialog method [MFC]
- modal dialog boxes [MFC], initializing
- modeless dialog boxes [MFC], initializing
- MFC dialog boxes [MFC], initializing
ms.assetid: 968142f5-19f9-4b34-a1d4-8e6412d4379b
ms.openlocfilehash: 14cdf94bef79f254b4aaa2c1c0dfba6c88b7498b
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685626"
---
# <a name="initializing-the-dialog-box"></a>Iletişim kutusu başlatılıyor

İletişim kutusu ve tüm denetimleri oluşturulduktan sonra, ancak ekranda iletişim kutusu (herhangi bir türden) görüntülenmeden önce, iletişim kutusu nesnesinin [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) üye işlevi çağırılır. Kalıcı bir iletişim kutusu için, bu `DoModal` çağrısı sırasında gerçekleşir. Kalıcı olmayan bir iletişim kutusu için, `Create` çağrıldığında `OnInitDialog` çağrılır. Bir düzenleme kutusunun başlangıç metnini ayarlamak gibi, iletişim kutusunun denetimlerini başlatmak için genellikle `OnInitDialog` ' ı geçersiz kılabilirsiniz. @No__t-2 geçersiz kılmanızda, `CDialog` temel sınıfının `OnInitDialog` üye işlevini çağırmanız gerekir.

İletişim kutusunun arka plan rengini (ve uygulamanızdaki diğer tüm iletişim kutularından) ayarlamak istiyorsanız, bkz. [Iletişim kutusunun arka plan rengini ayarlama](../mfc/setting-the-dialog-boxs-background-color.md).

## <a name="see-also"></a>Ayrıca bkz.

[MFC 'de Iletişim kutularıyla çalışma](../mfc/life-cycle-of-a-dialog-box.md)
