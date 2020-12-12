---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2732'
title: Derleyici hatası C2732
ms.date: 11/04/2016
f1_keywords:
- C2732
helpviewer_keywords:
- C2732
ms.assetid: 01b7ad2c-93cf-456f-a4c0-c5f2fdc7c07c
ms.openlocfilehash: 1ca97fbf46685af1df37b8caf82a03effc1ec6bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123220"
---
# <a name="compiler-error-c2732"></a>Derleyici hatası C2732

bağlantı belirtimi, ' function ' için daha önceki belirtile çelişiyor

İşlev, farklı bir bağlantı belirticisiyle zaten tanımlanmış.

Bu hata, farklı bağlantı belirticilerine sahip içerme dosyaları nedeniyle oluşabilir.

Bu hatayı onarmak için **`extern`** deyimlerini, linkages 'nin kabul etmesi için değiştirin. Özellikle, `#include` bloklarda yönergeleri sarmayın `extern "C"` .

## <a name="example"></a>Örnek

Aşağıdaki örnek C2732 oluşturur:

```cpp
// C2732.cpp
extern void func( void );   // implicit C++ linkage
extern "C" void func( void );   // C2732
```
