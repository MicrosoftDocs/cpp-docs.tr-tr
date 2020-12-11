---
description: 'Hakkında daha fazla bilgi edinin: komut kimlikleri'
title: Komut Kimlikleri
ms.date: 11/04/2016
helpviewer_keywords:
- command IDs, MFC
- command IDs
ms.assetid: e0171a2b-45b9-41fa-945d-ec2f7602ded0
ms.openlocfilehash: bba3b8b342b4d2e0c9492f9d0f3100a5d8f9e7d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159992"
---
# <a name="command-ids"></a>Komut Kimlikleri

Komut, tek başına komut KIMLIĞI tarafından tam olarak tanımlanır ( **WM_COMMAND** iletisinde kodlandı). Bu KIMLIK, komutu üreten Kullanıcı arabirimi nesnesine atanır. Genellikle kimlikler, atandığı kullanıcı arabirimi nesnesinin işlevselliği için adlandırılır.

Örneğin, düzenleme menüsündeki tüm öğelerin Işaretini Kaldır **ID_EDIT_CLEAR_ALL** gıbı bir kimlik atanabilir. Sınıf kitaplığı, özellikle çerçevenin kendisini işlediği komutlar için **ID_EDIT_CLEAR_ALL** veya **ID_FILE_OPEN** gibi bazı kimlikleri önceden tanımlar. Diğer komut kimliklerini kendiniz oluşturacaksınız.

Visual C++ menü düzenleyicisinde kendi menülerinizi oluşturduğunuzda, sınıf kitaplığının adlandırma kuralını **ID_FILE_OPEN** gösterildiği gibi izlemek iyi bir fikirdir. [Standart komutlar](standard-commands.md) , sınıf kitaplığı tarafından tanımlanan standart komutları açıklar.

## <a name="see-also"></a>Ayrıca bkz.

[Kullanıcı arabirimi nesneleri ve komut kimlikleri](user-interface-objects-and-command-ids.md)
