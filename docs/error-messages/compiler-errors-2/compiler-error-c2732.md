---
title: Derleyici Hatası C2732
ms.date: 11/04/2016
f1_keywords:
- C2732
helpviewer_keywords:
- C2732
ms.assetid: 01b7ad2c-93cf-456f-a4c0-c5f2fdc7c07c
ms.openlocfilehash: 820a620b7e4414123c56433f84536393834f6fd6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62208408"
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