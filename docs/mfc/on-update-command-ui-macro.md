---
title: On_update_command_uı makrosu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- ON_UPDATE_COMMAND_UI
dev_langs:
- C++
helpviewer_keywords:
- ON_UPDATE_COMMAND_UI macro [MFC]
- update handlers [MFC]
- command-handler macros
- updating user-interface objects [MFC]
ms.assetid: 3e72b50f-4119-4c82-81cf-6e09b132de05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43caffe53be180221b4145a03df7cfc41c31828e
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928644"
---
# <a name="onupdatecommandui-macro"></a>ON_UPDATE_COMMAND_UI Makrosu
Kullanım **özellikleri** komutu-hedef nesne komutu güncelleştirme işleyici için bir kullanıcı arabirimi nesnesi bağlanmak için penceresi. Bu otomatik olarak kullanıcı arabirimi nesnesinin kimliği on_update_command_uı makrosu bağlama ve bir işleyici güncelleştirmeyi işleyecek nesne oluşturma. Bkz: [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md) daha fazla bilgi için.  
  
 Örneğin, programınızın Düzenle menüsünde bir Tümünü Temizle komutu güncelleştirmek için kullanın **özellikleri** seçilen sınıfı, bir işlev bildirimi komutu güncelleştirme işleyici için bir ileti eşleme girdisi eklemek için pencere olarak adlandırılan `OnUpdateEditClearAll` sınıfında bildirim ve sınıfın uygulama dosya boş işlevi şablonunda. İşlev prototipi şöyle görünür:  
  
 [!code-cpp[NVC_MFCDocView#2](../mfc/codesnippet/cpp/on-update-command-ui-macro_1.h)]  
  
 Tüm işleyiciler, işlevi gösterildiği gibi **afx_msg** anahtar sözcüğü. Tüm işleyicileri güncelleştirme gibi tek bir bağımsız değişken için bir işaretçi geçen bir `CCmdUI` nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Kullanıcı Arabirimi Nesnelerini Güncelleştirme](../mfc/how-to-update-user-interface-objects.md)

