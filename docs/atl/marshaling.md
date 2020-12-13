---
description: 'Daha fazla bilgi edinin: sıralama'
title: Hazırlama
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
ms.openlocfilehash: 2931bd9ab5e2fb8376ced44dd519a6de107be88e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152639"
---
# <a name="marshaling"></a>Hazırlama

Hazırlama COM tekniği, tek bir işlemde bir nesne tarafından açığa çıkarılan arabirimlerin başka bir işlemde kullanılmasına izin verir. Sıralama sırasında, COM, yöntemin parametrelerini işlemlere taşınabilecek bir biçime (veya diğer makinelerde çalışan işlemlere kadar) ve diğer uçta bu parametrelerin paketini açmak için her ikisi de kod (veya arabirim uygulayıcısı tarafından sağlanan kodu kullanır) sağlar. Benzer şekilde, COM bu aynı adımları çağrıdan geri dönüş üzerinde gerçekleştirmelidir.

> [!NOTE]
> Bir nesne tarafından sunulan bir arabirim nesneyle aynı işlemde kullanılırken sıralama genellikle gerekli değildir. Ancak, iş parçacıkları arasında sıralama gerekebilir.

## <a name="see-also"></a>Ayrıca bkz.

[COM'a Giriş](../atl/introduction-to-com.md)<br/>
[Sıralama ayrıntıları](/windows/win32/com/marshaling-details)
