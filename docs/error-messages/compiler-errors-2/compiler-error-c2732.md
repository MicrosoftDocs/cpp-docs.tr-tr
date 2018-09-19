---
title: Derleyici Hatası C2732 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2732
dev_langs:
- C++
helpviewer_keywords:
- C2732
ms.assetid: 01b7ad2c-93cf-456f-a4c0-c5f2fdc7c07c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 040fd73bcb69ef032d5c6150bb157337f34a2088
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079667"
---
# <a name="compiler-error-c2732"></a>Derleyici Hatası C2732

bağlama belirtimi 'function' için önceki belirtimi çelişiyor

İşlev zaten farklı bir bağlantı tanımlayıcısı ile bildirilir.

Bu hataya neden tarafından farklı bağlantı tanımlayıcıları ile dosyaları içerir.

Bu hatayı düzeltmek için değiştirme `extern` deyimleri böylece raporlarınız kabul etmiş olursunuz. Özellikle, değil kaydırma `#include` yönergelerinde `extern "C"` engeller.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2732 oluşturur:

```
// C2732.cpp
extern void func( void );   // implicit C++ linkage
extern "C" void func( void );   // C2732
```