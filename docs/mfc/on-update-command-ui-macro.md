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
ms.workload: cplusplus
ms.openlocfilehash: 3de873cf70bafa77d7c8f4b05c70ce211b2c2258
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="onupdatecommandui-macro"></a>ON_UPDATE_COMMAND_UI Makrosu
Kullanım **özellikleri** komutu-hedef nesne komutu güncelleştirme işleyici için bir kullanıcı arabirimi nesnesi bağlanmak için penceresi. Kullanıcı arabirimi nesnesinin kimliği için otomatik olarak bağlanacak `ON_UPDATE_COMMAND_UI` makrosu ve güncelleştirme işleyecek nesnesinde bir işleyici oluşturun. Bkz: [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md) daha fazla bilgi için.  
  
 Örneğin, programınızın Düzenle menüsünde bir Tümünü Temizle komutu güncelleştirmek için kullanın **özellikleri** seçilen sınıfı, bir işlev bildirimi komutu güncelleştirme işleyici için bir ileti eşleme girdisi eklemek için pencere olarak adlandırılan `OnUpdateEditClearAll` sınıfında bildirim ve sınıfın uygulama dosya boş işlevi şablonunda. İşlev prototipi şöyle görünür:  
  
 [!code-cpp[NVC_MFCDocView#2](../mfc/codesnippet/cpp/on-update-command-ui-macro_1.h)]  
  
 Tüm işleyiciler, işlevi gösterildiği gibi **afx_msg** anahtar sözcüğü. Tüm işleyicileri güncelleştirme gibi tek bir bağımsız değişken için bir işaretçi geçen bir `CCmdUI` nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Kullanıcı Arabirimi Nesnelerini Güncelleştirme](../mfc/how-to-update-user-interface-objects.md)

