---
title: Bağlayıcı Araçları Uyarısı LNK4221
ms.date: 11/04/2016
f1_keywords:
- LNK4221
helpviewer_keywords:
- LNK4221
ms.assetid: 8e2eb2de-9532-4b85-908a-8c9ff5c4cccb
ms.openlocfilehash: baea8643001c550aeb3cb35dc6fe414e4330c0c1
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51523474"
---
# <a name="linker-tools-warning-lnk4221"></a>Bağlayıcı Araçları Uyarısı LNK4221

Bu nesne dosyası tüm önceden tanımlanmamış ortak sembolleri tanımlamaz, bu şekilde, bu kitaplığı kullanan bağlantı işlemleri tarafından kullanılmayacak

Aşağıdaki iki kod parçacıkları göz önünde bulundurun.

```
// a.cpp
#include <atlbase.h>
```

```
// b.cpp
#include <atlbase.h>
int function()
{
   return 0;
}
```

İki nesnesi dosyası oluşturun ve dosyalarını derlemek için çalıştırın **cl /c a.cpp b.cpp** bir komut isteminde. Nesne dosyası çalıştırarak bağlarsanız **bağlantı//out:test.lib a.obj b.obj lib**, LNK4221 uyarı alırsınız. Çalıştırarak nesneleri bağlarsanız **bağlantı//out:test.lib b.obj a.obj lib**, bir uyarı almaz.

Bağlayıcının son giren ilk çıkar (LIFO) bir biçimde çalıştığından İkinci senaryoda hiçbir uyarı verilir. İlk senaryoda b.obj a.obj önce işlenir ve eklemek için yeni sembol a.obj sahiptir. Bağlayıcı a.obj işlenecek yönlendirerek uyarı önleyebilirsiniz.

İki kaynak dosyaları seçeneğini belirttiğinizde, bu hatanın yaygın bir nedeni olduğundan [/Yc (önceden derlenmiş üst bilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md) belirtilen üst bilgi dosyası aynı ada sahip **önceden derlenmiş üst bilgi** alan. Varsayılan olarak, stdafx.cpp stdafx.h içerir ve yeni simgeleri eklemez olduğundan, bu sorunun sık karşılaşılan bir nedeni stdafx.h ile ilgilidir. Başka bir kaynak dosyası ile stdafx.h içeriyorsa **/Yc** ve ilişkili .obj dosyasına stdafx.obj önce işlenir, bağlayıcı LNK4221 oluşturmaz.

Tek yönlü Bu sorunu olduğu için her ön derlenmiş üstbilgi emin olmak için çözmek için onunla içeren yalnızca bir kaynak dosya var. **/Yc**. Önceden derlenmiş üst bilgiler tüm kaynak dosyalarını kullanmanız gerekir. Bu ayar değiştirme hakkında daha fazla bilgi için bkz. [/Yu (önceden derlenmiş üst bilgi dosyasını kullanma)](../../build/reference/yu-use-precompiled-header-file.md).