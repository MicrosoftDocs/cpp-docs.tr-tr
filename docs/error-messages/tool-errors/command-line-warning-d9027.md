---
description: 'Hakkında daha fazla bilgi edinin: Command-Line Warning D9027'
title: Komut Satırı Uyarısı D9027
ms.date: 11/04/2016
f1_keywords:
- D9027
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
ms.openlocfilehash: 8c17750f3310072f8f69c77587a1c17fc9377e79
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136116"
---
# <a name="command-line-warning-d9027"></a>Komut Satırı Uyarısı D9027

' ' kaynak dosyası \<filename> yoksayıldı

CL.exe giriş kaynak dosyasını yok sayıldı.

Bu uyarı,/FO seçeneği ile bir komut satırındaki bir çıkış dosya adı arasındaki bir boşluk,/c seçeneği ile kaynaklanıyor olabilir. Örneğin:

```
cl /c /Fo output.obj input.c
```

/Fo ve arasında bir boşluk olduğundan `output.obj` CL.exe `output.obj` giriş dosyasının adı olarak alır. Sorunu gidermek için, alanı kaldırın:

```
cl /c /Fooutput.obj input.c
```
