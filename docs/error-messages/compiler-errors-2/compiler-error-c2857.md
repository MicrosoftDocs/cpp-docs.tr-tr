---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2857'
title: Derleyici hatası C2857
ms.date: 09/13/2018
f1_keywords:
- C2857
helpviewer_keywords:
- C2857
ms.assetid: b57302bd-58ec-45ae-992a-1e282d5eeccc
ms.openlocfilehash: 85f2a9cffc8a96998a102d9e8219d9656cb3386f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337524"
---
# <a name="compiler-error-c2857"></a>Derleyici hatası C2857

> /I *filename* komut satırı seçeneğiyle belirtilen ' #include ' ifadesiyle kaynak dosyada bulunamadı

[/Yıc](../../build/reference/yc-create-precompiled-header-file.md) seçeneği, derlenen kaynak dosyasında bulunmayan bir içerme dosyasının adını belirtir.

## <a name="remarks"></a>Açıklamalar

Ön derlenmiş üst bilgi (PCH) dosyası oluşturmak için kaynak dosyada **/Yıc**<em>filename</em> seçeneğini kullandığınızda, bu kaynak dosya dosya *adı* üst bilgi dosyasını içermelidir. Belirtilen *dosya adı* dahil olmak üzere kaynak dosyanın içerdiği her dosya, PCH dosyasına dahildir. PCH dosyasını kullanmak için **/yu**<em>filename</em> seçeneği kullanılarak derlenen diğer kaynak dosyalarında dosya *adı* ekleme, dosyadaki ilk açıklama olmayan satır olmalıdır. Derleyici, kaynak dosyasındaki bu dahil etmeden önce herhangi bir şeyi yoksayar.

Bu hata, `#include "filename"` pch kaynak dosyanızda derlenmemiş bir koşullu derleme bloğundaki bir deyimin oluşmasına neden olabilir.

## <a name="example"></a>Örnek

Tipik kullanımda, projenizdeki bir kaynak dosya, PCH kaynak dosyası olarak atanır ve bir üst bilgi dosyası, PCH üstbilgi dosyası olarak kullanılır. Tipik bir PCH üstbilgi dosyası projenizde kullanılan tüm kitaplık üst bilgilerine sahiptir, ancak hala geliştirme aşamasında olan yerel üstbilgiler değildir. Bu örnekte, PCH üstbilgi dosyası *my_pch. h* olarak adlandırılır.

```cpp
// my_pch.h
#pragma once
#include <stdio.h>
```

PCH kaynak dosyası, **/YC**<em>my_pch. h</em> seçeneği kullanılarak derlenir. Derleyici bu PCH üstbilgi dosyasını içeren bir içerme bulamazsa, C2857 oluşturur:

```cpp
// my_pch.cpp
// Compile by using: cl /EHsc /W4 /Yumy_pch.h /c my_pch.cpp

#if 0
#include "my_pch.h"  // C2857; remove conditional directives to fix
#endif
```

Bu PCH dosyasını kullanmak için, kaynak dosyaların **/yu**<em>my_pch. h</em> seçeneği kullanılarak derlenmesi gerekir. PCH üstbilgi dosyası, önce PCH 'yi kullanan kaynak dosyalarında yer almalıdır:

```cpp
// C2857.cpp
// Compile my_pch.cpp first, then
// compile by using: cl /EHsc /W4 /Yumy_pch.h my_project.cpp my_pch.obj
// Include the pch header before any other non-comment line
#include "my_pch.h"

int main()
{
    puts("Using a precompiled header file.\n");
}
```
