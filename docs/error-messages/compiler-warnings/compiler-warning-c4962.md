---
title: Derleyici Uyarısı C4962 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4962
dev_langs:
- C++
helpviewer_keywords:
- C4962
ms.assetid: 62b156fe-04e5-4a6e-9339-6ab148185f87
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: caff08744497936839e1021cef8fc86e0e8aa7e5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066264"
---
# <a name="compiler-warning-c4962"></a>Derleyici Uyarısı C4962

"function': iyileştirmeler profil verilerinin tutarsız olmasına yol açtığı için devre dışı profil temelli iyileştirmeler"

Bir işlev, işlev sayısı (Profil) verileri güvenilmez olduğundan /LTCG:PGO ile derlenmedi. Bu işlev için güvenilir profil verilerini içeren .pgc dosyası yeniden oluşturmak için profil oluşturma yineler.

Varsayılan olarak bu uyarıyı kapalıdır. Daha fazla bilgi için [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md).