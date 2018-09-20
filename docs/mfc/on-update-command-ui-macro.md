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
ms.openlocfilehash: 17111e24a63d527996eadd82c804e5147ad78552
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433471"
---
# <a name="onupdatecommandui-macro"></a>ON_UPDATE_COMMAND_UI Makrosu

Kullanım **özellikleri** komut güncelleştirme işleyici komut hedefi nesnesi bir kullanıcı arabirimi nesnesi bağlanmak penceresi. Otomatik olarak kullanıcı arabirimi nesne kimliği için on_update_command_uı makrosu bağlanmak ve bir işleyici güncelleştirmeyi işleyen nesneyi oluşturmak. Bkz: [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md) daha fazla bilgi için.

Örneğin, programınızın Düzenle menüsü Tümünü Temizle bir komutta güncelleştirmek için kullanın **özellikleri** seçilen sınıfında, bir işlev bildirimi komut güncelleştirme işleyici için bir ileti eşleme girdisi eklemek için pencere olarak adlandırılan `OnUpdateEditClearAll` sınıfında bildirim ve sınıf uygulama dosyasında bir boş işlev şablonu. İşlev prototipi şöyle görünür:

[!code-cpp[NVC_MFCDocView#2](../mfc/codesnippet/cpp/on-update-command-ui-macro_1.h)]

Tüm işleyiciler, işlev gösterildiği gibi **afx_msg** anahtar sözcüğü. Tüm işleyicileri güncelleştirme gibi tek bir bağımsız değişken bir işaretçi alır. bir `CCmdUI` nesne.

## <a name="see-also"></a>Ayrıca Bkz.

[Nasıl yapılır: Kullanıcı Arabirimi Nesnelerini Güncelleştirme](../mfc/how-to-update-user-interface-objects.md)

