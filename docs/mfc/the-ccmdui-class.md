---
title: CCmdUI Sınıfı
ms.date: 11/04/2016
helpviewer_keywords:
- updating user interface objects [MFC]
- user interface objects [MFC], updating
- CCmdUI class [MFC], menu updating
- update handlers [MFC]
- toolbars [MFC], updating
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
ms.openlocfilehash: 105aa7ad6c5cc6a5563dbde8145327a2b3d066a1
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447146"
---
# <a name="the-ccmdui-class"></a>CCmdUI Sınıfı

Bir update komutunu işleyicisine yönlendirirse, çerçeve işleyiciyi bir `CCmdUI` nesnesine (veya `CCmdUI`türetilmiş bir sınıfın nesnesine) geçirir. Bu nesne, komutu oluşturan menü öğesini veya araç çubuğu düğmesini veya diğer kullanıcı arabirimi nesnesini temsil eder. Güncelleştirme işleyicisi, Kullanıcı arabirimi nesnesini güncelleştirme işaretçisi aracılığıyla `CCmdUI` yapısının üye işlevlerini çağırır. Örneğin, Tümünü Temizle menü öğesi için bir güncelleştirme işleyicisi aşağıda verilmiştir:

[!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]

Bu işleyici, menü öğesine erişimi olan bir nesnenin `Enable` üye işlevini çağırır. `Enable` öğeyi kullanıma hazır hale getirir.

## <a name="see-also"></a>Ayrıca bkz.

[Nasıl yapılır: Kullanıcı Arabirimi Nesnelerini Güncelleştirme](../mfc/how-to-update-user-interface-objects.md)
