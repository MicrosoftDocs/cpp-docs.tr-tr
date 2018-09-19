---
title: ATL iletişim kutusu ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding dialog resources
- MFC dialog boxes, ATL dialogs
- dialog boxes, ATL
ms.assetid: 152a378f-7b24-4f66-aeba-c740973f03a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 512f791b3db513c2a143bda84a8dc2677b341544
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106057"
---
# <a name="adding-an-atl-dialog-box"></a>ATL iletişim kutusu ekleme

ATL iletişim projenize eklemek için projenizin bir ATL projesi ya da MFC projesinde ATL desteği içerir olması gerekir. Kullanabileceğiniz [ATL projesi Sihirbazı](../../atl/reference/atl-project-wizard.md) bir ATL uygulama oluşturmak için veya [MFC uygulamanıza bir ATL nesnesi eklemek](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) bir MFC uygulaması için ATL desteği uygulamak için.

Varsayılan olarak, ATL iletişim kutusu Sihirbazı türetilen bir iletişim kutusu uygulayan [Caxdialogımpl](../../atl/reference/caxdialogimpl-class.md). Bu sınıf, ActiveX ve Windows denetimleri barındırma desteği içerir. Sihirbaz, kod üretti sonra ActiveX denetimi desteği, yükü istemiyorsanız tüm örneklerini değiştirin `CAxDialogImpl` ya da ile [CSimpleDialog](../../atl/reference/csimpledialog-class.md) veya [Cdialogımpl](../../atl/reference/cdialogimpl-class.md) , temel sınıf olarak .

> [!NOTE]
>  `CSimpleDialog` yalnızca Windows ortak denetimleri destekleyen kalıcı iletişim kutuları oluşturur. `CDialogImpl` ya da kalıcı veya kısıtlayıcı olmayan iletişim kutuları oluşturur.

### <a name="to-add-an-atl-dialog-resource-to-your-project"></a>Bir ATL iletişim kutusu kaynağı projenize eklemek için

1. Bir ATL projesi oluşturun [ATL projesi Sihirbazı](../../atl/reference/atl-project-wizard.md).

2. Gelen [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code), proje adını sağ tıklatıp **Ekle** kısayol menüsünden. Tıklayın **sınıfı Ekle**.

3. Şablonlar bölmesinde [sınıfı Ekle](../../ide/add-class-dialog-box.md) iletişim kutusu, tıklayın **ATL iletişim kutusu**. Tıklayın **açık** görüntülenecek [ATL iletişim kutusu Sihirbazı](../../atl/reference/atl-dialog-wizard.md).

Daha fazla bilgi için [iletişim kutusu uygulama](../../atl/implementing-a-dialog-box.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)<br/>
[Pencere sınıfları](../../atl/atl-window-classes.md)<br/>
[İleti eşlemeleri](../../atl/message-maps-atl.md)

