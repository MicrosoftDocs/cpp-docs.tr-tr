---
title: Hazırlama
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
ms.openlocfilehash: 9963e261f26daa57cb58e30ffc404b431d781bfa
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492038"
---
# <a name="marshaling"></a>Hazırlama

Hazırlama COM tekniği, tek bir işlemde bir nesne tarafından açığa çıkarılan arabirimlerin başka bir işlemde kullanılmasına izin verir. Sıralama sırasında, COM, yöntemin parametrelerini işlemlere taşınabilecek bir biçime (veya diğer makinelerde çalışan işlemlere kadar) ve bu parametrelerin paketini açmak için her ikisi de kod (veya arabirim uygulayıcısı tarafından sağlanan kodu kullanır) sağlar. diğer uçta. Benzer şekilde, COM bu aynı adımları çağrıdan geri dönüş üzerinde gerçekleştirmelidir.

> [!NOTE]
>  Bir nesne tarafından sunulan bir arabirim nesneyle aynı işlemde kullanılırken sıralama genellikle gerekli değildir. Ancak, iş parçacıkları arasında sıralama gerekebilir.

## <a name="see-also"></a>Ayrıca bkz.

[COM’a Giriş](../atl/introduction-to-com.md)<br/>
[Sıralama ayrıntıları](/windows/win32/com/marshaling-details)
