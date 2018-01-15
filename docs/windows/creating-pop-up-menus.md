---
title: "Açılır menüler oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- context menus, Menu Editor
- pop-up menus, creating
- menus, pop-up
- menus, creating
- shortcut menus, creating
- pop-up menus, displaying
ms.assetid: dff4dddf-2e8d-4c34-b755-90baae426b58
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6185f52eeaf56ac0d31cb8e9f22715db36514725
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-pop-up-menus"></a>Açılır Menüler Oluşturma
[Açılır menüler](../mfc/menus-mfc.md) görüntü sık kullanılan komutlar. Bağlama duyarlı işaretçinin konuma olabilirler. Açılır menüler uygulamanızda kullanarak menü oluşturma ve uygulama kodu bağlanmayı gerektirir.  
  
 Menü kaynağı oluşturduktan sonra uygulama kodunuz menüsü kaynak yüklemek ve kullanmak gerek duyduğu [TrackPopupMenu](http://msdn.microsoft.com/library/windows/desktop/ms648002) menüsünün görünmesini neden olacak. Kullanıcı açılır menüyü dışında tıklayarak kapatıldığında veya bir komut tıklamıştır sonra bu işlevi döndürür. Kullanıcı bir komut seçerse, tanıtıcı geçirildi penceresine komutu ileti gönderilir.  
  
### <a name="to-create-a-pop-up-menu"></a>Açılır menü oluşturmak için  
  
1.  [Menü oluşturmak](../windows/creating-a-menu.md) boş bir başlıkla (sağlamıyorsa bir **resim yazısı**).  
  
2.  [Menü komutu için yeni menü ekleme](../windows/adding-commands-to-a-menu.md). (Geçici resim yazısı buraya türü yazan) ilk menü komutu için boş menü başlığı altına taşıyın. Tür a **resim yazısı** ve diğer bilgileri.  
  
     Açılır menüde diğer menü komutları için bu işlemi yineleyin.  
  
3.  Menü kaynağı kaydedin.  
  
    > [!TIP]
    >  Açılır menüyü görüntüleme hakkında daha fazla bilgi için bkz: [menü açılır menü olarak görüntüleme](../windows/viewing-a-menu-as-a-pop-up-menu.md).  
  

  
 **Gereksinimler**  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uygulamanıza açılır menü bağlanma](../windows/connecting-a-pop-up-menu-to-your-application.md)   
 [Menü Düzenleyicisi](../windows/menu-editor.md)