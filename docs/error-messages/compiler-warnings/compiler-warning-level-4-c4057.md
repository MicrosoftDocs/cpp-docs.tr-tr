---
title: Derleyici Uyarısı (düzey 4) C4057 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4057
dev_langs:
- C++
helpviewer_keywords:
- C4057
ms.assetid: e75d0645-84c9-4bef-a812-942ed9879aa3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b10ce6b67fd24b4b8db01177af0225deab9dba4b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088013"
---
# <a name="compiler-warning-level-4-c4057"></a>Derleyici Uyarısı (düzey 4) C4057

'operator': 'identifier2' öğesinden 'ıdentifier1' yöneltme için biraz farklı taban türlerden farklı

İşaretçi ifadeleri iki farklı temel türlere başvurur. İfadeler, dönüştürme olmadan kullanılır.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. İmzalı ve imzasız türlerini karıştırmak.

1. Karıştırma **kısa** ve **uzun** türleri.