---
title: "Bağlayıcı araçları hatası LNK2013 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2013
dev_langs: C++
helpviewer_keywords: LNK2013
ms.assetid: 21408e2d-3f56-4d1f-a031-00df70785ed4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 37d6fac7ff5f9fae061ed44c639d3d3de1e9fbda
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk2013"></a>Bağlayıcı Araçları Hatası LNK2013
düzeltmesi türü düzeltmesi taşması. Hedef 'sembol adını' aralık dışında kalıyor  
  
 Bağlayıcı hedef simgenin talimat 's konumdan çok uzakta olduğu için gerekli adres veya offset verilen yönerge sığamıyorsa.  
  
 Birden fazla görüntü oluşturma veya kullanarak bu sorunu çözebilirsiniz [/sipariş](../../build/reference/order-put-functions-in-order.md) yönerge ve hedef birlikte yakın olacak şekilde seçeneği.  
  
 Sembol adı, kullanıcı tanımlı bir simge (ve derleyicinin ürettiği sembol değil) olduğunda, hatayı gidermek için aşağıdaki eylemleri de deneyebilirsiniz:  
  
-   Statik işlev olmayan statik olarak değiştirin.  
  
-   Arayan aynı olacak şekilde statik işlevi içeren kod bölümü yeniden adlandırın.  
  
 Kullanım `DUMPBIN /SYMBOLS`, bir işlev statik olup olmadığını görmek için.