---
description: 'Hakkında daha fazla bilgi edinin: User-Interface nesneler ve komut kimlikleri'
title: Kullanıcı Arabirimi Nesneleri ve Komut Kimlikleri
ms.date: 11/19/2018
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
ms.openlocfilehash: 142b72956e0a1b9e60ef48c7db325cd0ac822444
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263627"
---
# <a name="user-interface-objects-and-command-ids"></a>Kullanıcı Arabirimi Nesneleri ve Komut Kimlikleri

Menü öğeleri, araç çubuğu düğmeleri ve hızlandırıcı tuşları, komut oluşturma yeteneğine sahip "Kullanıcı arabirimi nesneleri" dir. Her bir kullanıcı arabirimi nesnesinin KIMLIĞI vardır. Bir kullanıcı arabirimi nesnesini, nesnesine ve komutuna aynı KIMLIĞI atayarak bir komutla ilişkilendirirsiniz. [İletilerde](../mfc/messages.md)açıklandığı gibi, komutlar özel iletiler olarak uygulanır. Aşağıdaki şekil "çerçevede bulunan komutlar", çerçevenin komutları nasıl yönettiğini gösterir. Bir kullanıcı arabirimi nesnesi gibi bir komut oluşturduğunda, `ID_EDIT_CLEAR_ALL` uygulamanızdaki nesnelerden biri komutu işler — aşağıdaki şekilde, belge nesnesinin `OnEditClearAll` işlevi belgenin ileti eşlemesi aracılığıyla çağrılır.

![Çerçevede komutlar](../mfc/media/vc385p1.gif "Çerçevede komutlar") <br/>
Çerçevede komutlar

Aşağıdaki şekil "çerçevede komut güncelleştirme" bölümünde, MFC 'nin menü öğeleri ve araç çubuğu düğmeleri gibi kullanıcı arabirimi nesnelerini nasıl güncelleştirdiği gösterilmektedir. Bir menü kapatılmadan önce veya araç çubuğu düğmeleri durumunda boşta döngüsü sırasında, MFC bir update komutunu yönlendirir. Aşağıdaki şekilde, belge nesnesi, `OnUpdateEditClearAll` Kullanıcı arabirimi nesnesini etkinleştirmek veya devre dışı bırakmak için, güncelleştirme komut işleyicisini çağırır.

![Çerçevede komut güncelleştirme](../mfc/media/vc385p2.png "Çerçevede komut güncelleştirme") <br/>
Çerçevede komut güncelleştirme

## <a name="see-also"></a>Ayrıca bkz.

[Çerçevede iletiler ve komutlar](../mfc/messages-and-commands-in-the-framework.md)
