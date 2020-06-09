---
title: Komut Kimlikleri
ms.date: 11/04/2016
helpviewer_keywords:
- command IDs, MFC
- command IDs
ms.assetid: e0171a2b-45b9-41fa-945d-ec2f7602ded0
ms.openlocfilehash: f7d675891904301b16aafe3acb2c294eede6d8d8
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619034"
---
# <a name="command-ids"></a>Komut Kimlikleri

Komut, tek başına komut KIMLIĞI tarafından tam olarak tanımlanır ( **WM_COMMAND** iletisinde kodlandı). Bu KIMLIK, komutu üreten Kullanıcı arabirimi nesnesine atanır. Genellikle kimlikler, atandığı kullanıcı arabirimi nesnesinin işlevselliği için adlandırılır.

Örneğin, düzenleme menüsündeki tüm öğelerin Işaretini Kaldır **ID_EDIT_CLEAR_ALL**gıbı bir kimlik atanabilir. Sınıf kitaplığı, özellikle çerçevenin kendisini işlediği komutlar için **ID_EDIT_CLEAR_ALL** veya **ID_FILE_OPEN**gibi bazı kimlikleri önceden tanımlar. Diğer komut kimliklerini kendiniz oluşturacaksınız.

Visual C++ menü düzenleyicisinde kendi menülerinizi oluşturduğunuzda, sınıf kitaplığının adlandırma kuralını **ID_FILE_OPEN**gösterildiği gibi izlemek iyi bir fikirdir. [Standart komutlar](standard-commands.md) , sınıf kitaplığı tarafından tanımlanan standart komutları açıklar.

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı Arabirimi Nesneleri ve Komut Kimlikleri](user-interface-objects-and-command-ids.md)
