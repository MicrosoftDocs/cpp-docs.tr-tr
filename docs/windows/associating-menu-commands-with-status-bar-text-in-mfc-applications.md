---
title: "Durum çubuğu metniyle MFC uygulamalarında menü komutlarını ilişkilendirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- status bars, associating menu items
- menus, status bar text
ms.assetid: 757c0e02-bc97-493f-bccd-6cc6887ebc64
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ea0f68bbd0c426aee8141c27d6852bfaaa6ed523
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [Menü Düzenleyicisi](../windows/menu-editor.md)