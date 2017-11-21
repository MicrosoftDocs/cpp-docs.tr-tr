---
title: "Durum çubuğu metniyle MFC uygulamalarında menü komutlarını ilişkilendirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- status bars, associating menu items
- menus, status bar text
ms.assetid: 757c0e02-bc97-493f-bccd-6cc6887ebc64
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 16bf93390538a5f2abebb2bf327970dbec1d2a8b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="associating-menu-commands-with-status-bar-text-in-mfc-applications"></a>MFC Uygulamalarında Menü Komutlarını Durum Çubuğu Metniyle İlişkilendirme
Uygulamanızı her bir kullanıcı seçebilirsiniz menü komutları için açıklayıcı metin görüntüleyebilirsiniz. Her menü komutunu kullanarak için bir metin dizesi atayarak bunu **komut istemi** Özellikleri penceresinde özelliği. Bir dize varsa [dize tablosu](../windows/string-editor.md) Kimliğine komutu ile aynıdır, bir kullanıcı bir menü öğesi geldiğinde MFC uygulaması otomatik olarak bu dize kaynağı çalışan uygulama durum çubuğunda görüntülenir.  
  
### <a name="to-associate-a-menu-command-with-a-status-bar-text-string"></a>Bir durum çubuğu metin dizesi menü komutu ilişkilendirmek için  
  
1.  İçinde **menü** Düzenleyicisi, menü komutunu seçin.  
  
2.  İçinde [Özellikler penceresini](/visualstudio/ide/reference/properties-window), ilgili durum çubuğu metni yazın **komut istemi** kutusu.  
  

  
 **Gereksinimler**  
  
 MFC  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dizeler (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [Menüye komut ekleme](../windows/adding-commands-to-a-menu.md)   
 [Menü düzenleyicisi](../windows/menu-editor.md)