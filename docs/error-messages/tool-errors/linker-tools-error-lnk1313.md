---
title: Bağlayıcı araçları hatası LNK1313 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1313
dev_langs:
- C++
helpviewer_keywords:
- LNK1313
ms.assetid: 5df0b72e-bb3f-428c-8d84-6084238f9827
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6a896c8ba012c69755c5292475b2d155ad92066
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34705094"
---
# <a name="linker-tools-error-lnk1313"></a>Bağlayıcı Araçları Hatası LNK1313

> IJW/yerel modül; algılandı saf modüllerle bağlanamıyor

## <a name="remarks"></a>Açıklamalar

Visual C++ geçerli sürümü ile derlenmiş .obj dosyaları ile yerel ya da karma yönetilen/yerel .obj dosyaları bağlantılandırma desteklemiyor **/CLR: pure**.

**/CLR: pure** derleyici seçeneği Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor.

## <a name="example"></a>Örnek

```cpp
// LNK1313.cpp
// compile with: /c /clr:pure
// a pure module
int main() {}
```

## <a name="example"></a>Örnek

```cpp
// LNK1313_b.cpp
// compile with: /c /clr
// an IJW module
void test(){}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek LNK1313 oluşturur.

```cpp
// LNK1313_c.cpp
// compile with: /link LNK1313.obj LNK1313_b.obj
// LNK1313 warning expected
```