---
title: Hazırlama
ms.date: 11/04/2016
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
ms.openlocfilehash: 83cf29fb45347b7bfcfc1644546684f074061d25
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319349"
---
# <a name="marshaling"></a>Hazırlama

Mareşallik COM tekniği, bir işlemde bir nesne tarafından maruz kalan arabirimlerin başka bir işlemde kullanılmasını sağlar. Mareşallikte COM, bir yöntemin parametrelerini hem işlemler arasında (hem de diğer makinelerde çalışan işlemlere kablo boyunca) taşıyabilen bir biçime paketlemek ve bu parametreleri diğer uçta açmak için kod (veya arayüz uygulayıcısı tarafından sağlanan kodu kullanır) sağlar. Aynı şekilde, COM aramadan dönüşte de aynı adımları gerçekleştirmelidir.

> [!NOTE]
> Bir nesne tarafından sağlanan bir arabirim nesneyle aynı işlemde kullanılıyorsa, genellikle mareşallik gerekmez. Ancak, iş parçacıkları arasında mareşallik gerekebilir.

## <a name="see-also"></a>Ayrıca bkz.

[COM'a Giriş](../atl/introduction-to-com.md)<br/>
[Marshaling Ayrıntılar](/windows/win32/com/marshaling-details)
