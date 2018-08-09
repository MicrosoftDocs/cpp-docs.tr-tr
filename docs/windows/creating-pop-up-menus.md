---
title: Açılır menüler oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- context menus, Menu Editor
- pop-up menus, creating
- menus, pop-up
- menus, creating
- shortcut menus, creating
- pop-up menus, displaying
ms.assetid: dff4dddf-2e8d-4c34-b755-90baae426b58
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4e58951fe214efda0002f3ea864e67d0ea35423c
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39648080"
---
# <a name="creating-pop-up-menus"></a>Açılır Menüler Oluşturma
[Açılır menüler](../mfc/menus-mfc.md) görüntü sık kullanılan komutları. Bağlama duyarlı işaretçisi konumunu olabilirler. Uygulamanıza açılır menüleri kullanarak menü oluşturmak ve ardından uygulama koduna bağlanmayı gerektirir.  
  
 Menü kaynağı oluşturulduktan sonra uygulama kodunuz menü kaynağı yüklemek ve kullanmak gereken [TrackPopupMenu](http://msdn.microsoft.com/library/windows/desktop/ms648002) menüsünün görünmesi neden olacak. Kullanıcı açılır menüyü dışında tıklayarak kapatıldı veya komutu tıkladıktan sonra bu işlevi döndürür. Kullanıcı komut seçerse, tanıtıcı geçirildi penceresine komut ileti gönderilir.  
  
### <a name="to-create-a-pop-up-menu"></a>Açılır menü oluşturmak için  
  
1.  [Menü oluşturmak](../windows/creating-a-menu.md) boş bir başlığa sahip (sağlamayan bir **açıklamalı alt yazı**).  
  
2.  [Yeni menüsüne bir menü komutu eklemek](../windows/adding-commands-to-a-menu.md). Boş Menü başlığının altında ilk menü Komut çubuğuna Taşı (geçici açıklamalı alt yazı yazan `Type Here`). Tür a **açıklamalı alt yazı** ve diğer bilgiler.  
  
     Diğer bir menü komutları açılır menüde için bu işlemi yineleyin.  
  
3.  Menü kaynağı kaydedin.  
  
    > [!TIP]
    >  Açılır menü görüntüleme ile ilgili daha fazla bilgi için bkz: [menüyü açılır menü olarak görüntüleme](../windows/viewing-a-menu-as-a-pop-up-menu.md).  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uygulamanıza açılır menü bağlantısı](../windows/connecting-a-pop-up-menu-to-your-application.md)   
 [Menü Düzenleyicisi](../windows/menu-editor.md)