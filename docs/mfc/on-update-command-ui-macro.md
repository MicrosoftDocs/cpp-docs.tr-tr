---
title: "On_update_command_uı makrosu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ON_UPDATE_COMMAND_UI
dev_langs: C++
helpviewer_keywords:
- ON_UPDATE_COMMAND_UI macro [MFC]
- update handlers [MFC]
- command-handler macros
- updating user-interface objects [MFC]
ms.assetid: 3e72b50f-4119-4c82-81cf-6e09b132de05
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 64b9c77d8c851364790d61e7844b46f25880168c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="onupdatecommandui-macro"></a>ON_UPDATE_COMMAND_UI Makrosu
Kullanım **özellikleri** komutu-hedef nesne komutu güncelleştirme işleyici için bir kullanıcı arabirimi nesnesi bağlanmak için penceresi. Kullanıcı arabirimi nesnesinin kimliği için otomatik olarak bağlanacak `ON_UPDATE_COMMAND_UI` makrosu ve güncelleştirme işleyecek nesnesinde bir işleyici oluşturun. Bkz: [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md) daha fazla bilgi için.  
  
 Örneğin, programınızın Düzenle menüsünde bir Tümünü Temizle komutu güncelleştirmek için kullanın **özellikleri** seçilen sınıfı, bir işlev bildirimi komutu güncelleştirme işleyici için bir ileti eşleme girdisi eklemek için pencere olarak adlandırılan `OnUpdateEditClearAll` sınıfında bildirim ve sınıfın uygulama dosya boş işlevi şablonunda. İşlev prototipi şöyle görünür:  
  
 [!code-cpp[NVC_MFCDocView#2](../mfc/codesnippet/cpp/on-update-command-ui-macro_1.h)]  
  
 Tüm işleyiciler, işlevi gösterildiği gibi **afx_msg** anahtar sözcüğü. Tüm işleyicileri güncelleştirme gibi tek bir bağımsız değişken için bir işaretçi geçen bir `CCmdUI` nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: kullanıcı arabirimi nesnelerini güncelleştirme](../mfc/how-to-update-user-interface-objects.md)

