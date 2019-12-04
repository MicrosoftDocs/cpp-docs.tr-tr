---
title: Derleyici hatası C2732
ms.date: 11/04/2016
f1_keywords:
- C2732
helpviewer_keywords:
- C2732
ms.assetid: 01b7ad2c-93cf-456f-a4c0-c5f2fdc7c07c
ms.openlocfilehash: 61bac8c1b5c9e029cc5833f458669b490fed8c91
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755804"
---
# <a name="compiler-error-c2732"></a>Derleyici hatası C2732

bağlantı belirtimi, ' function ' için daha önceki belirtile çelişiyor

İşlev, farklı bir bağlantı belirticisiyle zaten tanımlanmış.

Bu hata, farklı bağlantı belirticilerine sahip içerme dosyaları nedeniyle oluşabilir.

Bu hatayı onarmak için `extern` deyimlerini, linkages 'nin kabul etmesi için değiştirin. Özellikle, `extern "C"` bloklarda `#include` yönergelerini sarmayın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2732 oluşturur:

```cpp
// C2732.cpp
extern void func( void );   // implicit C++ linkage
extern "C" void func( void );   // C2732
```
