---
title: Kullanıcı arabirimi nesneleri ve komut kimlikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keyboard shortcuts, associating with IDs
- MFC, command routing
- toolbar controls [MFC], command ID
- menu items, associating with IDs
- user interface objects [MFC], associating with IDs
- command IDs, user interface objects
- command routing [MFC], MFC
- command handling [MFC], user-interface objects
ms.assetid: 4ea19e9b-ed1e-452e-bd33-7f509107a45b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e8a61699ddd2c48e36bdfd5936fb4ab7aa56e0a9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416129"
---
# <a name="user-interface-objects-and-command-ids"></a>Kullanıcı Arabirimi Nesneleri ve Komut Kimlikleri

Menü öğeleri, araç çubuğu düğmeleri ve kısayol tuşları olan "kullanıcı arabirimi nesneleri" komutları oluşturma yeteneği. Her tür kullanıcı arabirimi nesnesi, bir kimliği vardır. Bir kullanıcı arabirimi nesnesi nesne ve komut aynı kimliği atayarak bir komut ile ilişkilendirin. İçinde anlatıldığı gibi [iletileri](../mfc/messages.md), komutları, özel ileti olarak uygulanır. "Komutları, Framework" Aşağıdaki şekil, framework komutları nasıl yönettiğini gösterir. Ne zaman bir kullanıcı arabirimi nesnesi oluşturur, komut gibi `ID_EDIT_CLEAR_ALL`, uygulamanızdaki nesneleri birini işler komutu — Aşağıda, belge nesnenin şekildeki `OnEditClearAll` belgenin ileti eşlemesi çağrılan işlev.

![Framework'te komutları](../mfc/media/vc385p1.gif "vc385p1") Framework komutları

"Komut güncelleştirme içinde Framework" aşağıdaki şekilde, MFC menü öğeleri ve araç çubuğu düğmeleri gibi kullanıcı arabirimi nesneleri güncelleştirmeleri nasıl gösterilmektedir. Önce aşağı doğru açılır menü veya araç çubuğu düğmeleri söz konusu olduğunda boşta döngü sırasında güncelleştirme komutu MFC yönlendirir. Aşağıdaki çizimde, belge nesnesi güncelleştirme komut işleyicisi, çağıran `OnUpdateEditClearAll`, etkinleştirme veya devre dışı kullanıcı arabirimi nesnesi.

![Komutu Framework güncelleştirme](../mfc/media/vc385p2.png "vc385p2") Framework komut güncelleştiriliyor

## <a name="see-also"></a>Ayrıca Bkz.

[Framework'teki İletiler ve Komutlar](../mfc/messages-and-commands-in-the-framework.md)

