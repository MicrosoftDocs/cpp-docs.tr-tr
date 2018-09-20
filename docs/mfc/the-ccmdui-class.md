---
title: Ccmduı sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CCmdUI
dev_langs:
- C++
helpviewer_keywords:
- updating user interface objects [MFC]
- user interface objects [MFC], updating
- CCmdUI class [MFC], menu updating
- update handlers [MFC]
- toolbars [MFC], updating
ms.assetid: 2f2bae62-8c29-45a4-bbce-490eb01907d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 18b5675aff2d10f224238a1ba6d3b919e1b285a7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374588"
---
# <a name="the-ccmdui-class"></a>CCmdUI Sınıfı

Bu güncelleştirme komut işleyicisine yönlendirir, framework işleyici işaretçisi geçirir. bir `CCmdUI` nesne (veya bir nesne için bir `CCmdUI`-türetilmiş sınıf). Bu nesne, menü öğesi veya araç çubuğu düğmesini veya komut oluşturulan diğer kullanıcı arabirimi nesnesi temsil eder. Güncelleştirme işleyici üye işlevlerini çağıran `CCmdUI` yapı ile güncelleştirme kullanıcı arabirimi nesnesi için işaretçi. Örneğin, bir güncelleştirme işleyici Tümünü Temizle menü öğesi için şu şekildedir:

[!code-cpp[NVC_MFCDocView#3](../mfc/codesnippet/cpp/the-ccmdui-class_1.cpp)]

Bu işleyici çağırır `Enable` menü öğesine erişimi olan bir nesnenin üye işlevi. `Enable` öğenin kullanılabilir hale getirir.

## <a name="see-also"></a>Ayrıca Bkz.

[Nasıl yapılır: Kullanıcı Arabirimi Nesnelerini Güncelleştirme](../mfc/how-to-update-user-interface-objects.md)

