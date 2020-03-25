---
title: Bağlayıcı Araçları Hatası LNK2013
ms.date: 11/04/2016
f1_keywords:
- LNK2013
helpviewer_keywords:
- LNK2013
ms.assetid: 21408e2d-3f56-4d1f-a031-00df70785ed4
ms.openlocfilehash: 6ad3f40f06e64422b393edb457a0dcf419828b6f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194752"
---
# <a name="linker-tools-error-lnk2013"></a>Bağlayıcı Araçları Hatası LNK2013

Düzeltme türü düzeltme taşması. ' Sembol adı ' hedefi Aralık dışında

Hedef sembol yönergenin konumundan çok uzakta olduğundan, bağlayıcı gerekli adrese veya uzaklığa göre aralığa uymuyor.

Bu sorunu birden çok görüntü oluşturarak ya da yönerge ve hedefin birbirine yaklaşabilmesi için [/Order](../../build/reference/order-put-functions-in-order.md) seçeneğini kullanarak çözebilirsiniz.

Sembol adı Kullanıcı tanımlı bir sembol olduğunda (derleyici tarafından oluşturulan bir sembol değil), hatayı çözmek için aşağıdaki eylemleri de deneyebilirsiniz:

- Statik işlevi statik olmayan şekilde değiştirin.

- Statik işlevi içeren kod bölümünü çağıran ile aynı olacak şekilde yeniden adlandırın.

Bir işlevin statik olup olmadığını görmek için `DUMPBIN /SYMBOLS`kullanın.
