---
title: NMAKE önemli hatası U1059 | Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1059
dev_langs:
- C++
helpviewer_keywords:
- U1059
ms.assetid: b21d9198-9c63-40d0-b589-80e17294ce24
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8b54919398c757bfe05f747ff57341f31decfc61
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43200796"
---
# <a name="nmake-fatal-error-u1059"></a>NMAKE Önemli Hatası U1059

> sözdizimi hatası: '}' bağımlıda eksik

Bağımlı bir arama yolunu yanlış şekilde belirtildi. Ya da bir alan yolu veya kapanış ayracı var (**}**) atlandı.

Bağımlı bir dizin belirtimi için sözdizimi

> **{** *dizinleri* **} bağımlı**

Burada *dizinleri* bir veya daha fazla yol, noktalı virgülle ayırarak belirtir (**;**). Boşluk olmayan izin verilir.

Kısmını veya tümünü bir arama yolu bir makro tarafından değiştirilirse, makro genişletme içinde boşluk olmadan var olduğundan emin olun.