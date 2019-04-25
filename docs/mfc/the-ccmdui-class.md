---
title: CCmdUI Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CCmdUI
helpviewer_keywords:
- updating user interface objects [MFC]
- user interface objects [MFC], updating
- CCmdUI class [MFC], menu updating
- update handlers [MFC]
- toolbars [MFC], updating
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
ms.openlocfilehash: 8e0af0703924d6fae626d3753b8523efe0c56652
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306307"
---
# <a name="the-ccmdui-class"></a>CCmdUI Sınıfı

Bu güncelleştirme komut işleyicisine yönlendirir, framework işleyici işaretçisi geçirir. bir `CCmdUI` nesne (veya bir nesne için bir `CCmdUI`-türetilmiş sınıf). Bu nesne, menü öğesi veya araç çubuğu düğmesini veya komut oluşturulan diğer kullanıcı arabirimi nesnesi temsil eder. Güncelleştirme işleyici üye işlevlerini çağıran `CCmdUI` yapı ile güncelleştirme kullanıcı arabirimi nesnesi için işaretçi. Örneğin, bir güncelleştirme işleyici Tümünü Temizle menü öğesi için şu şekildedir:

[!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]

Bu işleyici çağırır `Enable` menü öğesine erişimi olan bir nesnenin üye işlevi. `Enable` öğenin kullanılabilir hale getirir.

## <a name="see-also"></a>Ayrıca bkz.

[Nasıl yapılır: Kullanıcı arabirimi nesnelerini güncelleştirme](../mfc/how-to-update-user-interface-objects.md)
