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
ms.openlocfilehash: 47ef359f71d9dd30f2ba1ff1c4cf504bccd33ffd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667954"
---
# <a name="the-ccmdui-class"></a>CCmdUI Sınıfı

Bu güncelleştirme komut işleyicisine yönlendirir, framework işleyici işaretçisi geçirir. bir `CCmdUI` nesne (veya bir nesne için bir `CCmdUI`-türetilmiş sınıf). Bu nesne, menü öğesi veya araç çubuğu düğmesini veya komut oluşturulan diğer kullanıcı arabirimi nesnesi temsil eder. Güncelleştirme işleyici üye işlevlerini çağıran `CCmdUI` yapı ile güncelleştirme kullanıcı arabirimi nesnesi için işaretçi. Örneğin, bir güncelleştirme işleyici Tümünü Temizle menü öğesi için şu şekildedir:

[!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]

Bu işleyici çağırır `Enable` menü öğesine erişimi olan bir nesnenin üye işlevi. `Enable` öğenin kullanılabilir hale getirir.

## <a name="see-also"></a>Ayrıca Bkz.

[Nasıl yapılır: Kullanıcı Arabirimi Nesnelerini Güncelleştirme](../mfc/how-to-update-user-interface-objects.md)

