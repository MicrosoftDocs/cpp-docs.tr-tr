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
ms.openlocfilehash: 9320b9ead0276b6fb5e1b9773260049a01520e12
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33299857"
---
# <a name="linker-tools-error-lnk2013"></a>Bağlayıcı Araçları Hatası LNK2013
düzeltmesi türü düzeltmesi taşması. Hedef 'sembol adını' aralık dışında kalıyor  
  
 Bağlayıcı hedef simgenin talimat 's konumdan çok uzakta olduğu için gerekli adres veya offset verilen yönerge sığamıyorsa.  
  
 Birden fazla görüntü oluşturma veya kullanarak bu sorunu çözebilirsiniz [/sipariş](../../build/reference/order-put-functions-in-order.md) yönerge ve hedef birlikte yakın olacak şekilde seçeneği.  
  
 Sembol adı, kullanıcı tanımlı bir simge (ve derleyicinin ürettiği sembol değil) olduğunda, hatayı gidermek için aşağıdaki eylemleri de deneyebilirsiniz:  
  
-   Statik işlev olmayan statik olarak değiştirin.  
  
-   Arayan aynı olacak şekilde statik işlevi içeren kod bölümü yeniden adlandırın.  
  
 Kullanım `DUMPBIN /SYMBOLS`, bir işlev statik olup olmadığını görmek için.