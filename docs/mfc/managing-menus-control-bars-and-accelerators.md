---
title: Menüleri, Denetim çubuklarını ve Hızlandırıcıları yönetme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e19cda1869938a854ff03ea83cdda747e8120a0
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929536"
---
# <a name="managing-menus-control-bars-and-accelerators"></a>Menüleri, Denetim Çubuklarını ve Hızlandırıcıları Yönetme
Çerçeve penceresi menüleri, araç çubuğu düğmeleri, durum çubuğu ve Hızlandırıcıları dahil olmak üzere, kullanıcı arabirimi nesnelerini güncelleştirme yönetir. MDI uygulamaları menü çubuğunda paylaşımı yönetir.  
  
## <a name="managing-menus"></a>Menüleri yönetme  
 Çerçeve penceresi açıklanan on_update_command_uı mekanizmasını kullanarak kullanıcı arabirimi öğeleri güncelleştirilirken katılan [güncelleştirme kullanıcı arabirimi nesnelerini nasıl](../mfc/how-to-update-user-interface-objects.md). Araç çubukları ve diğer denetim çubukları düğmeleri boşta döngü sırasında güncelleştirilir. Menü öğeleri menü çubuğundaki aşağı açılır menüler yalnızca menüyü aşağı bırakır önce güncelleştirilir.  
  
 MDI uygulamaları için menü çubuğundaki ve resim yazısı MDI çerçeve penceresi yönetir. MDI çerçeve penceresi hiçbir etkin MDI alt pencereleri olduğunda, menü çubuğu olarak kullanılan bir varsayılan menüsünü sahip olur. Etkin alt olduğunda MDI çerçeve pencere menü çubuğu etkin MDI alt pencere menüsü tarafından ele alınır. Grafik ve çalışma belgeler gibi birden çok belge türü MDI uygulama destekliyorsa, her tür kendi menüleri menü çubuğuna koyar ve ana çerçeve penceresinin başlık değiştirir.  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) MDI uygulamaları için Pencere menüsünden standart komutlar için varsayılan uygulamaları sağlar. Özellikle, yeni pencere komutu (ıd_wındow_new) yeni çerçeve penceresi ve geçerli belge görünümü oluşturmak için uygulanır. Yalnızca Gelişmiş özelleştirme gerekiyorsa bu uygulamaları geçersiz kılmanız gerekir.  
  
 Belge türü birden çok MDI alt pencereleri menü kaynakları paylaşır. Birkaç MDI alt pencereleri aynı belge şablonu tarafından oluşturduysanız, tüm Windows sistem kaynağı kaydetme aynı menü kaynağı kullanabilirsiniz.  
  
## <a name="managing-the-status-bar"></a>Durum çubuğu yönetme  
 Çerçeve penceresi de kendi istemci alanı içinde durum çubuğunu yerleştirir ve durum yönetir çubuğunun göstergeleri. Çerçeve penceresi temizler ve durum çubuğu ileti alanına gerektiği şekilde güncelleştirir ve kullanıcı menü öğesi veya araç çubuğu düğmeleri seçer açıklandığı gibi komut istemi dizeleri görüntüler [durum çubuğunda komut bilgilerini görüntüle nasıl](../mfc/how-to-display-command-information-in-the-status-bar.md).  
  
## <a name="managing-accelerators"></a>Hızlandırıcıları yönetme  
 Her çerçeve penceresi Hızlandırıcı çeviri sizin için otomatik olarak klavye bir isteğe bağlı Hızlandırıcı tablosu tutar. Bu mekanizma çağırma menü komutlarını Hızlandırıcı tuşları (kısayol tuşları olarak da bilinir) tanımlamak kolaylaştırır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çerçeve Pencerelerini Kullanma](../mfc/using-frame-windows.md)

