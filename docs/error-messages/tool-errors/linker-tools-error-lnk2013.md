---
title: Bağlayıcı Araçları Hatası LNK2013
ms.date: 11/04/2016
f1_keywords:
- LNK2013
helpviewer_keywords:
- LNK2013
ms.assetid: 21408e2d-3f56-4d1f-a031-00df70785ed4
ms.openlocfilehash: 4d932a89f1b0bde27f6de2f84b2ed103dab1b1b0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620736"
---
# <a name="linker-tools-error-lnk2013"></a>Bağlayıcı Araçları Hatası LNK2013

düzeltme türü düzeltme taşması. Hedef 'sembol adı' je mimo rozsah

Bağlayıcı hedefi sembolü yönergesinin konumdan çok uzakta olduğu için gerekli adres veya offset verilen yönerge sığamıyorsa.

Birden çok görüntü oluşturma veya kullanarak bu sorunu çözebilirsiniz [/sipariş](../../build/reference/order-put-functions-in-order.md) yönerge ve hedef birbirine yakın şekilde seçeneği.

Sembol adı, kullanıcı tanımlı bir sembol (ve bir derleyici tarafından oluşturulan sembolü değil) olduğunda, hatayı gidermek için aşağıdaki eylemleri de deneyebilirsiniz:

- Statik olmayan statik işlevi değiştirin.

- Çağıranın aynı statik işlevi içeren kod bölümünde yeniden adlandırın.

Kullanım `DUMPBIN /SYMBOLS`statik bir işlev olup olmadığını görmek için.