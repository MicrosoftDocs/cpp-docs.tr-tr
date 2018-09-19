---
title: Derleyici Uyarısı (düzey 1) C4532 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4532
dev_langs:
- C++
helpviewer_keywords:
- C4532
ms.assetid: 4e2a286a-d233-4106-9f65-29be1a94ca02
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 717af9626866fb20e92342fe90f4dde2b5030774
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46025483"
---
# <a name="compiler-warning-level-1-c4532"></a>Derleyici Uyarısı (düzey 1) C4532

'continue': __finally/finally bloğunun dışına atlama sonlandırma işleme sırasında davranışı tanımsız

Derleyici, aşağıdaki anahtar sözcükler birini karşılaştı:

- [continue](../../cpp/continue-statement-cpp.md)

- [break](../../cpp/break-statement-cpp.md)

- [goto](../../cpp/goto-statement-cpp.md)

dışında bir atlama neden bir [__finally](../../cpp/try-finally-statement.md) veya [son](../../dotnet/finally.md) olağan dışı sonlandırma sırasında blok.

Bir özel durum oluşursa ve yığın sonlandırma işleyicileri yürütülürken sapmasına sırada ( `__finally` veya finally bloklarında), ve kod dışı atlar bir `__finally` önce block `__finally` blok uç, davranış tanımlanmamıştır. Özel durumu düzgün bir şekilde işlenmemiş için denetimi geriye doğru izleme kodu döndürmeyebilir.

/ Atlama, bir **__finally** engelleme, olağan dışı sonlandırma için ilk olarak denetleyin.

Aşağıdaki örnek, C4532 oluşturur; Yalnızca açıklama uyarıları gidermek için atlama deyimleri yerleştirin.

```
// C4532.cpp
// compile with: /W1
// C4532 expected
int main() {
   int i;
   for (i = 0; i < 10; i++) {
      __try {
      } __finally {
         // Delete the following line to resolve.
         continue;
      }

      __try {
      } __finally {
         // Delete the following line to resolve.
         break;
      }
   }
}
```