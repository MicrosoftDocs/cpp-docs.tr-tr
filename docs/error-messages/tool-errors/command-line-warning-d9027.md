---
title: Komut Satırı Uyarısı D9027
ms.date: 11/04/2016
f1_keywords:
- D9027
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
ms.openlocfilehash: 46ed5750bd1f315f20658ace9b83fac532fbbabb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80196684"
---
# <a name="command-line-warning-d9027"></a>Komut Satırı Uyarısı D9027

'\<filename > ' kaynak dosyası yoksayıldı

CL. exe giriş kaynak dosyasını yoksaydı.

Bu uyarı,/FO seçeneği ile bir komut satırındaki bir çıkış dosya adı arasındaki bir boşluk,/c seçeneği ile kaynaklanıyor olabilir. Örneğin:

```
cl /c /Fo output.obj input.c
```

/Fo ve `output.obj`arasında bir boşluk olduğundan, CL. exe giriş dosyasının adı olarak `output.obj` alır. Sorunu gidermek için, alanı kaldırın:

```
cl /c /Fooutput.obj input.c
```
