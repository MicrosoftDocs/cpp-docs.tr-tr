---
title: "Derleyici Uyarısı (düzey 4) C4718 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4718
dev_langs:
- C++
helpviewer_keywords:
- C4718
ms.assetid: 29507f8a-b024-42c1-a3b8-f35d1f2641f3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 214c481f4ad77a7a67190cd7427e0cd5775ccc8c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4718"></a>Derleyici Uyarısı (düzey 4) C4718
'işlev çağrısı': Özyinelemeli çağrı silme hiçbir yan etkisi vardır  
  
 Bir işlev yinelemeli bir çağrı içerir, ancak Aksi takdirde hiçbir yan etkisi vardır. Bu işlev için bir çağrı siliniyor. Program doğruluğunu etkilenmez, ancak bir davranıştır. Çalışma zamanı yığın taşması özel durumu içinde çağrısında bırakarak sonuçlanabilir gelirken, çağrı silinmesi bu olasılığı kaldırır.