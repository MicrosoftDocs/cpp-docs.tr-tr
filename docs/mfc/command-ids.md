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
ms.openlocfilehash: 0dc27e39f6e2753b7b468e39c283d58c3e585d6d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341478"
---
# <a name="command-ids"></a>Komut Kimlikleri
Bir komutu tam olarak tek başına komutu Kimliğiyle açıklanan (kodlanmış **WM_COMMAND** ileti). Bu kimliği komutu oluşturan kullanıcı arabirimi nesneye atanmış. Genellikle, kimlikleri atandığı kullanıcı arabirimi nesnesinin işlevselliğini adlandırılır.  
  
 Örneğin, Düzen menüsü Tümünü Temizle öğesinde bir kimliği gibi atanabilir **ıd_edıt_clear_all**. Sınıf kitaplığı özellikle framework kendisini gibi işleme komutlar için bazı kimlikler önceden belirler **ıd_edıt_clear_all** veya `ID_FILE_OPEN`. Diğer komut kimlikleri kendiniz oluşturur.  
  
 Menü düzenleyicisi Visual C++'da kendi menüleri oluşturduğunuzda, tarafından gösterildiği gibi sınıf kitaplığı izlemek için iyi bir fikir kuralı adlandırma olduğu `ID_FILE_OPEN`. [Standart komutlar](../mfc/standard-commands.md) sınıf kitaplığı tarafından tanımlanan standart komutlarını açıklar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kullanıcı Arabirimi Nesneleri ve Komut Kimlikleri](../mfc/user-interface-objects-and-command-ids.md)

