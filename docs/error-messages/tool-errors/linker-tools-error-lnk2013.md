---
title: Bağlayıcı araçları hatası LNK2013 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2013
dev_langs:
- C++
helpviewer_keywords:
- LNK2013
ms.assetid: 21408e2d-3f56-4d1f-a031-00df70785ed4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d04ce4ca8079317da090cf05d43f41e4e40a6b19
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041746"
---
# <a name="linker-tools-error-lnk2013"></a>Bağlayıcı Araçları Hatası LNK2013

düzeltme türü düzeltme taşması. Hedef 'sembol adı' je mimo rozsah

Bağlayıcı hedefi sembolü yönergesinin konumdan çok uzakta olduğu için gerekli adres veya offset verilen yönerge sığamıyorsa.

Birden çok görüntü oluşturma veya kullanarak bu sorunu çözebilirsiniz [/sipariş](../../build/reference/order-put-functions-in-order.md) yönerge ve hedef birbirine yakın şekilde seçeneği.

Sembol adı, kullanıcı tanımlı bir sembol (ve bir derleyici tarafından oluşturulan sembolü değil) olduğunda, hatayı gidermek için aşağıdaki eylemleri de deneyebilirsiniz:

- Statik olmayan statik işlevi değiştirin.

- Çağıranın aynı statik işlevi içeren kod bölümünde yeniden adlandırın.

Kullanım `DUMPBIN /SYMBOLS`statik bir işlev olup olmadığını görmek için.