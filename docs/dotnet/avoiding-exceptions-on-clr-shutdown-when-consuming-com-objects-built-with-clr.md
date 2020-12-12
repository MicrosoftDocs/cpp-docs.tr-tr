---
description: Hakkında daha fazla bilgi edinin:/clr ile oluşturulan COM nesnelerini tüketirken CLR kapatılırken özel durumları önleme
title: Clr ile oluşturulan COM nesneleri tarafından oluşturulan özel durumları önleme
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], CLR shutdown exceptions
- /clr compiler option [C++], CLR shutdown exceptions
- mixed assemblies [C++], CLR shutdown exceptions
- /clr compiler option [C++], COM objects
- interoperability [C++], CLR shutdown exceptions
- CLR shutdown exceptions [C++]
ms.assetid: 41249d83-4b51-4e46-866f-27f475f2498c
ms.openlocfilehash: 899f7905aafcf1bff92e37ee70253e74759b3f57
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282620"
---
# <a name="avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr"></a>CLR Kapatmasında /clr ile Oluşturulan COM Nesnelerini Tüketirken Özel Durumları Önleme

Ortak dil çalışma zamanı (CLR) kapalı moduna girdiğinde, yerel işlevlerin CLR hizmetlerine sınırlı erişimi vardır. **/Clr** ile derlenen bir com nesnesinde yayın çağrılmaya çalışırken, clr yerel koda geçiş yapar ve ardından IUnknown:: Release çağrısına (yönetilen kodda tanımlanır) hizmet vermek için yönetilen koda geri geçiş yapar. CLR, Kapalı modda olduğundan, çağrıyı yönetilen koda geri vermez.

Bunu çözmek için, Release metotlarından çağrılan yok edicilerin yalnızca yerel kod içerdiğinden emin olun.

## <a name="see-also"></a>Ayrıca bkz.

[Karışık (yerel ve yönetilen) derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)
