---
title: Menüleri, Denetim Çubuklarını ve Hızlandırıcıları Yönetme
ms.date: 11/04/2016
helpviewer_keywords:
- MDI [MFC], frame windows
- control bars [MFC], updating in frame windows
- menus [MFC], updating as context changes
- user interface objects [MFC], updating
- accelerator tables [MFC]
- sharing menus [MFC]
- updating user-interface objects [MFC]
- frame windows [MFC], updating
- status bars [MFC], updating
ms.assetid: 97ca1997-06df-4373-b023-4f7ecd81047b
ms.openlocfilehash: 9a089829658265cd835a8c7344aa5bc45fbc109a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57293816"
---
# <a name="managing-menus-control-bars-and-accelerators"></a>Menüleri, Denetim Çubuklarını ve Hızlandırıcıları Yönetme

Çerçeve penceresi menüleri, araç çubuğu düğmeleri, durum çubuğu ve Hızlandırıcıları dahil olmak üzere, kullanıcı arabirimi nesnelerini güncelleştirme yönetir. MDI uygulamaları menü çubuğundaki paylaşımı yönetir.

## <a name="managing-menus"></a>Menüler yönetme

Çerçeve penceresi açıklanan on_update_command_uı mekanizması kullanarak kullanıcı arabirimi öğeleri güncelleştirilirken katıldığı [kullanıcı arabirimi nesnelerini güncelleştirme](../mfc/how-to-update-user-interface-objects.md). Boşta döngü sırasında araç çubukları ve diğer denetim çubukları düğmeleri güncelleştirildi. Menü öğelerinin açılan menüler menü çubuğunda bir menü açılır önce güncelleştirildi.

MDI uygulamaları için MDI çerçeve penceresinin menü çubuğu ve açıklamalı alt yazı yönetir. Bir MDI çerçeve penceresinin hiçbir etkin MDI alt pencereleri olduğunda, menü çubuğu olarak kullanılan bir varsayılan menü sahip. Etkin alt olduğunda, MDI çerçeve penceresinin menü çubuğunu menüsünü etkin MDI alt penceresi tarafından ele alınır. Bir MDI uygulaması grafiği ve çalışma, belgeler gibi birden çok belge türü destekliyorsa her türü kendi menü menü çubuğuna yerleştirir ve ana çerçeve penceresinin başlık değiştirir.

[CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) standart komutlar için varsayılan uygulamaları MDI uygulamaları için Pencere menüsünden sağlar. Özellikle, yeni bir çerçeve penceresi ve geçerli belge görünümü oluşturmak için yeni bir pencere komut (ıd_wındow_new) uygulanır. Gelişmiş özelleştirme gerekiyorsa bu uygulamaları geçersiz kılmak gerekir.

Aynı belge türü birden çok MDI alt pencereleri, menü kaynakları paylaşır. Birkaç MDI alt pencereleri aynı belge şablonu tarafından oluşturulmadıysa, tüm Windows sistem kaynakları kaydetme aynı menü kaynağı kullanabilirsiniz.

## <a name="managing-the-status-bar"></a>Durum çubuğu yönetme

Çerçeve penceresi de kendi istemci alanı içinde durum çubuğuna yerleştirir ve durumunu yöneten çubuğunun göstergeleri. Çerçeve penceresi temizler ve durum çubuğundaki ileti alanı gereken şekilde güncelleştiren ve menü öğeleri veya araç çubuğu düğmeleri, kullanıcının seçtiği olarak açıklandığı gibi komut istemi dizeleri görüntüler [durum çubuğunda komut bilgilerini görüntüleme nasıl](../mfc/how-to-display-command-information-in-the-status-bar.md).

## <a name="managing-accelerators"></a>Hızlandırıcıları yönetme

Her bir çerçeve penceresi Hızlandırıcı çeviri sizin için otomatik olarak klavye ile bir isteğe bağlı Hızlandırıcı tablosu tutar. Bu mekanizma, menü komutlarını çağırma hızlandırma tuşları (kısayol tuşları olarak da bilinir) tanımlamak kolaylaştırır.

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve Pencerelerini Kullanma](../mfc/using-frame-windows.md)
