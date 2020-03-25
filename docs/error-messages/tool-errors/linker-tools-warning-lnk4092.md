---
title: Bağlayıcı Araçları Uyarısı LNK4092
ms.date: 11/04/2016
f1_keywords:
- LNK4092
helpviewer_keywords:
- LNK4092
ms.assetid: d569ec47-a338-40e1-940b-8a8061459acb
ms.openlocfilehash: 706ab843f4b079b507033af76a7f407816fce820
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183364"
---
# <a name="linker-tools-warning-lnk4092"></a>Bağlayıcı Araçları Uyarısı LNK4092

Paylaşılan yazılabilir Bölüm ' section ' yeniden konumlar içeriyor; görüntü düzgün çalışmayabilir

Bağlayıcı, önemli olabilecek bir sorundan dolayı sizi uyaran paylaşılan bir bölüm olduğunda bu uyarıyı yayar.

Birden çok işlem arasında veri paylaşmanın bir yolu, bir bölümü "paylaşılan" olarak işaretlemenize olanak sağlar. Ancak, bir bölümü paylaşılan olarak işaretlemek sorunlara yol açabilir. Örneğin, paylaşılan bir veri bölümünde bunun gibi bildirimleri içeren bir DLL 'SI vardır:

```
int var = 1;
int *pvar = &var;
```

Değeri DLL 'nin belleğe yüklendiği yere bağlı olduğundan, bağlayıcı `pvar` çözümlenemiyor, bu nedenle DLL 'ye bir yeniden konumlandırma kaydı koyar. DLL belleğe yüklendiğinde, `var` adresi çözülebilir ve `pvar` atanabilir. Başka bir işlem aynı DLL 'yi yüklerse, ancak aynı adrese yükleyemezse, `var` adresi için yeniden konumlandırma ikinci işlem için güncelleştirilir ve ilk işlemin adres alanı yanlış adrese işaret eder.
