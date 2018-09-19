---
title: Derleyici Hatası C2097 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2097
dev_langs:
- C++
helpviewer_keywords:
- C2097
ms.assetid: 7e5b2fd4-f61c-4b8a-b265-93e987a04bd3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2da955f5382a1ebacdb507a69ed02627b11462e5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021869"
---
# <a name="compiler-error-c2097"></a>Derleyici Hatası C2097

Geçersiz başlatma

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. Nonconstant değerini kullanarak bir değişkenin başlatılması.

1. Uzun bir adresi kısa bir adresle başlatma.

1. Yerel yapı, birleşim veya dizi ile derleme yaparken nonconstant bir ifade ile başlatma **/Za**.

1. Virgül işleci içeren bir ifade ile başlatma.

1. Sabit veya sembolik bir ifade ile başlatma.