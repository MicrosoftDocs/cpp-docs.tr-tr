---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları uyarısı LNK4092'
title: Bağlayıcı Araçları Uyarısı LNK4092
ms.date: 11/04/2016
f1_keywords:
- LNK4092
helpviewer_keywords:
- LNK4092
ms.assetid: d569ec47-a338-40e1-940b-8a8061459acb
ms.openlocfilehash: 6ef835981a8ed7921147697d6ed9fc79ceeb7033
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210016"
---
# <a name="linker-tools-warning-lnk4092"></a>Bağlayıcı Araçları Uyarısı LNK4092

Paylaşılan yazılabilir Bölüm ' section ' yeniden konumlar içeriyor; görüntü düzgün çalışmayabilir

Bağlayıcı, önemli olabilecek bir sorundan dolayı sizi uyaran paylaşılan bir bölüm olduğunda bu uyarıyı yayar.

Birden çok işlem arasında veri paylaşmanın bir yolu, bir bölümü "paylaşılan" olarak işaretlemenize olanak sağlar. Ancak, bir bölümü paylaşılan olarak işaretlemek sorunlara yol açabilir. Örneğin, paylaşılan bir veri bölümünde bunun gibi bildirimleri içeren bir DLL 'SI vardır:

```
int var = 1;
int *pvar = &var;
```

`pvar`DEĞERI dll 'nin belleğe yüklendiği yere bağlı olduğundan bağlayıcı çözümlenemiyor, bu nedenle dll 'ye bir konum değiştirme kaydı koyar. DLL belleğe yüklendiğinde, adresi `var` çözülebilir ve `pvar` atanabilir. Başka bir işlem aynı DLL 'yi yüklerse, ancak aynı adrese yükleyemezse, adresi için yeniden konumlandırma `var` ikinci işlem için güncelleştirilir ve ilk işlemin adres alanı yanlış adrese işaret eder.
