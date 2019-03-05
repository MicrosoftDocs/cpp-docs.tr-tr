---
title: Komut Kimlikleri
ms.date: 11/04/2016
helpviewer_keywords:
- command IDs, MFC
- command IDs
ms.assetid: e0171a2b-45b9-41fa-945d-ec2f7602ded0
ms.openlocfilehash: 76071105e72f1ca4a851b9cdb76d5f1a96f44edb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57274586"
---
# <a name="command-ids"></a>Komut Kimlikleri

Bir komutu tam olarak tek başına komut Kimliğiyle açıklanan (kodlanmış **WM_COMMAND** ileti). Komut oluşturur. kullanıcı arabirimi nesnesi bu Kimliğe atanır. Genellikle, kimlikleri için atanmış olan kullanıcı arabirimi nesnesi işlevselliğini adlandırılır.

Örneğin, Düzen menüsündeki Tümünü Temizle bir öğesi kimliği gibi atanabilir **ıd_edıt_clear_all**. Sınıf kitaplığı, özellikle framework kendisi gibi işleme komutlar için bazı kimlikler önceden belirler **ıd_edıt_clear_all** veya **ıd_fıle_open**. Diğer komut kimlikleri kendiniz oluşturmanız.

Menü düzenleyicisi Visual C++'da kendi menüleri oluşturduğunuzda, tarafından gösterildiği gibi sınıf kitaplığı izlemek için iyi bir fikir kuralı adlandırma olduğu **ıd_fıle_open**. [Standart komutlar](../mfc/standard-commands.md) sınıf kitaplığı tarafından tanımlanan standart komutlarını açıklar.

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı Arabirimi Nesneleri ve Komut Kimlikleri](../mfc/user-interface-objects-and-command-ids.md)
