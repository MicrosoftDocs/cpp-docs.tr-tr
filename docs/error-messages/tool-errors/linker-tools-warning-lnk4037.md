---
title: Bağlayıcı araçları uyarısı LNK4037 | Microsoft Docs
ms.custom: ''
ms.date: 10/04/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4037
dev_langs:
- C++
helpviewer_keywords:
- LNK4037
ms.assetid: 9ba02fd3-b04f-4679-bab9-26fa82cf09bb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6b87f0a415d6ae7d282e29c2ca67fda043c2a901
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302441"
---
# <a name="linker-tools-warning-lnk4037"></a>Bağlayıcı araçları uyarısı LNK4037

>'*sembol*' yok; göz ardı

Düzenlenmiş adı *simgesi* kullanarak sıralanmalıdır değil [/sipariş](../../build/reference/order-put-functions-in-order.md) olacağından programa bulunamadı. Belirtimini denetleyin *simgesi* sipariş yanıt dosyasındaki. Daha fazla bilgi için bkz: [/ORDER (Put işlevleri Sırala)](../../build/reference/order-put-functions-in-order.md) bağlayıcı seçeneği.

> [!NOTE]
> Statik işlev adları değil Ortak sembol adları olduğundan bağlantı statik işlevleri order yapılamıyor. Zaman **/sipariş** belirtilen uyarı bu bağlayıcı ya da statik sipariş yanıt dosyasını dosyasındaki her simge için oluşturulur veya bulunamadı.