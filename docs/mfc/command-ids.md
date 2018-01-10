---
title: Komut kimlikleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- command IDs, MFC
- command IDs
ms.assetid: e0171a2b-45b9-41fa-945d-ec2f7602ded0
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b651c734fbd7098705801aefcaa490293a4d661d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="command-ids"></a>Komut Kimlikleri
Bir komutu tam olarak tek başına komutu Kimliğiyle açıklanan (kodlanmış **WM_COMMAND** ileti). Bu kimliği komutu oluşturan kullanıcı arabirimi nesneye atanmış. Genellikle, kimlikleri atandığı kullanıcı arabirimi nesnesinin işlevselliğini adlandırılır.  
  
 Örneğin, Düzen menüsü Tümünü Temizle öğesinde bir kimliği gibi atanabilir **ıd_edıt_clear_all**. Sınıf kitaplığı özellikle framework kendisini gibi işleme komutlar için bazı kimlikler önceden belirler **ıd_edıt_clear_all** veya `ID_FILE_OPEN`. Diğer komut kimlikleri kendiniz oluşturur.  
  
 Menü düzenleyicisi Visual C++'da kendi menüleri oluşturduğunuzda, tarafından gösterildiği gibi sınıf kitaplığı izlemek için iyi bir fikir kuralı adlandırma olduğu `ID_FILE_OPEN`. [Standart komutlar](../mfc/standard-commands.md) sınıf kitaplığı tarafından tanımlanan standart komutlarını açıklar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı Arabirimi Nesneleri ve Komut Kimlikleri](../mfc/user-interface-objects-and-command-ids.md)

