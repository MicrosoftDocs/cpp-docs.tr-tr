---
title: Komut kimlikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- command IDs, MFC
- command IDs
ms.assetid: e0171a2b-45b9-41fa-945d-ec2f7602ded0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e1e03f10199c1b582a1a8603a6ea6c93e1d55473
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931238"
---
# <a name="command-ids"></a>Komut Kimlikleri
Bir komutu tam olarak tek başına komutu Kimliğiyle açıklanan (kodlanmış **WM_COMMAND** ileti). Bu kimliği komutu oluşturan kullanıcı arabirimi nesneye atanmış. Genellikle, kimlikleri atandığı kullanıcı arabirimi nesnesinin işlevselliğini adlandırılır.  
  
 Örneğin, Düzen menüsü Tümünü Temizle öğesinde bir kimliği gibi atanabilir **ıd_edıt_clear_all**. Sınıf kitaplığı özellikle framework kendisini gibi işleme komutlar için bazı kimlikler önceden belirler **ıd_edıt_clear_all** veya **ıd_fıle_open**. Diğer komut kimlikleri kendiniz oluşturur.  
  
 Menü düzenleyicisi Visual C++'da kendi menüleri oluşturduğunuzda, tarafından gösterildiği gibi sınıf kitaplığı izlemek için iyi bir fikir kuralı adlandırma olduğu **ıd_fıle_open**. [Standart komutlar](../mfc/standard-commands.md) sınıf kitaplığı tarafından tanımlanan standart komutlarını açıklar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı Arabirimi Nesneleri ve Komut Kimlikleri](../mfc/user-interface-objects-and-command-ids.md)

