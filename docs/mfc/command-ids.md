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
ms.openlocfilehash: 5087c271151793169cbf7350f78750044ccead0b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446978"
---
# <a name="command-ids"></a>Komut Kimlikleri

Bir komutu tam olarak tek başına komut Kimliğiyle açıklanan (kodlanmış **WM_COMMAND** ileti). Komut oluşturur. kullanıcı arabirimi nesnesi bu Kimliğe atanır. Genellikle, kimlikleri için atanmış olan kullanıcı arabirimi nesnesi işlevselliğini adlandırılır.

Örneğin, Düzen menüsündeki Tümünü Temizle bir öğesi kimliği gibi atanabilir **ıd_edıt_clear_all**. Sınıf kitaplığı, özellikle framework kendisi gibi işleme komutlar için bazı kimlikler önceden belirler **ıd_edıt_clear_all** veya **ıd_fıle_open**. Diğer komut kimlikleri kendiniz oluşturmanız.

Menü düzenleyicisi Visual C++'da kendi menüleri oluşturduğunuzda, tarafından gösterildiği gibi sınıf kitaplığı izlemek için iyi bir fikir kuralı adlandırma olduğu **ıd_fıle_open**. [Standart komutlar](../mfc/standard-commands.md) sınıf kitaplığı tarafından tanımlanan standart komutlarını açıklar.

## <a name="see-also"></a>Ayrıca Bkz.

[Kullanıcı Arabirimi Nesneleri ve Komut Kimlikleri](../mfc/user-interface-objects-and-command-ids.md)

