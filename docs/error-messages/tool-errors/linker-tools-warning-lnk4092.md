---
title: Bağlayıcı Araçları Uyarısı LNK4092
ms.date: 11/04/2016
f1_keywords:
- LNK4092
helpviewer_keywords:
- LNK4092
ms.assetid: d569ec47-a338-40e1-940b-8a8061459acb
ms.openlocfilehash: 0b18002135d225a90f7e45adc2ff57a64c0a79f4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62279326"
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