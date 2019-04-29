---
title: Derleyici Hatası C2891
ms.date: 11/04/2016
f1_keywords:
- C2891
helpviewer_keywords:
- C2891
ms.assetid: e12cfb2d-df45-4b0d-b155-c51d17e812fa
ms.openlocfilehash: d9a1cdafdf7d3a2843aee4a20f71c7e6a4693150
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366374"
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