---
description: 'Daha fazla bilgi edinin: CCmdUI sınıfı'
title: CCmdUI Sınıfı
ms.date: 11/04/2016
helpviewer_keywords:
- updating user interface objects [MFC]
- user interface objects [MFC], updating
- CCmdUI class [MFC], menu updating
- update handlers [MFC]
- toolbars [MFC], updating
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
ms.openlocfilehash: 5fae6d2dda948fd3720a29d502d7f050e388bceb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216138"
---
# <a name="the-ccmdui-class"></a>CCmdUI Sınıfı

Bir update komutunu işleyicisine yönlendirirse, çerçeve işleyiciyi bir `CCmdUI` nesneye (veya bir `CCmdUI` türetilmiş sınıfın nesnesine) geçirir. Bu nesne, komutu oluşturan menü öğesini veya araç çubuğu düğmesini veya diğer kullanıcı arabirimi nesnesini temsil eder. Güncelleştirme işleyicisi, `CCmdUI` Kullanıcı arabirimi nesnesini güncelleştirme işaretçisi aracılığıyla yapının üye işlevlerini çağırır. Örneğin, Tümünü Temizle menü öğesi için bir güncelleştirme işleyicisi aşağıda verilmiştir:

[!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]

Bu işleyici, `Enable` menü öğesine erişimi olan bir nesnenin üye işlevini çağırır. `Enable` öğeyi kullanıma açık hale getirir.

## <a name="see-also"></a>Ayrıca bkz.

[Nasıl yapılır: User-Interface nesneleri güncelleştirme](../mfc/how-to-update-user-interface-objects.md)
