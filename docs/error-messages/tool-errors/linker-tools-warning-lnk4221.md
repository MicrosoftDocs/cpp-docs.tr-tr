---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları uyarısı LNK4221'
title: Bağlayıcı Araçları Uyarısı LNK4221
ms.date: 08/19/2019
f1_keywords:
- LNK4221
helpviewer_keywords:
- LNK4221
ms.assetid: 8e2eb2de-9532-4b85-908a-8c9ff5c4cccb
ms.openlocfilehash: d7aee041536afc1da0c4fd8a6e520ceb5e99e57a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222638"
---
# <a name="linker-tools-warning-lnk4221"></a>Bağlayıcı Araçları Uyarısı LNK4221

Bu nesne dosyası önceden tanımlanmamış ortak sembolleri tanımlamaz, bu nedenle bu kitaplığı kullanan bağlantı işlemleri tarafından kullanılmayacak

Aşağıdaki iki kod parçacıklarını göz önünde bulundurun.

```cpp
// a.cpp
#include <atlbase.h>
```

```cpp
// b.cpp
#include <atlbase.h>
int function()
{
   return 0;
}
```

Dosyaları derlemek ve iki nesne dosyası oluşturmak için, komut isteminde **cl/c a. cpp b. cpp** komutunu çalıştırın. Nesne dosyalarını, **/lib/Out: test. lib a. obj b. obj bağlantısını** çalıştırarak BAĞLARSANıZ, LNK4221 uyarısını alırsınız. Nesneleri, **/lib/Out: test. lib b. obj a. obj**' i çalıştırarak bağlarsanız, bir uyarı almazsınız.

Bağlayıcı en son ilk çıkar (LıFO) şekilde çalıştığından ikinci senaryoda uyarı verilmez. İlk senaryoda, b. obj bir. obj öncesinde işlenir ve bir. obj eklenecek yeni bir sembol içermez. Önce bir. obj öğesini işlemek için bağlayıcıyı inceleyerek, uyarıdan kaçınabilirsiniz.

::: moniker range=">=msvc-160"

Bu hatanın yaygın nedenlerinden biri, **ön derlenmiş üstbilgi** alanında aynı üstbilgi dosyası adı ile [/Yc (ön derlenmiş üstbilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md) seçeneğini belirtmektir. Varsayılan olarak, *pch. cpp* , pch. *h* ' yi içerdiğinden ve yeni semboller eklemediğinden bu sorunun yaygın bir nedeni, *pch. h* ile ilgilidir. Başka bir kaynak dosyası, **/YC** ile *pch. h* ve ilişkili. obj dosyası pch. obj öğesinden önce IŞLENDIYSE, bağlayıcı LNK4221 oluşturur.

::: moniker-end

::: moniker range="<=msvc-150"

Bu hatanın yaygın nedenlerinden biri, **ön derlenmiş üstbilgi** alanında aynı üstbilgi dosyası adı ile [/Yc (ön derlenmiş üstbilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md) seçeneğini belirtmektir. Bu sorunun yaygın nedenlerinden biri stbafx *. h* ile ilgilidir, bu nedenle stbafx. *cpp* , *stbafx. h* öğesini içerir ve yeni semboller eklemez. Başka bir kaynak dosyası, **/YC** ile *stdadfx. h* ve ilişkili. obj dosyası stbafx. obj öğesinden önce IŞLENDIYSE, bağlayıcı LNK4221 atar.

::: moniker-end

Bu sorunu çözmek için bir yol, her ön derlenmiş üst bilgi için, bunu **/Yıc** ile içeren yalnızca bir kaynak dosyası olduğundan emin olmak içindir. Diğer tüm kaynak dosyaları önceden derlenmiş üst bilgiler kullanmalıdır. Bu ayarı değiştirme hakkında daha fazla bilgi için bkz. [/yu (önceden derlenmiş üst bilgi dosyasını kullan)](../../build/reference/yu-use-precompiled-header-file.md).
