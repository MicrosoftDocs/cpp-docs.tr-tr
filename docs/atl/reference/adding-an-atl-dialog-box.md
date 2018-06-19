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
ms.openlocfilehash: e0883b87ce991b08a96b1d10b4acedf8562022a3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361531"
---
# <a name="adding-an-atl-dialog-box"></a>ATL iletişim kutusu ekleme
ATL iletişim projenize eklemek için projenize ATL projesinde veya MFC projesinde ATL desteği içeren olması gerekir. Kullanabileceğiniz [ATL Proje Sihirbazı](../../atl/reference/atl-project-wizard.md) bir ATL uygulama oluşturmak için veya [ATL nesne MFC uygulamanıza eklemek](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) MFC uygulaması için ATL desteği uygulamak için.  
  
 Varsayılan olarak, türetilmiş bir iletişim kutusu ATL iletişim Sihirbazı'nı uygulayan [CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md). Bu sınıf ActiveX ve Windows denetimleri barındırma için destek içerir. Sihirbaz, kodunuzu üretti sonra ActiveX denetimi desteği, yükü istemiyorsanız tüm örneklerini değiştirmek `CAxDialogImpl` ya da ile [CSimpleDialog](../../atl/reference/csimpledialog-class.md) veya [Cdialogımpl](../../atl/reference/cdialogimpl-class.md) temel sınıf olarak .  
  
> [!NOTE]
>  `CSimpleDialog` yalnızca Windows ortak denetimleri destekleyen kalıcı iletişim kutuları oluşturur. `CDialogImpl` ya da kalıcı veya kalıcı olmayan iletişim kutuları oluşturur.  
  
### <a name="to-add-an-atl-dialog-resource-to-your-project"></a>ATL iletişim kutusu kaynağı projenize eklemek için  
  
1.  Kullanarak bir ATL projesi oluşturun [ATL Proje Sihirbazı](../../atl/reference/atl-project-wizard.md).  
  
2.  Gelen [sınıf görünümü](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), proje adına sağ tıklatın ve **Ekle** kısayol menüsünden. Tıklatın **sınıfı ekleme**.  
  
3.  Şablonlar bölmesinde [sınıfı Ekle](../../ide/add-class-dialog-box.md) iletişim kutusu, tıklatın **ATL iletişim**. Tıklatın **açık** görüntülemek için [ATL iletişim Sihirbazı'nı](../../atl/reference/atl-dialog-wizard.md).  
  
 Daha fazla bilgi için bkz: [bir iletişim kutusu uygulama](../../atl/implementing-a-dialog-box.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıf ekleme](../../ide/adding-a-class-visual-cpp.md)   
 [Pencere sınıfları](../../atl/atl-window-classes.md)   
 [İleti eşlemeleri](../../atl/message-maps-atl.md)

