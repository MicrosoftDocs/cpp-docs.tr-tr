---
title: Önemli hata C1383 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1383
dev_langs:
- C++
helpviewer_keywords:
- C1383
ms.assetid: ca224d14-d687-4fd6-80c2-8b82f28924ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 98f6fe881b2cdc46d4d2848d6faf850381f54c7b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062195"
---
# <a name="fatal-error-c1383"></a>Önemli hata C1383

derleyici seçeneği /GL, ortak dil çalışma zamanının yüklü sürümüyle uyumlu değil

C1383 oluşur ortak dil çalışma zamanının önceki bir sürümü daha yeni bir derleyici ile kullanırken ve ile derleme yaparken **/CLR** ve **/GL**

Çözmek için ya da kullanmayın **/GL** ile **/CLR** veya derleyici ile birlikte gelen ortak dil çalışma zamanı sürümünü yükleyin.

Daha fazla bilgi için [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) ve [/GL (bütün Program iyileştirmesi)](../../build/reference/gl-whole-program-optimization.md).