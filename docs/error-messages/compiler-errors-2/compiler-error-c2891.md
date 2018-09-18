---
title: Derleyici Hatası C2891 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2891
dev_langs:
- C++
helpviewer_keywords:
- C2891
ms.assetid: e12cfb2d-df45-4b0d-b155-c51d17e812fa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 86d81662cb02fa3c8f6af75009daf4dab9b70196
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016565"
---
# <a name="compiler-error-c2891"></a>Derleyici Hatası C2891

'parameter': bir şablon parametresinin adresi alınamaz

Lvalue olmadığı sürece bir şablon parametresinin adresi alınamaz. Tür parametrelerine sahip oldukları herhangi bir adres lvalues değildir. Türü olmayan değerleri lvalues olmayan şablon parametre listeleri de bir adresi yok. Şablon parametre olarak geçirilen değer şablon bağımsız değişkeni derleyici tarafından oluşturulan bir kopyasını derleyici hatası C2891 neden bir kod örneğini olmasıdır.

```
template <int i> int* f() { return &i; }
```

Lvalues, başvuru türleri gibi bir şablon parametreleri alınan kendi adresi.

```
template <int& r> int* f() { return &r; }
```

Bu hatayı düzeltmek için bir lvalue olmadığı sürece bir şablon parametresinin adresi almaz.