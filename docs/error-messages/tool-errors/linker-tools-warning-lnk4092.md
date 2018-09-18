---
title: Bağlayıcı araçları uyarısı LNK4092 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4092
dev_langs:
- C++
helpviewer_keywords:
- LNK4092
ms.assetid: d569ec47-a338-40e1-940b-8a8061459acb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b9b47b347e11e640425bc7840a0f78a33e9e3b7e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46113428"
---
# <a name="linker-tools-warning-lnk4092"></a>Bağlayıcı Araçları Uyarısı LNK4092

Paylaşılan yazılabilir bölüm 'bölümü' konum değiştirmeleri içeriyor; Görüntü düzgün çalışmayabilir

Bağlayıcı, potansiyel ciddi bir sorun sizi uyarabilmek için paylaşılan bir bölümü olduğunda bu uyarı yayar.

Bir bölüm "paylaşılan" olarak işaretlemek için birden çok işlem arasında veri paylaşımı yollarından biri açıklanmıştır. Ancak, bir bölüm paylaşılan olarak işaretlenmesi sorunlara neden olabilir. Örneğin, bir paylaşılan veri bölümü şöyle bildirimlerinde içeren bir DLL vardır:

```
int var = 1;
int *pvar = &var;
```

Bağlayıcı çözümlenemiyor `pvar` nerede bellekte DLL yüklü değerine bağlı olduğundan, bu nedenle bunu koyar bir yeniden konumlandırma kaydı DLL'de. Ne zaman dll Dosyasının belleğe yüklendiği, adresini `var` çözülebilir ve `pvar` atanmış. Başka bir işlem aynı DLL'yi yükler, ancak aynı anda yüklenemiyor adres, adresi için bir yeniden konumlandırma `var` ikinci işlem ve ilk işlemin adres alanı yanlış adresine işaret edecek için güncelleştirilir.