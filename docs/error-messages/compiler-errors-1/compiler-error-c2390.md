---
title: Derleyici Hatası C2390 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2390
dev_langs:
- C++
helpviewer_keywords:
- C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5de5a9af8f8aa04219f0a7d61162336745fd4bfa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098222"
---
# <a name="compiler-error-c2390"></a>Derleyici Hatası C2390

'identifier': Geçersiz depolama sınıfı 'belirticisi'

Depolama sınıfı genel kapsam tanımlayıcısı geçerli değil. Varsayılan depolama sınıfı geçersiz sınıf yerine kullanılır.

Olası çözümler:

- Bir işlev tanımlayıcı ise ile bildirimini `extern` depolama.

- Tanımlayıcı bir biçimsel parametre veya yerel değişken ise, otomatik depolama ile bildirin.

- Tanımlayıcı bir genel değişken ise, hiçbir depolama sınıfı (otomatik depolama) bildirin.

## <a name="example"></a>Örnek

- Aşağıdaki örnek, C2390 oluşturur:

```
// C2390.cpp
register int i;   // C2390

int main() {
   register int j;   // OK
}
```