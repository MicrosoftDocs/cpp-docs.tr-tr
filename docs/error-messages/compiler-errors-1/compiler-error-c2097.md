---
title: Derleyici Hatası C2097
ms.date: 11/04/2016
f1_keywords:
- C2097
helpviewer_keywords:
- C2097
ms.assetid: 7e5b2fd4-f61c-4b8a-b265-93e987a04bd3
ms.openlocfilehash: 8b50221997dcf2fb60ee2b82ed630dd325a38145
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676596"
---
# <a name="compiler-error-c2097"></a>Derleyici Hatası C2097

Geçersiz başlatma

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. Nonconstant değerini kullanarak bir değişkenin başlatılması.

1. Uzun bir adresi kısa bir adresle başlatma.

1. Yerel yapı, birleşim veya dizi ile derleme yaparken nonconstant bir ifade ile başlatma **/Za**.

1. Virgül işleci içeren bir ifade ile başlatma.

1. Sabit veya sembolik bir ifade ile başlatma.