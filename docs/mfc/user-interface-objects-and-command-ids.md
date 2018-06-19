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
ms.openlocfilehash: 6b56babf0e42dde521a6bda3a7d9713db519182c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385605"
---
# <a name="user-interface-objects-and-command-ids"></a>Kullanıcı Arabirimi Nesneleri ve Komut Kimlikleri
Menü öğeleri, araç çubuğu düğmeleri ve Hızlandırıcı tuşları olan "kullanıcı arabirimi nesneleri" komutları oluşturma yeteneği. Böyle bir kullanıcı arabirimi nesne her bir kimliği vardır. Bir kullanıcı arabirimi nesnesi nesne ve komutu aynı kimliği atayarak komutu ile ilişkilendirin. İçinde anlatıldığı gibi [iletileri](../mfc/messages.md), komutları, özel iletileri olarak uygulanır. "Komutları içinde Framework" Aşağıda şekil framework komutları nasıl yönettiğini gösterir. Bir kullanıcı arabirimi nesnesi oluşturduğunda bir komut gibi `ID_EDIT_CLEAR_ALL`, uygulamanızda nesnelerden işleme komutu — Aşağıda, belge nesnesinin şekildeki `OnEditClearAll` işlevi, belgenin ileti eşlemesi çağrılır.  
  
 ![Framework'te komutları](../mfc/media/vc385p1.gif "vc385p1")  
Framework'te komutları  
  
 "Komutu güncelleştirme içinde Framework" aşağıdaki şekilde MFC menü öğeleri ve araç çubuğu düğmeleri gibi kullanıcı arabirimi nesnelerini güncelleştirme biçimini gösterilmektedir. Bir menüyü aşağı veya araç çubuğu düğmeleri söz konusu olduğunda boşta döngü sırasında bırakır önce MFC bir güncelleştirme komutu yönlendirir. Aşağıdaki şekilde belge nesnesi, güncelleştirme komut işleyici çağırır `OnUpdateEditClearAll`, etkinleştirme veya kullanıcı arabirimi nesne devre dışı.  
  
 ![Komut Framework güncelleştirme](../mfc/media/vc385p2.png "vc385p2")  
Komutunu Framework güncelleştiriliyor  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Framework'teki İletiler ve Komutlar](../mfc/messages-and-commands-in-the-framework.md)

