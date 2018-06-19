---
title: NMAKE önemli hatası U1099 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1099
dev_langs:
- C++
helpviewer_keywords:
- U1099
ms.assetid: 6688a805-43e6-4247-a2d0-14be082f0b13
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7be09691de4212d07b1452ffe33725a3978fc053
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322110"
---
# <a name="nmake-fatal-error-u1099"></a>NMAKE Önemli Hatası U1099
yığın taşması  
  
 İşlenmekte olan derleme görevleri dosyası NMAKE içindeki geçerli yığın ayırma için çok karmaşık. NMAKE 0x3000 (12 K) ayırma sahiptir.  
  
 NMAKE'ın yığın ayırma artırmak için Çalıştır [editbin /stack](../../build/reference/stack.md) yardımcı programı ile daha büyük bir yığın seçeneği:  
  
 **edıtbın /STACK:reserve NMAKE. EXE**  
  
 Burada *yedek* bir sayı NMAKE içindeki geçerli yığın ayırma değerinden daha büyük.