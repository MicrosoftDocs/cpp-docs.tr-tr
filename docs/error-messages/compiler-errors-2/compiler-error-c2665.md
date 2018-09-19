---
title: Derleyici Hatası C2665 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2665
dev_langs:
- C++
helpviewer_keywords:
- C2665
ms.assetid: a7f99b61-2eae-4f2b-ba75-ea68fd1e8312
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b442e1de0481ef3d00742ed201575526332decff
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109151"
---
# <a name="compiler-error-c2665"></a>Derleyici Hatası C2665

'function': 'type' türünden Sayı1 aşırı hiçbiri parametresi sayı2 dönüştürebilir

Aşırı yüklenen işlevin parametre gerekli türüne dönüştürülemiyor.  Olası çözümler:

- Bir dönüştürme operatörünün sağlayın.

- Açık dönüştürme kullanın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2665 oluşturur.

```
// C2665.cpp
void func(short, char*){}
void func(char*, char*){}

int main() {
   func(0, 1);   // C2665
   func((short)0, (char*)1);   // OK
}
```