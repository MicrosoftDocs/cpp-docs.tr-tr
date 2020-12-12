---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları hata LNK2013'
title: Bağlayıcı Araçları Hatası LNK2013
ms.date: 11/04/2016
f1_keywords:
- LNK2013
helpviewer_keywords:
- LNK2013
ms.assetid: 21408e2d-3f56-4d1f-a031-00df70785ed4
ms.openlocfilehash: 51b754e19656ad8ec7ef1686605086b6e4a41853
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338461"
---
# <a name="linker-tools-error-lnk2013"></a>Bağlayıcı Araçları Hatası LNK2013

Düzeltme türü düzeltme taşması. ' Sembol adı ' hedefi Aralık dışında

Hedef sembol yönergenin konumundan çok uzakta olduğundan, bağlayıcı gerekli adrese veya uzaklığa göre aralığa uymuyor.

Bu sorunu birden çok görüntü oluşturarak ya da yönerge ve hedefin birbirine yaklaşabilmesi için [/Order](../../build/reference/order-put-functions-in-order.md) seçeneğini kullanarak çözebilirsiniz.

Sembol adı Kullanıcı tanımlı bir sembol olduğunda (derleyici tarafından oluşturulan bir sembol değil), hatayı çözmek için aşağıdaki eylemleri de deneyebilirsiniz:

- Statik işlevi statik olmayan şekilde değiştirin.

- Statik işlevi içeren kod bölümünü çağıran ile aynı olacak şekilde yeniden adlandırın.

`DUMPBIN /SYMBOLS`Bir işlevin statik olup olmadığını görmek için kullanın.
