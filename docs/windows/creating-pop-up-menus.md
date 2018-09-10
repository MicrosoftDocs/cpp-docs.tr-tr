---
title: Açılır menüler (C++) oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- context menus [C++], Menu Editor
- pop-up menus [C++], creating
- menus [C++], pop-up
- menus [C++], creating
- shortcut menus [C++], creating
- pop-up menus [C++], displaying
ms.assetid: dff4dddf-2e8d-4c34-b755-90baae426b58
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3fd2fcc5fc8603f265fa2d213325227baecd7f5d
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313774"
---
# <a name="creating-pop-up-menus-c"></a>Açılır menüler oluşturma (C++)

[Açılır menüler](../mfc/menus-mfc.md) görüntü sık kullanılan komutları. Bağlama duyarlı işaretçisi konumunu olabilirler. Uygulamanıza açılır menüleri kullanarak menü oluşturmak ve ardından uygulama koduna bağlanmayı gerektirir.

Menü kaynağı oluşturulduktan sonra uygulama kodunuz menü kaynağı yüklemek ve kullanmak gereken [TrackPopupMenu](/windows/desktop/api/winuser/nf-winuser-trackpopupmenu) menüsünün görünmesi neden olacak. Kullanıcı açılır menüyü dışında tıklayarak kapatıldı veya komutu tıkladıktan sonra bu işlevi döndürür. Kullanıcı komut seçerse, tanıtıcı geçirildi penceresine komut ileti gönderilir.

### <a name="to-create-a-pop-up-menu"></a>Açılır menü oluşturmak için

1. [Menü oluşturmak](../windows/creating-a-menu.md) boş bir başlığa sahip (sağlamayan bir **açıklamalı alt yazı**).

2. [Yeni menüsüne bir menü komutu eklemek](../windows/adding-commands-to-a-menu.md). Boş Menü başlığının altında ilk menü Komut çubuğuna Taşı (geçici açıklamalı alt yazı yazan `Type Here`). Tür a **açıklamalı alt yazı** ve diğer bilgiler.

   Diğer bir menü komutları açılır menüde için bu işlemi yineleyin.

3. Menü kaynağı kaydedin.

   > [!TIP]
   > Açılır menü görüntüleme ile ilgili daha fazla bilgi için bkz: [menüyü açılır menü olarak görüntüleme](../windows/viewing-a-menu-as-a-pop-up-menu.md).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Uygulamanıza Açılır Menü Bağlantısı Yapma](../windows/connecting-a-pop-up-menu-to-your-application.md)  
[Menü Düzenleyicisi](../windows/menu-editor.md)